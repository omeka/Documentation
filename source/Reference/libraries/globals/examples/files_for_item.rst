To display image icons without a link to the image files:

.. code-block:: php
    
    <div class="element-text">
        <?php echo files_for_item(
            array(
                'linkToFile' => false
            )
        ); ?>
    </div>


To add an attribute such as ``rel="lightbox"`` to the image links for use with lightbox:

.. code-block:: php
    
    <div class="element-text">
        <?php echo files_for_item(
            array(
                'linkAttributes' => array('rel' => 'lightbox')
            )
        ); ?>
    </div>

To add css class and id selectors to the images:

.. code-block:: php
    
    <div class="element-text">
        <?php echo files_for_item(
            array(
               'imgAttributes' => array('id' => 'foobar')
            )
        ); ?>
    </div>

To change the size of the images displayed for the item, for example to a fullsize image (this may be constrained by css):

.. code-block:: php
    
    <div class="element-text">
        <?php echo files_for_item(
            array(
               'imageSize' => 'fullsize'
            )
        ); ?>
    </div>

To change the default icon displayed, particularly if an image is not generated for a particular file associated with an item. Image files must be located in 'application/views/scripts/images'.

.. code-block:: php
    
    <div class="element-text">
        <?php echo files_for_item(
            array(
               'icons' => array('audio/mgep' => img('audio.gif'))
            )
        ); ?>
    </div>