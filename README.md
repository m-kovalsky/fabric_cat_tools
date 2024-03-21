# fabric_cat_tools

## Install the .whl file in a Fabric notebook
```python
%pip install "https://raw.githubusercontent.com/m-kovalsky/fabric_cat_tools/main/fabric_cat_tools-0.2.0-py3-none-any.whl"
```

# Functions
## add_field_parameter
#### Adds a field parameter to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_field_parameter(
            datasetName = 'AdventureWorks'
            ,tableName = 'Parameter'
            ,objects = ["[Sales Amount]", "[Order Qty]", "'Internet Sales'[Color]"]
            #,workspaceName = '' 
            )
```

### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the field parameter table.
#### objects [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Required; List of columns/measures to be included in the field parameter. Columns are fully qualified 'TableName'[ColumnName] and measures are in square brackets [MeasureName].
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## add_hierarchy
#### Adds a hierarchy to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_hierarchy(
            datasetName = 'AdventureWorks'
            ,tableName = 'Geography'
            ,hierarchyName = 'Geography Hierarchy'
            ,levels = ['Continent', 'Country', 'City']
            #,workspaceName = '' 
            )
```

## add_measure
#### Adds a measure to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_measure(
        datasetName = 'AdventureWorks'
        ,tableName = 'Internet Sales'
        ,measureName = 'Sales Amount'
        ,measureExpression =  "SUM( 'Internet Sales'[SalesAmount] )"
        #,measureDisplayFolder = ''
        #,measureFormatString = ''
        #,workspaceName = '' 
        )
```

## add_relationship
#### Adds a relationship to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_relationship(
            datasetName = 'AdventureWorks'
            ,fromTable = 'Internet Sales'
            ,fromColumn = 'ProductKey'
            ,toTable = 'Product'
            ,toColumn = 'ProductKey'
            ,fromCardinality = 'Many'
            ,toCardinality = 'One'
            #,workspaceName = '' 
            )
```

## add_role
#### Adds a role to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_role(
            datasetName = 'AdventureWorks'
            ,roleName = 'Reader'
            ,roleDescription = 'This role is for...'
            #,workspaceName = '' 
            )
```

## add_rls
#### Adds row level security to a table within a role to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_rls(
            datasetName = 'AdventureWorks'
            ,roleName = 'Reader'
            ,tableName = 'UserGeography'
            ,filterExpression = "'UserGeography'[UserEmail] = USERPRINCIPALNAME()"
            #,workspaceName = '' 
            )
```


## check_fallback_reason
#### Shows the reason a table in a Direct Lake semantic model would fallback to Direct Query.
```python
import fabric_cat_tools as fct
fct.check_fallback_reason(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## clear_cache
#### Clears the cache of a semantic model.
```python
import fabric_cat_tools as fct
fct.clear_cache(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## control_fallback
#### Set the DirectLakeBehavior for a semantic model.
```python
import fabric_cat_tools as fct
fct.control_fallback(
            datasetName = 'AdventureWorks'
            ,directLakeBehavior = 'DirectLakeOnly'            
            #,workspaceName = '' 
            )
```

## create_blank_semantic_model
#### Creates a new blank semantic model (no tables/columns etc.).
```python
import fabric_cat_tools as fct
fct.create_blank_semantic_model(
            datasetName = 'AdventureWorks'
            #,compatibilityLevel = 1604
            #,workspaceName = '' 
            )
```

## create_pqt_file
#### Dynamically generates a Power Query Template file based on the semantic model. The .pqt file is saved within the Files section of your lakehoues.
```python
import fabric_cat_tools as fct
fct.create_pqt_file(
            datasetName = 'AdventureWorks'
            #,fileName = 'PowerQueryTemplate'
            #,workspaceName = '' 
            )
```

## create_report_from_reportjson
#### Creates a report based on a report.json file (and an optional themes.json file).
```python
import fabric_cat_tools as fct
fct.create_report_from_reportjson(
            reportName = 'MyReport'
            ,datasetName = 'AdventureWorks'
            ,reportJson = ''
            #,themeJson = ''
            #,workspaceName = ''
            )
```

## create_semantic_model_from_bim
#### Creates a new semantic model based on a Model.bim file.
```python
import fabric_cat_tools as fct
fct.create_semantic_model_from_bim(
            datasetName = 'AdventureWorks'
            ,bimFile = ''
            #,workspaceName = ''
            )
```

## direct_lake_schema_compare
#### Checks that all the tables in a Direct Lake semantic model map to tables in their corresponding lakehouse and that the columns in each table exist.
```python
import fabric_cat_tools as fct
fct.direct_lake_schema_compare(
            datasetName = 'AdventureWorks'
            ,workspaceName = ''
            #,lakehouseName = ''
            #,lakehouseWorkspaceName = ''
            )
```

## get_direct_lake_guardrails
#### Shows the guardrails for when Direct Lake semantic models will fallback to Direct Query based on Microsoft's online documentation.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_guardrails()
```

## get_directlake_guardrails_for_sku
#### Shows the guardrails for Direct Lake based on the SKU used by your workspace's capacity.
*Use the result of the 'get_sku_size' function as an input for this function's skuSize parameter.*
```python
import fabric_cat_tools as fct
fct.get_directlake_guardrails_for_sku(
            skuSize = ''
            )
```

## get_lakehouse_columns
#### Shows the tables and columns of a lakehouse and their respective properties.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_columns(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## get_lakehouse_details
#### Shows the properties associated with a lakehouse.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_details(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

#### Shows the tables of a lakehouse and their respective properties.
## get_lakehouse_tables
```python
import fabric_cat_tools as fct
fct.get_lakehouse_tables(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## get_measure_dependencies
#### Shows all dependencies for all measures in a semantic model
```python
import fabric_cat_tools as fct
fct.get_measure_dependencies(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## get_semantic_model_bim
#### Extracts the Model.bim file for a given semantic model.
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## get_shared_expression
#### Dynamically generates the M expression used by a Direct Lake model for a given lakehouse.
```python
import fabric_cat_tools as fct
fct.get_shared_expression(
            lakehouseName = ''
            #,workspaceName = '' 
            )
```

## get_sku_size
#### Shows the SKU size for a workspace.
```python
import fabric_cat_tools as fct
fct.get_sku_size(
            workspaceName = '' 
            )
```

## list_direct_lake_model_calc_tables
#### Shows the calculated tables and their respective DAX expression for a Direct Lake model (which has been migrated from import/DirectQuery.
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## measure_dependency_tree
#### Shows a measure dependency tree of all dependent objects for a measure in a semantic model.
```python
import fabric_cat_tools as fct
fct.measure_dependency_tree(
            datasetName = 'AdventureWorks'
            ,measureName = 'Sales Amount'
            #,workspaceName = '' 
            )
```

## migrate_calc_tables_to_lakehouse
#### Creates delta tables in your lakehouse based on the DAX expression of a calculated table in an import/DirectQuery semantic model. The DAX expression encapsulating the calculated table logic is stored in the new Direct Lake semantic model as model annotations.
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_lakehouse(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```

## migrate_calc_tables_to_semantic_model
#### Creates new tables in the Direct Lake semantic model based on the lakehouse tables created using the 'migrate_calc_tables_to_lakehouse' function.
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```

## migrate_model_objects_to_semantic_model
#### Adds the rest of the model objects (besides tables/columns) and their properties to a Direct Lake semantic model based on an import/DirectQuery semantic model.
```python
import fabric_cat_tools as fct
fct.migrate_model_objects_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```

## migrate_tables_columns_to_semantic_model
#### Adds tables/columns to the new Direct Lake semantic model based on an import/DirectQuery semantic model.
```python
import fabric_cat_tools as fct
fct.migrate_tables_columns_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```

## refresh_calc_tables
#### Recreates the delta tables in the lakehouse based on the DAX expressions stored as model annotations in the Direct Lake semantic model.
```python
import fabric_cat_tools as fct
fct.refresh_calc_tables(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```

## refresh_semantic_model
#### Performs a refresh on a semantic model.
```python
import fabric_cat_tools as fct
fct.refresh_semantic_model(
            datasetName = 'AdventureWorks'
            ,refreshType = 'full'
            #,workspaceName = '' 
            )
```

## remove_column
#### Removes a column (or multiple columns) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_column(
            datasetName = 'AdventureWorks'
            ,tableName = ['Internet Sales', 'Geography']
            ,columnName = ['SalesAmount', 'GeographyKey']
            #,workspaceName = '' 
            )
```

## remove_measure
#### Removes a measure (or multiple measures) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_measure(
            datasetName = 'AdventureWorks'
            ,measureName = ['Sales Amount', 'Order Quantity']
            #,workspaceName = '' 
            )
```

## remove_table
#### Removes a table (or multiple tables) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_table(
            datasetName = 'AdventureWorks'
            ,tableName = ['Internet Sales', 'Geography']
            #,workspaceName = '' 
            )
```

## report_rebind
#### Rebinds a report to a semantic model.
```python
import fabric_cat_tools as fct
fct.report_rebind(
            reportName = ''
            ,datasetName = ''
            #,workspaceName = '' 
            )
```

## report_rebind_all
#### Rebinds all reports in a workspace which are bound to a specific semantic model to a new semantic model.
```python
import fabric_cat_tools as fct
fct.report_rebind_all(
            datasetName = ''
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```

## resolve_lakehouse_name
#### Returns the name of the lakehouse for a given lakehouse Id.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_name(
        lakehouseId = ''
        #,workspaceName = '' 
        )
```

## resolve_lakehouse_id
#### Returns the ID of a given lakehouse.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_id(
        lakehouseName = 'MyLakehouse'
        #,workspaceName = '' 
        )
```

## resolve_dataset_id
#### Returns the ID of a given semantic model.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_id(
        datasetName = 'MyReport'
        #,workspaceName = '' 
        )
```

## resolve_dataset_name
#### Returns the name of a given semantic model ID.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_name(
        datasetId = ''
        #,workspaceName = '' 
        )
```

## resolve_report_id
#### Returns the ID of a given report.
```python
import fabric_cat_tools as fct
fct.resolve_report_id(
        reportName = 'MyReport'
        #,workspaceName = '' 
        )
```

## resolve_report_name
#### Returns the name of a given report ID.
```python
import fabric_cat_tools as fct
fct.resolve_report_name(
        reportId = ''
        #,workspaceName = '' 
        )
```

## show_unsupported_direct_lake_objects
#### Returns a list of a semantic model's objects which are not supported by Direct Lake
```python
import fabric_cat_tools as fct
fct.show_unsupported_direct_lake_objects(
        datasetName = 'AdventureWorks'
        #,workspaceName = '' 
        )
```

## update_direct_lake_model_lakehouse_connection
#### Remaps a Direct Lake semantic model's SQL Endpoint connection to a new lakehouse.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_model_lakehouse_connection(
            datasetName = ''
            #,lakehouseName = ''
            #,workspaceName = '' 
            )
```

## update_direct_lake_partition_entity
#### Remaps a table (or tables) in a Direct Lake semantic model to a table in a lakehouse.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_partition_entity(
            datasetName = 'AdventureWorks'
            ,tableName = 'Internet Sales'
            ,entityName = 'FACT_InternetSales'
            #,workspaceName = ''
            #,lakehouseName = ''
            #,lakehouseWorkspaceName = ''            
            )
```
