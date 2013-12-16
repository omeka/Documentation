#############################
Extending Exhibit Builder 3.0
#############################

Exhibit Builder 3.0 allows other plugins to add their own layouts.

**********************************
Placing layouts within your plugin
**********************************

The new Exhibit Builder layouts use the same "views" system as other Omeka
pages and views.

In any plugin (including the Exhibit Builder itself), layout views go in
the path ``views/shared/exhibit_layouts``.

************************
Registering a new layout
************************

Exhibit Builder provides a filter named ``exhibit_layouts``. To add a new
layout, you must hook into this filter and add some information about your
new layout. You need to decide three things:

- ID: an internal name for the layout and the name of the layout folder
- Name: the admin user-facing name for the layout
- Description: the admin user-facing description of the layout

The ID is the key into the array of layouts, and the name and description are
keys in an internal array. A filter implementation looks like this::

    public function filterExhibitLayouts($layouts) {
        $layouts['new-layout'] = array(
            'name' => 'New Layout',
            'description' => 'A new layout.'
        );
        return $layouts;
    }

************************************
Basic structure of an exhibit layout
************************************

Each layout has its own folder under the path mentioned above. The folder name
is the layouts ID, which will be used internally by the Exhibit Builder to find
and store the layouts picked by the user. An ID is simply a text string, and
the convention is that layout IDs be ASCII, lowercase, and hyphen-separated:
``sample-layout``, not ``SampleLayout`` or ``SampleLayout``.

Inside the layout folder, there are several files with predefined names that
the Exhibit Builder will look for:

form.php
    The PHP view file for the admin-side display of a form for the user to
    configure attachments, text, and options for a single block with this
    layout.

layout.php
    The PHP view file for the public-side display of a single block with this
    layout.

layout.css
    A CSS stylesheet that is automatically loaded when this layout is used on
    a public page.

layout.png
    A PNG preview image for the layout. This image is displayed on the admin
    side when the user is selecting the layout to use. To fit with the images
    for the other layouts, the image should be 260 pixels wide by 140 pixels
    tall.

Your views can reference and use other files with names of your choosing, but
the ones specified above are required and must be at the given locations.

***************************
The layout form -- form.php
***************************

The page block that the layout is being used on is accesible in the form.php
view as ``$block``. This block object is passed to the form helpers and is
used when form entries are created manually.

Attachments
-----------

The attachment interface is added by a simple helper::
    
    echo $this->exhibitFormAttachments($block);

Text
----

The text entry box is also added by a simple helper::

    echo $this->exhibitFormText($block);

Options
-------

Options are handled differently by each layout, so there is no standard form
helper for them. Instead, you should use the built-in Zend form helpers to
create form inputs for your layout options.

Internally, options are stored as a JSON-serialized array. Exhibit Builder
automatically saves any options that are sub-keys of the ``options`` key
in a block form.

Each block needs a different form name "stem," indexed by block. So, when
you're manually creating form inputs, you need to get this stem from the
block object::

    $formStem = $block->getFormStem();

The pre-existing options are also available on the block object::

    $options = $block->getOptions();

With those pieces of data, you can manually create a form input that will
reflect the status of an option. For example, a simple text input for 
an option named 'some-option'::

    echo $this->formText($formStem . '[options][some-option]', @options['some-option']);

*****************************
The layout view -- layout.php
*****************************

The layout view has four variables assigned to it.

``$attachments``
    An array of the attachment objects for items the user has attached to this
    block.

``$text``
    A string, containing the HTML text the user entered for this block. This
    text is filtered and can be output directly.

``$options``
    An array of the options the user selected for this block.

``$index``
    An integer, the index within the page of the current block.

Attachments
-----------

Single attachments
..................

There are two main helpers for displaying attachments on a layout. The first is
simply used for displaying a single attachment using Omeka's file display
functionality. This helper is the ``exhibitAttachment`` helper.

The ``exhibitAttachment`` helper takes 4 arguments, but only the first,
``$attachment``, is required.

``$attachment``
    The attachment object to display. This should be retrieved from the
    ``$attachments`` array assigned to the view.

``$fileOptions``
    An array of options for displaying the attached file. See the Usage section
    of the :php:func:`file_markup` documentation for examples of display options.

``$linkProps``
    An array of HTML attributes that will appear on the link to the item. This link
    will appear if an attachment is for an item with no files, or if the
    ``$forceImage`` argument is true.

``$forceImage``
    A boolean argument. If true, the normal :php:func:`file_markup`-style display
    will not be used, and instead :php:func:`file_image` will be. This can be
    useful for displaying attachments in grids or other structures where
    differing sizes and display methods would be unusable. This argument defaults
    to false.

The simplest possible example of using this helper just passes the attachment::
    
    foreach ($attachments as $attachment):
        echo $this->exhibitAttachment($attachment);
    endforeach;

Attachment galleries
....................

The second helper is the ``exhibitAttachmentGallery`` helper. The gallery helper
takes an array of attachments, and displays them in a gallery format.

``exhibitAttachmentGallery`` takes three arguments, only the first of which,
``$attachments``, is required.

``$attachments``
    An array of attachments to display a gallery of.

``$fileOptions``
    An array of file display options: see the explanation for the previous
    helper. If no ``imageSize`` option is given, the square thumbnail size
    is automatically selected by this function.

``$linkProps``
    An array of HTML attributes for the link around each displayed attachment.
    See the explanation for the previous helper.

Again, the simplest possible example simply passes the attachments. A gallery
of all attachments on a block in square thumbnail format is simple::

    echo $this->exhibitAttachmentGallery($attachments);

Custom displays
...............

Of course, you may wish to use the attached items and files in a
completely different way than the normal Omeka file display. In that
case, you can directly access the Item and File objects for each
attachment object, and work on them however you wish::

    foreach ($attachments as $attachment):
        $item = $attachment->getItem();
        $file = $attachment->getFile();
    endforeach;

*************************
Layout style - layout.css
*************************

The layout.css file is automatically loaded when the layout is used on a 
page. Any given page can contain many different layouts simultaneously, so
you need to take some care that you don't write styles that will interfere
with other layouts.

To help with keeping styles separate, Exhibit Builder automatically wraps
your layout output in a div with the class ``layout-<your layout id``. In
general, styles in layout.css should start with that class selector as the
first component of every selector.

**********************
Including extra assets
**********************

Some scripts, styles or other content can be included directly in layout.php.
But, some content may need to be placed in the ``<head>``, or may only be
included in the page once. For these scenarios, Exhibit Builder provides a
hook to add content to the head for exhibit pages. Note: layout.css is
automatically included, so you don't need to write anything to include it.

The hook is called `exhibit_builder_page_head`. It sends two arguments, the
View object ``$view``, and ``$layouts``, a keyed array of the layouts in use
on the page being shown. You can check for your layout ID in the keys of
``$layouts`` and include whatever content your layout needs::

    public function hookExhibitBuilderPageHead($args) {
        if (array_key_exists('my-layout', $args['layouts'])) {
            queue_js_file('my-script');
        }
    }
