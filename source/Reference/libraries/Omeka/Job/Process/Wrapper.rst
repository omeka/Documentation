-------------------------
Omeka_Job_Process_Wrapper
-------------------------

.. php:class:: Omeka_Job_Process_Wrapper

    Package: :doc:`Job\\Process </Reference/packages/Job/Process/index>`

    Wrapper that allows Omeka_Job to work with the existing Process/
    Omeka_Job_Process_Dispatcher API. Jobs are passed in as the 'job' argument, 
    and this wrapper handles decoding and executing the job.

    .. php:attr:: _process
    


    .. php:method:: _getJob($str)
    
        :param unknown $str:

    .. php:method:: run($args)
    
        Args passed in will consist of the JSON-encoded task.
        
        :param unknown $args:

    .. php:method:: __construct(Process $process)
    
        :param Process $process:

    .. php:method:: __destruct()