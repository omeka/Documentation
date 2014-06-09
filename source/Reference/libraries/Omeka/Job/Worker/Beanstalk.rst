--------------------------
Omeka_Job_Worker_Beanstalk
--------------------------

.. php:class:: Omeka_Job_Worker_Beanstalk

    Package: :doc:`Job\\Worker </Reference/packages/Job/Worker/index>`

    .. php:method:: __construct(Pheanstalk_Pheanstalk $pheanstalk, Omeka_Job_Factory $jobFactory, Omeka_Db $db)
    
        :param Pheanstalk_Pheanstalk $pheanstalk: 
        :param Omeka_Job_Factory $jobFactory: 
        :param Omeka_Db $db:

    .. php:method:: work(Pheanstalk_Job $pJob)
    
        :param Pheanstalk_Job $pJob:

    .. php:method:: _interrupt($job)
    
        :param unknown $job: