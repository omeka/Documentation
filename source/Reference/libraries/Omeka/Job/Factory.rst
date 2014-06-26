-----------------
Omeka_Job_Factory
-----------------

Package: :doc:`Job\\Factory </Reference/packages/Job/Factory/index>`

.. php:class:: Omeka_Job_Factory

    Factory for instantiating Omeka_Job instances.

    .. php:method:: __construct($options = array())

        :param $options:

    .. php:method:: from($json)

        Decode a message from JSON and use the results to instantiate a new job
        instance.

        :type $json: string
        :param $json:

    .. php:method:: build($data)

        Instantiate a new job instance from the arguments given.

        :param $data:
