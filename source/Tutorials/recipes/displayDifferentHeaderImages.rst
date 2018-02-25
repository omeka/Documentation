.. _recipesDisplayDifferentHeaderImages:


###############################
Display Different Header Images
###############################

********
Problem
********

I want to display a different header image if the page is a SimplePages page.

********
Solution
********

In the theme's header.php file, usually in theme/common/header.php, add the following code to change the image if the page is a SimplePage. This example comes from default theme::

    <header role="banner">
        <div id="site-title">
        <?php if ($bodyclass=='page simple-page'):?>
            <img src="my_image.jpg" alt="my_alt_text"/>
        <?php else: ?>
            <?php echo link_to_home_page(theme_logo()); ?>
        <?php endif ?>
        </div>
    </header>

In the site title div, the original code for the theme was::

    <header role="banner">
        <div id="site-title">
        <?php echo link_to_home_page(theme_logo()); ?>
        </div>
    </header>

The changes here check whether we're on a simple page, and if so will display your image of choice. Otherwise, it instead displays the theme logo.
