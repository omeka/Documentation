---------------
UsersController
---------------

Package: :doc:`Controller </Reference/packages/Controller/index>`

.. php:class:: UsersController

extends :php:class:`Omeka_Controller_AbstractActionController`

    .. php:attr:: _publicActions

        protected array

        Actions that are accessible by anonymous users.

    .. php:attr:: _browseRecordsPerPage

        protected

    .. php:method:: init()

    .. php:method:: _handlePublicActions()

        Peform common processing for the publicly accessible actions.

        Set a view script variable for header and footer view scripts and don't
        allow logged-in users access.

        The script variables are set for actions in $_publicActions, so the
        scripts for those actions should use these variables.

    .. php:method:: forgotPasswordAction()

        Send an email providing a link that allows the user to reset their
        password.

    .. php:method:: _sendResetPasswordEmail($toEmail, $activationCode)

        :param $toEmail:
        :param $activationCode:

    .. php:method:: activateAction()

    .. php:method:: addAction()

        :returns: void

    .. php:method:: editAction()

        Similar to 'add' action, except this requires a pre-existing record.

        The ID For this record must be passed via the 'id' parameter.

        :returns: void

    .. php:method:: changePasswordAction()

    .. php:method:: apiKeysAction()

    .. php:method:: browseAction()

    .. php:method:: deleteAction()

    .. php:method:: _getDeleteSuccessMessage($record)

        :param $record:

    .. php:method:: _getDeleteConfirmMessage($record)

        :param $record:

    .. php:method:: sendActivationEmail($user)

        Send an activation email to a new user telling them how to activate
        their account.

        :type $user: User
        :param $user:
        :returns: boolean True if the email was successfully sent, false otherwise.

    .. php:method:: loginAction()

    .. php:method:: getLoginErrorMessages(Zend_Auth_Result $result)

        This exists to customize the messages that people see when their attempt
        to login fails. ZF has some built-in default messages, but it seems like
        those messages may not make sense to a majority of people using the
        software.

        :type $result: Zend_Auth_Result
        :param $result:
        :returns: string

    .. php:method:: logoutAction()

    .. php:method:: _getUserForm(User $user, $ua = null)

        :type $user: User
        :param $user:
        :param $ua:

    .. php:method:: _getLog()
