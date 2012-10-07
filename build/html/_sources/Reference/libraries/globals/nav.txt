###
nav
###

.. php:function:: nav(array $links, integer|null $maxDepth = 0)

    Generate an unordered list of navigation links (and subnavigation links), 
    with class "current" for any links corresponding to the current page
    
    For example:
    <code>nav(array('Themes' => url('themes/browse')));</code>
    generates
    <code><li class="nav-themes"><a href="themes/browse">Themes</a></li></code>
    
    :param array $links: A keyed array, where key = text of the link, and value = uri of the link, or value = another ordered array $a with the following recursive structure: <ul> <li>$a['uri'] = URI of the link</li> <li>$a['subnav_links'] = array of $sublinks for the sub navigation (this can be recursively structured like $links)</li> <li>$a['subnav_attributes'] = associative array of attributes for the sub navigation</li> </ul> For example: <code> $links = array( 'Browse' => 'http://yoursite.com/browse', 'Categories' => array( 'uri' => 'http://yoursite.com/categories', 'subnav_links' => array( 'Dogs' => 'http://yoursite.com/dogs', 'Cats' => 'http://yoursite.com/cats' ), 'subnav_attributes' => array('class' => 'subnav') ), 'Contact Us' => 'http://yoursite.com/contact-us' ); echo nav($links); </code> This would produce: <code> <li><a href="http://yoursite.com/browse">Browse</a></li> <li><a href="http://yoursite.com/categories">Categories</a> <ul class="subnav"> <li><a href="http://yoursite.com/dogs">Dogs</a></li> <li><a href="http://yoursite.com/cats">Cats</a></li> </ul> </li> <li><a href="http://yoursite.com/contact-us">Contact Us</a><li> <code>
    :param integer|null $maxDepth: The maximum number of sub navigation levels to display. By default it is 0, which means it will only display the top level of links. If null, it will display all the levels.
    :returns: string HTML for the unordered list

*****
Usage
*****



********
Examples
********



