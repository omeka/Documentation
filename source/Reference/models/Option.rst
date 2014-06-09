------
Option
------

.. php:class:: Option

    Package: :doc:`Record </Reference/packages/Record/index>`

    A site option saved in the database.
    
    Options are stored and accessed by string keys.

    .. php:attr:: name
    
        Option name.

    .. php:attr:: value
    
        Option value.

    .. php:method:: __toString()
    
        Use the option's value when treating it as a string.
        
        :returns: string

    .. php:method:: _validate()
    
        Validate the Option.
        
        An option must have a non-empty and unique name.