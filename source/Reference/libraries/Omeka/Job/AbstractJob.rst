---------------------
Omeka_Job_AbstractJob
---------------------

Package: :doc:`Job </Reference/packages/Job/index>`

.. php:class:: Omeka_Job_AbstractJob

implements :php:interface:`Omeka_Job_JobInterface`

    Abstract implementation of an Omeka job.

    Most plugin implementations of jobs will extend this class to gain convenient access to the database and other potentially important resources.

    .. php:attr:: _db

        protected Omeka_Db

    .. php:attr:: _dispatcher

        protected Omeka_Job_Dispatcher_DispatcherInterface

    .. php:attr:: _user

        protected User

    .. php:attr:: _options

        protected

    .. php:method:: __construct($options)

        :param $options:

    .. php:method:: _setOptions($options)

        Set all the options associated with this task.

        This is a convenience method that calls setter methods for the options
        given in the array.  If an element in the array does not have an
        associated setter method, it will be passed into the options array.

        :param $options:

    .. php:method:: setDb(Omeka_Db $db)

        :type $db: Omeka_Db
        :param $db:

    .. php:method:: setJobDispatcher(Omeka_Job_Dispatcher_DispatcherInterface $dispatcher)

        :type $dispatcher: Omeka_Job_Dispatcher_DispatcherInterface
        :param $dispatcher:

    .. php:method:: setUser(User $user)

        Set the given User object on the Job object.

        :type $user: User
        :param $user:

    .. php:method:: getUser()

        Get the User currently set on this Job, if any.

        :returns: User|null

    .. php:method:: resend()

        Resend the job using the same options that were passed to the current
        job.

    .. php:method:: perform()
