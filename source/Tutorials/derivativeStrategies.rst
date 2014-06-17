##########################
File Derivative Strategies
##########################

.. versionadded:: 2.2

As of Omeka 2.2, administrators can switch between different strategies to
change the code that's used when creating thumbnails and other file derivatives.
Plugins can provide their own new strategies, and administrators can switch
between all available strategies and set options through the configuration file.

*********************************
Configuring a derivative strategy
*********************************

You switch derivative strategies and set their options through the configuration
file, :file:`application/config/config.ini`. All the file derivative settings
go under the key ``fileDerivatives``.

To set the strategy Omeka will use when creating derivatives, use the
``fileDerivatives.strategy`` setting. The value of the setting should be the
name of the strategy class you want to use. This class must implement
:php:interface:`Omeka_File_Derivative_StrategyInterface`. You can swtich
between the different strategies provided by Omeka, like
``ExternalImageMagick`` and ``Imagick``, or switch to a new strategy of your
own or one provided by a plugin. The string given must be the full name of the
class.

Beyond just switching the entire strategy, you can also configure settings for
each strategy through the config file. The key ``fileDerivatives.strategyOptions``
lets you specify named options that will be passed to the current strategy. For
example, both the built-in Omeka strategies support an option ``gravity``, which
sets which part of an image will be kept when cropping for a square thumbnail.
A site administrator would change this setting with one line in the config:

.. code-block:: ini

    fileDerivatives.strategyOptions.gravity = "north"

***********************
Creating a new strategy
***********************

Derivative strategies are classes implementing
:php:class:`Omeka_File_Derivative_StrategyInterface`. The interface has one main
entry point, the method :php:meth:`~Omeka_File_Derivative_StrategyInterface::createImage`.
``createImage`` is called by Omeka once per derivative type (thumbnail,
square thumbnail, fullsize) per file uploaded, and receives as arguments the
source and destination file paths, the type of image being created, the
configured size constraint, and the MIME type of the file.

``createImage`` simply returns a boolean true/false value. If the return value
is true, Omeka expects that a new derivative file will have been created at the
destination path. A return value of false indicates that the derivative process
failed and there is no derivative to upload. The strategy can use any means,
including PHP libraries or extensions, or even shell calls, to create the new
derivative, so long as it ends up in the correct location. Using the MIME type
parameter and/or the source path, a strategy could even use totally different
procedures for making derivatives for different kinds of files.

The interface also requires ``setOptions`` and ``getOptions`` methods, so
Omeka can inject the settings from the site's configuration file (see above).
You can implement these simple methods yourself, or you can extend from
:php:class:`Omeka_File_Derivative_AbstractStrategy`, which provides those methods
for you, but still leaves ``createImage`` as an abstract for you to override.
The ``AbstractStrategy`` class also provides a convenience method,
:php:meth:`~Omeka_File_Derivative_AbstractStrategy::getOption`, for getting a
specific named option with a fallback or default value.

A strategy simply needs to be located in a location Omeka can autoload from to
be available for the adiminstrator to select it in the config file. In a plugin
this means the class should live in the :file:`libraries` folder, at a path
conforming to `PSR-0 <http://www.php-fig.org/psr/psr-0/>`_.
