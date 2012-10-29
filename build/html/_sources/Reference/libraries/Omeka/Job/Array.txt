----------------------------------
Omeka_Job_Dispatcher_Adapter_Array
----------------------------------

.. php:class:: Omeka_Job_Dispatcher_Adapter_Array

    Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

    Store dispatched jobs in an array.
    
    This is used primarily by unit tests and should not be used in productioncode.

    .. php:attr:: _queueName
    


    .. php:attr:: _jobs
    


    .. php:method:: setQueueName($name)
    
        :param unknown $name:

    .. php:method:: send($encodedJob, $metadata)
    
        :param unknown $encodedJob: 
        :param unknown $metadata:

    .. php:method:: getJobs()

    .. php:method:: getJob($index = 0)
    
        :param unknown $index: