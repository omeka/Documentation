---------------------------------------------
Omeka_Job_Dispatcher_Adapter_AdapterInterface
---------------------------------------------

Package: :doc:`Job\\Dispatcher\\Adapter </Reference/packages/Job/Dispatcher/Adapter/index>`

.. php:interface:: Omeka_Job_Dispatcher_Adapter_AdapterInterface

    Interface for job dispatcher adapters.

    .. php:method:: setQueueName($name)

        Set the name of the queue that the adapter will use for incoming jobs.

        Note that this will not be used by some adapters and should be implemented
        to return false in those cases.

        :type $name: string
        :param $name:

    .. php:method:: send($encodedJob, $metadata)

        Send the job to whatever underlying system is used by the adapter.

        :type $encodedJob: string
        :param $encodedJob: The job encoded as a string.  In most cases, this will be passed directly into whatever client or queue the adapter uses.
        :type $metadata: array
        :param $metadata: An array containing all the metadata for the job. This is the unencoded version of the first argument and exists as a convenience so that adapter writers do not have to attempt to decode the first argument manually. This array contains the following keys: <ul> <li>className - Corresponds to the class name of the job.</li> <li>options - Options that are passed to the job when it is instantiated.</li> <li>createdBy - User object (or null) corresponding to the user who created this job.</li> <li>createdAt - Zend_Date corresponding to the date/time at which this job was created.</li> </ul>
