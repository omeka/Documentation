---------------------------------
Omeka_Job_Process_AbstractProcess
---------------------------------

.. php:class:: Omeka_Job_Process_AbstractProcess

    Package: :doc:`Job\\Process </Reference/packages/Job/Process/index>`

    Base class background processes descend from.

    .. php:attr:: _process
    


    .. php:attr:: _logger
    


    .. php:method:: __construct(Process $process, $logger)
    
        :param Process $process: 
        :param unknown $logger:

    .. php:method:: __destruct()

    .. php:method:: _log($message, $priority)
    
        :param unknown $message: 
        :param unknown $priority:

    .. php:method:: run($args)
    
        :param unknown $args: