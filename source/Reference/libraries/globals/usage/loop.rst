Usually, the ``$recordsVar`` parameter is a string name of the model whose records have already been set in the view by the controller.

This will be the name of the table, i.e., the pluralized, underscored name of the model. For example, a CamelCase model name like "CsvImport_Import" should be "csv_import_imports". 

The string will be converted to the table name. Thus, ``csv_import_imports`` and ``CsvImport_Import`` have exactly the same effect (provided the same convention was used in setting the records to loop in the view).

