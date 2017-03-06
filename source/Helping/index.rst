.. _helping:

##########################
Helping With Documentation
##########################

We always appreciate help correcting and filling out stubs in our documentation. You can submit
contribute and make pull requests by clicking the "Edit on GitHub" link on any of the documentation
pages. Check the `README on the documentation GitHub repo <https://github.com/omeka/Documentation>`_ for details.

From our forums and a developer survey, we know that the biggest thing that will help the
community of Omeka developers is example code, especially code that fills out the documentation
for Global (Theming) Functions. Those files are located under ``libraries/globals/examples``. Each
file there corresponds to an Omeka global function that has automatically generated documentation.

*****************
Function Examples
*****************

If you would like to contribute how you have used or modified one of the Omeka globals functions, 
you can use the :ref:`exampletemplate` file as a starting point. Also, look at 
the `Metadata <https://github.com/omeka/Documentation/blob/master/source/Reference/libraries/globals/examples/metadata.rst>`_ 
file as a working sample. Just branch the corresponding file within GitHub 
(or create your own local copy), fill in the details of what you did, and submit a new pull request.

***************
Recipe Examples
***************

A second, broader, need is for recipes that fill out larger tasks. A recipe might combine several
functions or plugin structures to solve a large task.
These are found under ``Tutorials/recipes``. New ones can also be added via pull request.
There is also a :ref:`recipetemplate` for these, but the structure you use can follow whatever structures explain the process best.
Here is an example for `Retaining Search Order <https://github.com/omeka/Documentation/blob/master/source/Tutorials/recipes/retainingSearchSortOrderWhenPaging.rst>`_.

*******************
Docathon March 2017
*******************

Thanks to the CUNY Graduate Center, Omeka will be one of the projects tackled in 
`Docathon <https://bids.github.io/docathon/pages/hosts/gc.html>`_ the week of March 6, 2017.

You can find some guides to technical aspects above and in the 
`Documentation <https://github.com/omeka/Documentation>`_ README.

Here are a couple thoughts on quick and easy ways to help us all get the most out of Docathon.

**Have you hacked or built an Omeka theme?**

You've probably needed to modify the default use of one or more of Omeka's global
functions. (Or maybe you just had to figure out how it works!) If so, share your
example of what you did with the function so others can make more of the possibilities.

You might have rearranged pages, or incorporated other libraries to get your display just right.
Those would make excellent recipes to show how your solved a particular problem -- others will
want to learn from it for similar needs.

**Have you hacked or built an Omeka plugin?**

Some of the best Omeka plugins are the smallest ones that take care of a small need. Or,
an existing plugin might have been _close_ to what you needed, but called for some modification.
Sharing what you did as a recipe is a great way to reinforce what you learned and help others
in similar situations.

**Do you just want to learn a little about coding (for Omeka)?**

No time like the present. Tinkering with existing themes to make small changes to the display
is a great way to get started. You'll learn your way around themes, see how the functions work,
learn a little more about PHP, and help your fellow Omekans!

Start with an existing theme, and try your hand at modifying the output from one of the functions. 
Browse through the 
basic documentation for global functions, then find where they are used in an existing theme.
Then, experiment with some of the options listed in the documentation, but don't have an
example of the variety of options described. Then, share your example back for others to see
and learn from.


Submitting Additions and Changes
--------------------------------

A pull request is the best way to contribute. We'll give a quick look and provide feedback as
needed. We want to help you get your contribution available for everyone working
with Omeka as quickly as possible. You can do that either from a fork of the Documentation you
work on locally, or directly from GitHub. We'll be watching over the Docathon and respond as
quickly as we can.

Talking About Additions and Changes
-----------------------------------

For simplicity, we've created a couple of issues on the Documentation repo that reflect the guides
above. Adding comments there will be the quickest way to ask us a question. We'll be watching, and will 
respond as quickly as we can.

Hannah has also created a #cunygc channel in the `Docathon's Slack <http://docathon.slack.com>`_. That'll 
also be a good place to ask questions.
