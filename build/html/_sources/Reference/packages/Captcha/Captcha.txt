-------------
Omeka_Captcha
-------------

.. php:class:: Omeka_Captcha

    Package: :doc:`/Reference/packages/Captcha/index`

    Factory for creating a captcha for use when soliciting public input.

    .. php:method:: getCaptcha()
    
        Get a captcha object implementing Zend's captcha API.
        
        :returns: Zend_Captcha_Adapter|null

    .. php:method:: isConfigured()
    
        Return whether the captcha is configured.
        If this returns true, getCaptcha will not return null.
        
        :returns: boolean