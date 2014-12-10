Use to check if user is accessing pages from within the ``admin`` views and  manage routes accordingly.

.. code-block:: php

  // Don't add these routes on the admin side to avoid conflicts.
  if (is_admin_theme()) {
      return;
  }
