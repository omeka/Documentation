.. _workingwiththeadmintheme:

############################
Working with the Admin Theme
############################


*********************************************
Building a Configuration Form for Your Plugin
*********************************************

Most of the page, including the save button and overall layout is built for you. You only need to supply the actual inputs to use. The following template will help you build your forms in a way that is consistent with the rest of Omeka:

.. code-block:: html
    
    
    <div class="field">
        <div class="two columns alpha">
            <label></label>    
        </div>    
        <div class="inputs five columns omega">
            <p class="explanation"></p>
            <div class="input-block">        
                <input />        
            </div>
        </div>
    </div>
