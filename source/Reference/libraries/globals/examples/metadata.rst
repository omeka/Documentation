Use ``metadata`` function to get the description information for a collection. Use options array to limit the description to only the first 150 characters.

.. code-block:: php
    
    <div class="collection record">
        <?php
            $description = metadata($collection, array('Dublin Core', 'Description'), array('snippet' => 150));
        ?>
        <?php if ($description): ?>
            <p class="collection-description"><?php echo $description; ?></p>
        <?php endif; ?>
    </div>