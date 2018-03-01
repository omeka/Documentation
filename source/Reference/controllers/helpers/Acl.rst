----------------------------------
Omeka_Controller_Action_Helper_Acl
----------------------------------

Package: :doc:`Controller\\ActionHelper </Reference/packages/Controller/ActionHelper/index>`

.. php:class:: Omeka_Controller_Action_Helper_Acl

extends :php:class:`Zend_Controller_Action_Helper_Abstract`

    Leverages the ACL to automatically check permissions for the current
    controller/action combo.

    .. php:attr:: _acl

        protected Zend_Acl

        ACL object.

    .. php:attr:: _currentUser

        protected User|null

        User record corresponding to the logged-in user, otherwise null.

    .. php:attr:: _allowed

        protected array

        Temporarily allowed permissions.

    .. php:attr:: _autoloadResourceObject

        protected bool

        Whether we should automatically try to set the resource object.

    .. php:method:: __construct($acl, $currentUser)

        Instantiated with the ACL permissions which will be used to verify
        permission levels.

        :type $acl: Zend_Acl
        :param $acl:
        :param $currentUser:

    .. php:method:: preDispatch()

        Determine whether or not access is granted to a specific
        controller/action.

        If the user has been authenticated, display the Access Forbidden error
        page.
        Otherwise, give the user an opportunity to login before trying again.

    .. php:method:: isAllowed($privilege, $resource = null)

        Notifies whether the logged-in user has permission for a given resource/
        privilege combination.

        If an ACL resource being checked has not been defined, access to that
        resource should not be controlled.  This allows plugin writers to
        implement controllers without also requiring them to be aware of the ACL.

        Conversely, in the event that an ACL resource has been defined, all access
        permissions for that controller must be properly defined.

        The names of resources should correspond to the name of the controller
        class minus 'Controller', e.g.
        Geolocation_IndexController -> 'Geolocation_Index'
        CollectionsController -> 'Collections'

        :type $privilege: string
        :param $privilege:
        :param $resource:
        :returns: bool

    .. php:method:: getResourceName()

        Retrieve the name of the ACL resource based on the name of the controller
        and, if not the default module, the name of the module.

        :returns: string

    .. php:method:: setCurrentUser($currentUser)

        :type $currentUser: User|null
        :param $currentUser:

    .. php:method:: setAllowed($rule, $isAllowed = true)

        Temporarily override the ACL's permissions for this controller

        :type $rule: string
        :param $rule:
        :type $isAllowed: bool
        :param $isAllowed:

    .. php:method:: setAutoloadResourceObject($autoload)

        Set whether the ACL helper should try to automatically load
        a resource object from the request.

        :type $autoload: bool
        :param $autoload:

    .. php:method:: _getResourceObjectFromRequest()

        Try to get the current resource object for the request.

        :returns: Zend_Acl_Resource_Interface|null

    .. php:method:: _isLoginRequest()
