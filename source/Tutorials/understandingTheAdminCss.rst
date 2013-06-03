
.. _understanding_the_admin_css:

###########################
Understanding the Admin Css
###########################

*****************
Responsive Design
*****************

The Omeka Admin theme uses `Skeleton development kit <http://getskeleton.com/>` for easy, responsive styles. Each page consists of a twelve-column grid, with sections' columns defined by css classes. For example, a three column section would have the classes "three columns". 

.. image:: ../_static/images/columns.jpg

The first two columns are dedicated to navigation, while the latter ten holds the main content. Plugin views are contained within ten columns, and plugin writers should look to the structure of other admin views for markup patterns.

Within the main content, Omeka forms typically take up seven columns, and leave the last three for a save panel that follows the user down the page. The following is an example of markup from the "Add Item" view. The "alpha" class signifies the first set of columns within a set, and "omega" signifies the last set of columns. These classes modify the left and right margins respectively.

.. code-block:: html

    <section class="seven columns alpha" id="edit-form">
    
        <form method="post" enctype="multipart/form-data" id="item-form" action="">
    
        ...
        
        </form>
    
    </section>
    
    <section class="three columns omega">
    
    ...
    
    </section>

For reference:

* `Official Skeleton website <http://getskeleton.com/>`_
* `Build a Responsive, Mobile-Friendly Web Page With Skeleton <http://designshack.net/articles/css/build-a-responsive-mobile-friendly-web-page-with-skeleton/>`_ (For a more detailed guide on understanding and using Skeleton.)