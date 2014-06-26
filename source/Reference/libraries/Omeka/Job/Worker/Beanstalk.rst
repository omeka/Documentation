--------------------------
Omeka_Job_Worker_Beanstalk
--------------------------

Package: :doc:`Job\\Worker </Reference/packages/Job/Worker/index>`

.. php:class:: Omeka_Job_Worker_Beanstalk

    .. php:method:: __construct(Pheanstalk_Pheanstalk $pheanstalk, Omeka_Job_Factory $jobFactory, Omeka_Db $db)

        :type $pheanstalk: Pheanstalk_Pheanstalk
        :param $pheanstalk:
        :type $jobFactory: Omeka_Job_Factory
        :param $jobFactory:
        :type $db: Omeka_Db
        :param $db:

    .. php:method:: work(Pheanstalk_Job $pJob)

        :type $pJob: Pheanstalk_Job
        :param $pJob:

    .. php:method:: _interrupt($job = null)

        :param $job:
