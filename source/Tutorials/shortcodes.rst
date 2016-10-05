#######################
Working with Shortcodes
#######################

.. versionadded:: 2.2

Starting with Omeka 2.2, Omeka offers shortcode support. The core comes with
several default shortcodes, and plugins can register their own, too. Users can
then insert shortcodes within free text, and Omeka will replace the shortcode
with whatever markup is returned from the registered callback. For more
information shortcodes from a user's persepective, see the
`Shortcodes page on the Omeka Codex <http://omeka.org/codex/Shortcodes>`_.

You can add support for shortcodes in two ways. First, plugins can add their
own shortcodes. For example, the Exhibit Builder plugin provides several
shortcodes for including Exhibits within other pages, and the Geolocation plugin
adds a shortcode for embedding a map. Second, plugins and themes can support
shortcodes within user-provided text. The Simple Pages plugin is the obvious
example of this: users can include shortcodes in the content of pages.

**********************
Adding a new shortcode
**********************

Shortcodes are added through the :php:func:`add_shortcode` function. The
function takes only two arguments: the name of the shortcode (what the user will
type at the beginning of the shortcode) and a
`callback <http://www.php.net/manual/en/language.types.callable.php>`_. A
plugin adding a shortcode should call :php:func:`!add_shortcode` in its
:doc:`/Reference/hooks/initialize` hook.

The callback will be called whenever a shortcode is encountered in text, and
is responsible for returning the markup that will actually be rendered on the
page in place of the shortcode. Two parameters are passed to the callback.
The first is an array of the arguments the user included in the shortcode (i.e.
``[my_shortcode arg1="value 1" arg2="value 2"]`` results in
``array('arg1' => 'value 1', 'arg2' => 'value 2')`` as the first parameter). The
second argument is an :php:class:`Omeka_View` instance, to simplify calling
view helpers or reading data from the view.

So, in all, a plugin can add a shortcode with very little code::

    class MyPlugin extends Omeka_Plugin_AbstractPlugin
    {
        protected $_hooks = array('initialize');

        public function hookInitialize()
        {
            add_shortcode('my_shortcode', array($this, 'shortcode'));
        }

        public function shortcode($args, $view)
        {
            return 'This is a very simple shortcode.';
        }
    }

***********************************
Supporting shortcodes in user input
***********************************

The flipside of adding new shortcodes is supporting shortcode replacement
in text input by the user. To support shortcodes, you only need to pass the
text through the :php:class:`shortcodes view helper <Omeka_View_Helper_Shortcodes>`.

Assuming ``$text`` is some text input by the user, you barely need to change
your code that would have normally output the text::

    /* No shortcode support: */
    echo $text;

    /* Shortcode support: */
    echo $this->shortcodes($text);

You can also use the shortcodes helper on static text::

    echo $this->shortcodes('[my_shortcode]');
