Use in the ``config_form.php`` file of a plugin to load the view object. For more information on the available view helpers, see the `Zend documentation  <http://framework.zend.com/manual/2.0/en/modules/zend.view.helpers.html>`_

.. code-block:: php
  :emphasize-lines: 1,5

  <?php $view = get_view(); ?>

  <div class="inputs five columns omega">
    <p class="explanation"><?php echo __("Latitude of the map's initial center point, in degrees. Must be between -90 and 90."); ?></p>
    <?php echo $view->formText('default_latitude', get_option('geolocation_default_latitude')); ?>
  </div>
