-----------------------------------
Omeka_Form_Element_SessionCsrfToken
-----------------------------------

Package: :doc:`Form </Reference/packages/Form/index>`

.. php:class:: Omeka_Form_Element_SessionCsrfToken

extends :php:class:`Zend_Form_Element_Xhtml`

    CSRF form protection

    This class is an adaptation of ZF's Hash element that uses a per-session token.

    .. php:attr:: helper

        string

        Use formHidden view helper by default

    .. php:attr:: _disableLoadDefaultDecorators

        protected bool

        Should we disable loading the default decorators?

    .. php:attr:: _token

        protected mixed

        Actual token used.

    .. php:attr:: _session

        protected Zend_Session_Namespace

    .. php:method:: init()

        Constructor

        Creates session namespace for CSRF token, and adds validator for CSRF
        token.

        :returns: void

    .. php:method:: setSession($session)

        Set session object

        :param $session:
        :returns: self

    .. php:method:: getSession()

        Get session object

        Instantiate session object if none currently exists

        :returns: Zend_Session_Namespace

    .. php:method:: getToken()

        Retrieve CSRF token

        :returns: string

    .. php:method:: render(Zend_View_Interface $view = null)

        Render CSRF token in form

        :type $view: Zend_View_Interface
        :param $view:
        :returns: string

    .. php:method:: getLabel()

        Override getLabel() to always be empty

        :returns: null

    .. php:method:: _initToken()

        Set the CSRF token

        If a session token exists, it is used. Otherwise, a new token is generated
        and saved in the session.

        :returns: self

    .. php:method:: _initCsrfValidator()

        Initialize CSRF validator

        :returns: self

    .. php:method:: _generateToken()

        Generate CSRF token

        :returns: void
