.. _recipeForRetainingSearchSortOrderWhenPaging:


###################################################################
Recipe for Retaining Search or Sort Order when Paging through Items
###################################################################

********
Problem
********

When paging item by item using the next and previous buttons, Omeka calls the next item in the database by its ID, not by the order that you have searched or sorted prior to viewing the individual items. 

********
Solution
********

My solution requires some changes to each theme.

1.	Create a **custom.php** file to hold the new navigation function.  The custom.php should be at the theme\'s root (ex: /APP_DIRECTORY/themes/default/custom.php)::

		function custom_paging()
		{
	    	//Starts a conditional statement that determines a search has been run
		    if (isset($_SERVER['QUERY_STRING'])) {
		    	
		        // Sets the current item ID to the variable $current
		        $current = metadata('item', 'id');
		        
		        //Break the query into an array
		        parse_str($_SERVER['QUERY_STRING'], $queryarray);
		        
		        //Items don't need the page level
		        unset($queryarray['page']);
		        
		        $itemIds = array();
		        $list = array();
		        if (isset($queryarray['query'])) {
		        	//We only want to browse previous and next for Items
		        	$queryarray['record_types'] = array('Item');
		        	//Get an array of the texts from the query.
		        	$textlist = get_db()->getTable('SearchText')->findBy($queryarray);
		        	//Loop through the texts ans populate the ids and records.
		        	foreach ($textlist as $value) {
		        		$itemIds[] = $value->record_id;
		        		$record = get_record_by_id($value['record_type'], $value['record_id']);
		        		$list[] = $record;
		        	}
		        }
		        elseif (isset($queryarray['advanced'])) {
			        if (!array_key_exists('sort_field', $queryarray))
			    	{
			    		$queryarray['sort_field'] = 'added';
			    		$queryarray['sort_dir'] = 'd';
			    	}
			        //Get an array of the items from the query.
		        	$list = get_db()->getTable('Item')->findBy($queryarray);
		        	foreach ($list as $value) {
		        		$itemIds[] = $value->id;
		        		$list[] = $value;
		        	}
		        }
		        //Browsing all items in general
		        else 
		        {
		        	if (!array_key_exists('sort_field', $queryarray))
			    	{
			    		$queryarray['sort_field'] = 'added';
			    		$queryarray['sort_dir'] = 'd';
			    	}
			    	$list = get_db()->getTable('Item')->findBy($queryarray);
		        	foreach ($list as $value) {
		        		$itemIds[] = $value->id;
		        	}
		        }
		    	
		        //Update the query string without the page and with the sort_fields
		        $updatedquery = http_build_query($queryarray);
		        $updatedquery = preg_replace('/%5B[0-9]+%5D/simU', '%5B%5D', $updatedquery);
		        
		        // Find where we currently are in the result set
		        $key = array_search($current, $itemIds);
		
		        // If we aren't at the beginning, print a Previous link
		        if ($key > 0) {
		            $previousItem = $list[$key - 1];
		            $previousUrl = record_url($previousItem, 'show') . '?' . $updatedquery;
		           	$text = __('&larr; Previous Item');
		            echo '<li id="previous-item" class="previous"><a href="' . html_escape($previousUrl) . '">' . $text . '</a></li>';
		        }
		 
		        // If we aren't at the end, print a Next link
		        if ($key >= 0 && $key < (count($list) - 1)) {
		            $nextItem = $list[$key + 1];
		            $nextUrl = record_url($nextItem, 'show') . '?' . $updatedquery;
		           	$text = __("Next Item &rarr;");
		           	echo '<li id="next-item" class="next"><a href="' . html_escape($nextUrl) . '">' . $text . '</a></li>';
		        }
		    } else {
		        // If a search was not run, then the normal next/previous navigation is displayed.
		        echo '<li id="previous-item" class="previous">'.link_to_previous_item_show().'</li>';
		        echo '<li id="next-item" class="next">'.link_to_next_item_show().'</li>';
		    }
		}
	

2.	Make sure the query parameters are being passed:
	In the **items/browse.php** class, replace the line::

		<h2><?php echo link_to_item(metadata('item', array('Dublin Core', 'Title')), array('class'=>'permalink')); ?></h2>

  with the following to pass the query and sorting parameters::

	    if(isset($_SERVER['QUERY_STRING']) && !empty($_SERVER['QUERY_STRING']))
	    {
	
	    	$searchlink = record_url('item').'?' . $_SERVER['QUERY_STRING'];
	
	    	echo '<h2><a href="'.$searchlink.'">'. metadata('item', array('Dublin Core','Title')).'</a></h2>';
	    }
	
	    else
	    {
	    	echo '<h2>'.link_to_item(metadata('item', array('Dublin Core','Title')), array('class'=>'permalink')).'</h2>';
	    }


3.	Have the links changed to use the new custom code from custom.php:
	In the **items/show.php** class, replace the lines::

	    <li id="previous-item" class="previous"><?php echo link_to_previous_item_show(); ?></li>

	    <li id="next-item" class="next"><?php echo link_to_next_item_show(); ?></li>

    with::

    	<?php custom_paging(); ?>


4.	Make a copy of the **application/views/scripts/search/index.php** and place it under the **THEME/search** directory (create one if it isn't already there).

5.	To preserve the query and sort parameters:
	In **search/index.php**, replace the line::

		<td><a href="<?php echo record_url($record, 'show'); ?>"><?php echo $searchText['title'] ? $searchText['title'] : '[Unknown]'; ?></a></td>

   with::

	   	<?php 
	
		if(isset($_SERVER['QUERY_STRING']) && !empty($_SERVER['QUERY_STRING']))
		{
			$searchlink = record_url($record, 'show').'?' . $_SERVER['QUERY_STRING'];
	
	    	?>
	
	
	
			<td><a href="<?php echo $searchlink; ?>"><?php echo $searchText['title'] ? $searchText['title'] : '[Unknown]'; ?></a></td>
	
		<?php
	    	}
	    	else
	    	{
	
		?>
	
			<td><a href="<?php echo record_url($record, 'show'); ?>"><?php echo $searchText['title'] ? $searchText['title'] : '[Unknown]'; ?></a></td>
		<?php 
	
		}
	
	    	?>
