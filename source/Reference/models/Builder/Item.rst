------------
Builder_Item
------------

Package: :doc:`Record\\Builder </Reference/packages/Record/Builder/index>`

.. php:class:: Builder_Item

extends :php:class:`Omeka_Record_Builder_AbstractBuilder`

    Build an item.

    .. php:const:: IS_PUBLIC

    .. php:attr:: _recordClass

        protected

    .. php:attr:: _settableProperties

        protected

    .. php:method:: setElementTexts($elementTexts)

        Set the element texts for the item.

        :type $elementTexts: array
        :param $elementTexts:

    .. php:method:: setFileMetadata($fileMetadata)

        Set the file metadata for the item.

        :type $fileMetadata: array
        :param $fileMetadata:

    .. php:method:: setRecordMetadata($metadata)

        Overrides setRecordMetadata() to allow setting the item type by name
        instead of ID.

        :type $metadata: array
        :param $metadata:

    .. php:method:: _addElementTexts()

        Add element texts to a record.

    .. php:method:: _replaceElementTexts()

        Replace all the element texts for existing element texts.

    .. php:method:: _addTags()

        Add tags to an item (must exist in database).

    .. php:method:: addFiles($transferStrategy, $files, $options = array())

        Add files to an item.

        <li>'Url|Filesystem' => string|array If a string is given, this represents
        the source identifier of a single file (the URL representing the file, or
        the absolute file path, respectively).  If an array is given, it assumes
        that each entry in the array must be either an array or a string.  If it
        an array, there are several default keys that may be present:
        <ul>
        <li>'source' => Any identifier that is appropriate to the transfer
        strategy in use.  For 'Url', this should be a valid URL.  For
        'Filesystem',
        it must be an absolute path to the source file to be transferred.</li>
        <li>'name' => OPTIONAL The filename to give to the transferred file.  This
        can be any arbitrary filename and will be listed as the original filename
        of the file.  This will also be used to generate the archival filename for
        the file.  If none is given, this defaults to using the
        getOriginalFileName() method of the transfer adapter.</li>
        <li>'metadata' => OPTIONAL This could contain any metadata that needs to
        be associated with the file.  This should be indexed in the same fashion
        as for items.  See ActsAsElementText::addTextsByArray()</li>
        </ul></li>
        </ul>

        :type $transferStrategy: string|Omeka_File_Ingest_AbstractIngest
        :param $transferStrategy: This can either be one of the following strings denoting built-in transfer methods: 'Upload', 'Filesystem', 'Url' Or it could be an implemented Omeka_File_Ingest_AbstractIngest class.
        :type $files: string|array
        :param $files: This can be a single string, an array of strings, or an array of arrays, depending on the parameters that are needed by the underlying strategy.  Expected parameters for the built in strategies are as follows: <ul> <li>'Upload' => null|string If a string is given, it represents the POST parameter name containing the uploaded file(s).  If null is given, all files in the POST will be ingested.</li>
        :type $options: array
        :param $options: OPTIONAL May contain the following flags where appropriate: <ul> <li>'ignore_invalid_files' => Do not throw exceptions when attempting to ingest invalid files.  Instead, skip to the next file in the list and continue processing.  False by default. (all except Upload).</li> <li>'ignoreNoFile' => Ignore errors resulting from POSTs that do not contain uploaded files as expected (only for Upload).</li> </ul>
        :returns: array Set of File records ingested.  May be empty if no files were ingested.

    .. php:method:: _addIngestValidators(Omeka_File_Ingest_AbstractIngest $ingester)

        Add the default validators for ingested files.

        The default validators are whitelists for file extensions and MIME types,
        and those lists can be configured via the admin settings form.

        These default validators can be disabled by the
        'disable_default_file_validation'
        flag in the settings panel.

        Plugins can add/remove/modify validators via the 'file_ingest_validators'
        filter.

        :type $ingester: Omeka_File_Ingest_AbstractIngest
        :param $ingester:

    .. php:method:: _beforeBuild(Omeka_Record_AbstractRecord $record)

        :type $record: Omeka_Record_AbstractRecord
        :param $record:
