.. _bestPracticesPlugins:


#####################################
Best Practices for Plugin Development
#####################################


*******************************
Use Omeka_Plugin_AbstractPlugin
*******************************

:php:class:`Omeka_Plugin_AbstractPlugin` is here to ease common steps in setting up your plugin. See :ref:`understandingomekapluginabstractplugin` for details.


*************************
Method Naming Conventions
*************************

Method names must be in camelCase (e.g., ``getItem()``).

For private or protected methods, prefix the method name with underscore (_).

See also `Zend's Coding Standards <http://framework.zend.com/manual/1.12/en/coding-standard.naming-conventions.html>`._

************************************
Maintain expected behaviors in Omeka
************************************

Omeka defines some hooks that operate on every record. For example, Omeka's :php:meth:`Omeka_Record_AbstractRecord::save` method fires hooks before and after saving. In most cases, you don't need to override it, but if you do, make sure you include ``$this->runCallbacks('beforeSave', $callbackArgs);`` and ``$this->runCallbacks('afterSave', $callbackArgs);`` where appropriate.

Similarly, whenever you override methods from abstract classes in Omeka, make sure that you have studied the parent methods' code to include all the expected callback. This will allow other developers to work with the expected behaviors of the objects.

Also, if you use any non-standard routing in your plugin, you must override :php:meth:`Omeka_Record_AbstractRecord::getRecordUrl` so that it returns the correct url to the record. Compare the ``getRecordUrl()`` method on the ``SimplePagesPage`` model in the "Simple Pages" plugin.

****************
Database changes
****************

Omeka 2.0 switched MySQL database engines from MyISAM_ to InnoDB_. We recommend 
that you set all plugin tables to InnoDB. Existing plugins may alter their 
tables during the upgrade hook::

    public function hookUpgrade($args)
    {
        if (version_compare($args['old_version'], $newPluginVersion, '<')) {
            // Change the storage engine to InnoDB.
            $sql = "ALTER TABLE {$this->_db->TableName} ENGINE = INNODB";
            $this->_db->query($sql);
        }
    }

.. _MyISAM: http://en.wikipedia.org/wiki/MyISAM
.. _InnoDB: http://en.wikipedia.org/wiki/InnoDB

********************************************
Use View Helpers instead of global functions
********************************************

View helpers are preferred alternatives to global theming functions. They 
provide a convenient interface (called directly from the view object) to logic 
and/or markup that's commonly used in view scripts. If you find yourself using 
global functions or static methods to support your views, consider using view 
helpers instead.

First, you must add your view helper directory path to the stack during plugin 
initialization::

    public function hookInitialize()
    {
        get_view()->addHelperPath(dirname(__FILE__) . '/views/helpers', 'PluginName_View_Helper_');
    }

Replace *PluginName* with your plugin's name. The helpers/ directory may be 
anywhere in your plugin's directory structure, but we recommend that you place 
it in the views/ directory for consistency.

Then create your view helper file in the helpers/ directory (named something 
like ViewHelperName.php) and in that file write your view helper class::

    class PluginName_View_Helper_ViewHelperName extends Zend_View_Helper_Abstract
    {
        public function viewHelperName($arg1, $arg2)
        {
            // Build markup.
            return $markup;
        }
    }

Note the use of UpperCamelCase and lowerCamelCase. The ``viewHelperName()`` 
method can accept any number of arguments and should return something, most 
often markup. You may add ``__construct()`` to the class if the helper needs a 
one-time setup (e.g. to assign class properties). The constructor will not be 
called on subsequent calls to the helper.

Now you can call your view helper directly in your view script like so:

.. code-block:: html+php

    <p><?php echo $this->viewHelperName() ?></p>

***************** 
Use View Partials
*****************

View partials let you separate out parts of long or complicated views into separate files. For example, if you have a browse view that allows different ordering, it is best to use view partials to separate the code for the different orderings to be in different partials. For example:

.. code-block:: html+php

    <?php if (isset($_GET['view']) && $_GET['view'] == 'hierarchy'): ?>
        <?php echo $this->partial('index/browse-hierarchy.php', array('simplePages' => get_simple_pages_for_loop())); ?>
    <?php else: ?>
        <?php echo $this->partial('index/browse-list.php', array('simplePages' => get_simple_pages_for_loop())); ?>
    <?php endif; ?>

When using hooks that add markup to views, such as 
:doc:`admin_items_show </Reference/hooks/admin_items_show>`, consider using 
partials instead of outputting markup directly in the callback.

************************************
Setting Up Your Plugin's Config Page
************************************




***********************
Building Forms in Admin
***********************

Omeka 2.0 admin interface works with modern CSS and design practices, including responsive design. Omeka 2.0 therefore also includes a :php:class:`Omeka_Form_Admin` class to help you quickly and easily build simple forms. It should be suitable for building basic add/edit forms. The SimplePages plugin makes uses it, can can offer a good example of usage.

It is best to put your form-building logic into your controller, e.g. in a ``_getForm()`` method. The :php:class:`Omeka_Form_Admin` class works basically as follows.

If you are editing an existing record, instantiate it like so: ``$form = new Omeka_Form_Admin(array('record'=>$record);``

If the form is for a record (which is typically the case), pass the record as one of the options. Additionally, if you want a link to the record's public page on the admin side, pass ``'hasPublicPage'=>true`` as an option::

    $options = array('record'=>$record, 'hasPublicPage'=>true);

Other options available for :php:class:`Omeka_Form_Admin` are:

``string`` type
    Often, this will be the record type (e.g. 'simple_pages_page'), but can be anything. Hooks for the save panel follow the type that you give. See :ref:`admintypepanelbuttons` and :ref:`admintypepanelfields`.

``string`` editGroupCssClass
    Change the CSS classes for the 'main' edit area. This should rarely be necessary.

``string`` saveGroupCssClass
    Change the CSS classes for the save panel. This should rarely be necessary.



To add your form elements to the main editing area, use :php:meth:`Omeka_Form_Admin::addElementToEditGroup`. You can either pass in a ``Zend_Form_Element`` you have already built, or pass in the parameters to build the element as if you were creating one. For example, creating a text input looks like this::

     $form->addElementToEditGroup(
         'text', 'title',
         array(
             'id'=>'simple-pages-title',
             'size'  => 40,
             'value' => metadata($page, 'title'),
             'label' => 'Title',
             'description' => 'The title of the page (required).',
             'required' => true
         )
     );

The first argument specifies the element type (text, textarea, etc.). The second gives the name to be used on the element in the form. The third gives a keyed array of various attributes for the element, as well as a label and a description.

If you build the Zend_Form_Element yourself, you can simply pass that in as the first parameter and leave the rest empty.

In some cases, it makes sense to add an element directly to the save panel on the right. This should be reserved for small, peripheral data, such as whether a record is public or featured, if the model implements those features.

Doing so works similarly, using the :php:meth:`Omeka_Form_Admin::addElementToSaveGroup` method::

        $form->addElementToSaveGroup(
            'checkbox', 'is_published',
            array(
                'id' => 'simple_pages_is_published',
                'values' => array(1, 0),
                'checked' => metadata($page, 'is_published'),
                'label' => 'Publish this page?',
                'description' => 'Checking this box will make the page public and it will appear in Simple Page navigation.'
            )
        );

As with ``addElementToEditGroup()``, you can build the element yourself and pass it as the first parameter.

For more complex form requiring tabs and a variety of sections, you'll want to familiarize yourself with :ref:`understanding_the_admin_css`.

See also :ref:`workingwiththeadmintheme`, which includes more details of how the HTML is constructed, and the CSS classes involved.

******
Search
******

Omeka 2.0 allows any record to be full-text searchable, not just items, but also 
files, collections, exhibits, etc. This includes records implemented by your 
plugin.

Individual record indexing and bulk-indexing will only work on record types that 
have been registered via the new 
:doc:`search_record_types </Reference/filters/search_record_types>` filter::
    
    public function filterSearchRecordTypes($searchableRecordTypes)
    {
        // Register the name of your record class. The key should be the name 
        // of the record class; the value should be the human readable and 
        // internationalized version of the record type.
        $searchableRecordTypes['YourRecord'] = __('Your Record');
        return $searchableRecordTypes;
    }

Follow this template to make your record searchable::

    class YourRecord extends Omeka_Record_AbstractRecord
    {
        // Add the search mixin during _initializeMixins() and after any mixins
        // that can add search text, such as Mixin_ElementText. Doing this
        // tells Omeka that you want this record to be searchable.
        protected function _initializeMixins()
        {
            // Add the search mixin.
            $this->_mixins[] = new Mixin_Search($this);
        }
     
        // Use the afterSave() hook to set the record's search text data.
        protected function afterSave($args)
        {
            // A record's search text is public by default, but there are times
            // when this is not desired, e.g. when an item is marked as
            // private. Make a check to see if the record is public or private.
            if ($private) {
                // Setting the search text to private makes it invisible to
                // most users.
                $this->setSearchTextPrivate();
            }
     
            // Set the record's title. This will be used to identify the record
            // in the search results.
            $this->setSearchTextTitle($recordTitle);
     
            // Set the record's search text. Records that implement the
            // Mixin_ElementText mixin during _initializeMixins() will
            // automatically have all element texts added. Note that you
            // can add multiple search texts, which simply appends them.
            $this->addSearchText($recordTitle);
            $this->addSearchText($recordText);
        }
     
        // The search results need a route to the record show page, so build 
        // a routing array here. You can also assemble the URL yourself using 
        // the URL view helper and return the entire URL as a string.
        public function getRecordUrl($action)
        {
            if ('your-show-action' == $action) {
                return $yourCustomRecordShowUrl;
            }
            return array(
                'module' => 'your-module', 
                'controller' => 'your-controller', 
                'action' => $action,
                'id' => $this->id, 
            );
        }
    }

***********************
Customizing Search Type
***********************

Omeka now comes with three search query types: keyword (full text), boolean, and 
exact match. Full text and boolean use `MySQL's native full text engine`_, while 
exact match searches for all strings identical to the query.

.. _`MySQL's native full text engine`: http://dev.mysql.com/doc/refman/5.0/en/fulltext-search.html

Plugin authors may customize the type of search by implementing the 
:doc:`search_query_types </Reference/filters/search_query_types>` filter. For 
example, if you want to implement a "ends with" query type that searches for 
records that contain at least one word that ends with a string::

    public function filterSearchQueryTypes($queryTypes)
    {
        // Accept an array and return an array.
        function your_search_query_types_callback($queryTypes)
        {
            // Register the name of your custom query type. The key should be 
            // the type's GET query value; the values should be the human 
            // readable and internationalized version of the query type.
            $queryTypes['ends_with'] = __('Ends with');
            return $queryTypes;
        }
    }

Then you must modify the search SQL using the 
:doc:`search_sql </Reference/hooks/search_sql>` hook, like so::

    public function hookSearchSql($args)
    {
        $params = $args['params'];
        if ('ends_with' == $params['query_type']) {
            $select = $args['select'];
            // Make sure to reset the existing WHERE clause.
            $select->reset(Zend_Db_Select::WHERE);
            $select->where('`text` REGEXP ?', $params['query'] . '[[:>:]]');
        }
    }

Remember that you're searching against an aggregate of all texts associated with 
a record, not structured data about the record.