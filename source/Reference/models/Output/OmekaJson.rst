----------------
Output_OmekaJson
----------------

.. php:class:: Output_OmekaJson

    Generates JSON version of the omeka-xml output, as dictated by the JsonML
    XSLT.

    .. php:const:: JSONML_XSLT_FILENAME
    
    
    
        JsonML XML stylesheet filename

    .. php:method:: toJson(Omeka_Output_OmekaXml_AbstractOmekaXml $omekaXml)
    
        Convert omeka-xml output to JSON.
        
        :param Omeka_Output_OmekaXml_AbstractOmekaXml $omekaXml: 
        :returns: string

