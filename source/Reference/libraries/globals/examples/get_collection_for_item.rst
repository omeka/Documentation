Print the title and description of the Collection the current Item
belongs to (if any)::

    <?php
    $collection = get_collection_for_item();
    if ($collection):
    ?>
        <h3><?php echo metadata($collection, array('Dublin Core', 'Title')); ?></h3>
        <p><?php echo metadata($collection, array('Dublin Core', 'Description')); ?></p>
    <?php endif; ?>

