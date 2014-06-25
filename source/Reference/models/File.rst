----
File
----

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: File

extends :php:class:`Omeka_Record_AbstractRecord`

implements :php:interface:`Zend_Acl_Resource_Interface`

    A file and its metadata.

    .. php:const:: DISABLE_DEFAULT_VALIDATION_OPTION

        Option name for whether the file validation is disabled.

    .. php:const:: DERIVATIVE_EXT

        File extension for all image derivatives.

    .. php:attr:: item_id

        int

        ID of the Item this File belongs to.

    .. php:attr:: order

        int

        Relative order of this File within the parent Item.

    .. php:attr:: filename

        string

        Current filename, as stored.

    .. php:attr:: original_filename

        string

        Original filename, as uploaded.

    .. php:attr:: size

        int

        Size of the file, in bytes.

    .. php:attr:: authentication

        string

        MD5 hash of the file.

    .. php:attr:: mime_type

        string

        MIME type of the file.

    .. php:attr:: type_os

        string

        Longer description of the file's type.

    .. php:attr:: has_derivative_image

        int

        Whether the file has derivative images.

    .. php:attr:: added

        string

        Date the file was added.

    .. php:attr:: modified

        string

        Date the file was last modified.

    .. php:attr:: stored

        int

        Whether the file has been moved to storage.

    .. php:attr:: metadata

        array

        Embedded metadata from the file.

    .. php:method:: getProperty($property)

        Get a property or special value of this record.

        :type $property: string
        :param $property:
        :returns: mixed

    .. php:method:: _initializeMixins()

        Initialize the mixins.

    .. php:method:: filterPostData($post)

        Unset immutable properties from $_POST.

        :type $post: array
        :param $post:
        :returns: array

    .. php:method:: beforeSave($args)

        Before-save hook.

        :type $args: array
        :param $args:

    .. php:method:: afterSave($args)

        After-save hook.

        :type $args: array
        :param $args:

    .. php:method:: getItem()

        Get the Item this file belongs to.

        :returns: Item

    .. php:method:: getPath($type = 'original')

        Get a system path for this file.

        Local paths are only available before the file is stored.

        :type $type: string
        :param $type:
        :returns: string

    .. php:method:: getWebPath($type = 'original')

        Get a web path for this file.

        :type $type: string
        :param $type:
        :returns: string

    .. php:method:: getDerivativeFilename()

        Get the filename for this file's derivative images.

        :returns: string

    .. php:method:: hasThumbnail()

        Determine whether this file has a thumbnail image.

        :returns: bool

    .. php:method:: hasFullsize()

        Determine whether this record has a fullsize image.

        This is an alias for hasThumbnail().

        :returns: bool

    .. php:method:: getExtension()

        Get the original file's extension.

        :returns: string

    .. php:method:: setDefaults($filepath, $options = array())

        Set the default values that will be stored for this record in the 'files'
        table.

        :param $filepath:
        :param $options:

    .. php:method:: unlinkFile()

        Unlink the file and file derivatives belonging to this record.

    .. php:method:: _delete()

        Perform any further deletion when deleting this record.

    .. php:method:: createDerivatives()

        Create derivatives of the original file.

    .. php:method:: extractMetadata()

        Extract ID3 metadata associated with the file.

        :returns: bool Whether getID3 was able to read the file.

    .. php:method:: _getId3()

        Read the file's embedded metadata with the getID3 library.

        :returns: getID3|bool Returns getID3 object, or false if there was an exception.

    .. php:method:: storeFiles()

        Store the files belonging to this record.

    .. php:method:: getStoragePath($type = 'fullsize')

        Get a storage path for the file.

        :type $type: string
        :param $type:
        :returns: string

    .. php:method:: setStorage($storage)

        Set the storage object.

        :type $storage: Omeka_Storage
        :param $storage:

    .. php:method:: getStorage()

        Get the storage object.

        :returns: Omeka_Storage

    .. php:method:: getResourceId()

        Get the ACL resource ID for the record.

        File records are 'Files' resources.

        :returns: string

    .. php:method:: isOwnedBy($user)

        Return whether this file is owned by the given user.

        Proxies to the Item's isOwnedBy.

        :type $user: User
        :param $user:
        :returns: bool

    .. php:method:: getFile()

        Return the representative File for the record (this File itself).

        :returns: File
