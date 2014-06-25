---------------------
Omeka_Record_Iterator
---------------------

Package: :doc:`Record </Reference/packages/Record/index>`

.. php:class:: Omeka_Record_Iterator

implements :php:interface:`Iterator`
implements :php:interface:`Traversable`

    .. php:attr:: _records

        protected

    .. php:attr:: _view

        protected

    .. php:attr:: _currentRecordVar

        protected

    .. php:method:: __construct($records, $view = null, $currentRecordVar = null)

        Construct the record iterator.

        :type $records: array
        :param $records:
        :type $view: null|Zend_View_Abstract
        :param $view:
        :type $currentRecordVar: null|string
        :param $currentRecordVar:

    .. php:method:: rewind()

    .. php:method:: current()

        Return the current record, setting it to the view if applicable.

    .. php:method:: key()

    .. php:method:: next()

        Release the previous record and advance the pointer to the next one.

    .. php:method:: valid()
