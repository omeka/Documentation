You can use the $vars array to control the 'id' and 'class' information for the body element of a given page:

.. code-block:: php
    
    <?php echo head(array('bodyid'=>'home', 'bodyclass' =>'two-col')); ?>


While the page title is generated from the page metadata by default, you can set a page title manually by passing a 'title' to the head function:

.. code-block:: php

    <?php
    $title = __('Explorations');
    echo head(array('title' => $title, 'bodyclass' => 'explorations browse'));
    ?>


