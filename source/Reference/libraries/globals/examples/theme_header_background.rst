This function is used to set the header image for a theme. It creates an internal css block and is used within the ``<head>`` of the HTML page. 
 
.. code-block:: php

    <head>
        <?php echo theme_header_background(); ?>
    </head>

Results in:

.. code-block:: php
    
    <head>
        <style>
            header {background:transparent url("http://mysite/files/theme_uploads/0e4a046bfc9d5f4d988300168f237b22.jpg") center left no-repeat;}
        </style>
    </head>



