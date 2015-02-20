.. code-block:: php

  $navArray = array();
  $navArray[] = array('label'=>'Browse All', 'uri'=>url('items'));
  $navArray[] = array('label'=>'Browse By Tag', 'uri'=>url('items/tags');

  echo nav($navArray);
