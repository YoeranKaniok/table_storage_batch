Microsoft Azure CosmosDB Table SDK for Python with batching functionality
=========================================================================

This project provides a wrapper for the Azure cosmosdb TableService. 
For documentation on this package please see the `Microsoft Azure CosmosDB Table SDK for Python`_ page.

Features
========

-  Table

   -  Automatically split lists of entities into batches based on PartitionKey
   -  Automatically chunk entities into sub-lists for correct batch sizes
   -  Batch Insert Entities
   -  Batch Update Entities
   -  Batch Merge Entities
   -  Batch Delete Entities
   -  Batch Insert or Replace Entities
   -  Batch Insert or Merge Entities
   
Getting Started
===============

To install via the Python Package Index (PyPI), type:


    pip install batch-table-storage
    
Minimum Requirements
--------------------

-  azure-cosmosdb-table==1.0.6


Code Sample
-----------

Import the wrapper class

    from batch_table_service import BatchTableService

Instantiate the service
 
    service = BatchTableService(account_name='storageAccount', account_key='x')
  
Create some entities
  
    entities = [
        {'PartitionKey': 'person', 'RowKey': '1', 'name': 'John'},
        {'PartitionKey': 'pet', 'RowKey': '1', 'name': 'Cat'}
    ]

Create and commit the batches:
   
    service.batch_insert_entities(table_name='tableA', entities=entities)


Learn More
==========
.. _Microsoft Azure CosmosDB Table SDK for Python: https://pypi.org/project/azure-cosmosdb-table/