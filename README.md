# fabric_cat_tools
This is a python library intended to be used in Microsoft Fabric notebooks. This library contains various functions for automating tasks related to semantic models and reports.

## Install the .whl file in a Fabric notebook
```python
%pip install "https://raw.githubusercontent.com/m-kovalsky/fabric_cat_tools/main/fabric_cat_tools-0.2.0-py3-none-any.whl"
```

## Once installed, run this code to import the library into your notebook
```python
import fabric_cat_tools as fct
```

# Function Categories

### Add/remove objects from semantic model
* [add_field_parameter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_field_parameter)
* [add_hierarchy](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_hierarchy)
* [add_measure](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_measure)
* [add_relationship](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_relationship)
* [add_rls](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_rls)
* [add_role](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_role)
* [remove_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_column)
* [remove_measure](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_measure)
* [remove_table](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_table)

### General semantic model
* [clear_cache](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clear_cache)
* [refresh_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#refresh_semantic_model)
* [report_rebind](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind)
* [report_rebind_all](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind_all)
* [get_measure_dependencies](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_measure_dependencies)
* [measure_dependency_tree](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#measure_dependency_tree)
* [get_semantic_model_bim](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_semantic_model_bim)
* [create_semantic_model_from_bim](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_semantic_model_from_bim)
* [create_report_from_reportjson](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_report_from_reportjson)

### Direct Lake Migration
* [create_pqt_file](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_pqt_file)
* [create_blank_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_blank_semantic_model)
* [migrate_tables_columns_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_tables_columns_to_semantic_model)
* [migrate_calc_tables_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_calc_tables_to_semantic_model)
* [migrate_model_objects_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_model_objects_to_semantic_model)
* [migrate_calc_tables_to_lakehouse](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_calc_tables_to_lakehouse)
* [refresh_calc_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#refresh_calc_tables)
* [direct_lake_schema_compare](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct_lake_schema_compare)
* [show_unsupported_direct_lake_objects](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#show_unsupported_direct_lake_objects)
* [update_direct_Lake_partition_entity](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#update_direct_Lake_partition_entity)
* [update_direct_lake_model_lakehouse_connection](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#update_direct_lake_model_lakehouse_connection)

### Direct Lake
* [check_fallback_reason](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#check_fallback_reason)
* [control_fallback](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#control_fallback)
* [get_direct_lake_lakehouse](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_direct_lake_lakehouse)
* [get_directlake_guardrails_for_sku](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_directlake_guardrails_for_sku)
* [get_direct_lake_guardrails](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_direct_lake_guardrails)
* [get_shared_expression](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_shared_expression)
* [get_sku_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_sku_size)
* [list_direct_lake_model_calc_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_direct_lake_model_calc_tables)

### Lakehouse
* [get_lakehouse_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_tables)
* [get_lakehouse_columns](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_columns)
* [get_lakehouse_details](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_details)

### Helper Functions
* [resolve_dataset_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_id)
* [resolve_dataset_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_name)
* [resolve_lakehouse_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_id)
* [resolve_lakehouse_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_name)
* [resolve_report_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_report_id)
* [resolve_report_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-files#resolve_report_name)

# Functions
## add_field_parameter
#### Adds a [field parameter](https://learn.microsoft.com/power-bi/create-reports/power-bi-field-parameters) to a semantic model.
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
### Returns
###### A printout stating the success/failure of the operation.

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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table in which the hierarchy will reside.
#### hierarchyName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the hierarchy.
#### levels [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Required; List of columns to be included as levels in the hierarchy.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table in which the measure will reside.
#### measureName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the measure.
#### measureExpression [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; DAX expression for the measure.
#### measureDisplayFolder [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Display folder for the measure.
#### measureFormatString [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Format string for the measure.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### fromTable [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table on the 'from' side of the relationship
#### toTable [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table on the 'to' side of the relationship
#### fromColumn [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the column on the 'from' side of the relationship
#### toColumn [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the column on the 'to' side of the relationship
#### fromCardinality [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Cardinality on the 'from' side of the relationship. Options: ('Many', 'One', None').
#### toCardinality [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Cardinality on the 'to' side of the relationship. Options: ('Many', 'One', None').
#### crossFilteringBehavior [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Setting for the cross filtering behavior of the relationship. Options: ('Automatic', 'OneDirection', 'BothDirections'). Default value: 'Automatic'.
#### securityFilteringBehavior [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Setting for the security filtering behavior of the relationship. Options: ('None', 'OneDirection', 'BothDirections'). Default value: 'OneDirection'.
#### isActive [bool](https://docs.python.org/3/library/functions.html#bool)
###### Optional; Setting for whether the relationship is active or not. Default value: True.
#### relyOnReferentialIntegrity [bool](https://docs.python.org/3/library/functions.html#bool)
###### Optional; Setting for the rely on referential integrity of the relationship. Default value: True.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### roleName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the role.
#### roleDescription [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Description of the role.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### roleName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the role to apply row level security.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table to apply row level security.
#### filterExpression [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; DAX expression for the row low level security.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
## check_fallback_reason
#### Shows the reason a table in a Direct Lake semantic model would fallback to Direct Query.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.check_fallback_reason(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### Pandas dataframe showing the tables in the semantic model and their fallback reason.

---
## clear_cache
#### Clears the cache of a semantic model.
```python
import fabric_cat_tools as fct
fct.clear_cache(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
## control_fallback
#### Set the DirectLakeBehavior for a semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.control_fallback(
            datasetName = 'AdventureWorks'
            ,directLakeBehavior = 'DirectLakeOnly'            
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### directLakeBehavior [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Setting for Direct Lake Behavior. Options: ('Automatic', 'DirectLakeOnly', 'DirectQueryOnly').
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### compatibilityLevel [int](https://docs.python.org/3/library/functions.html#int) 
###### Optional; Setting for the compatibility level of the semantic model. Default value: 1604.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
## create_pqt_file
#### Dynamically generates a [Power Query Template](https://learn.microsoft.com/power-query/power-query-template) file based on the semantic model. The .pqt file is saved within the Files section of your lakehouse.
```python
import fabric_cat_tools as fct
fct.create_pqt_file(
            datasetName = 'AdventureWorks'
            #,fileName = 'PowerQueryTemplate'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the import/DirectQuery semantic model.
#### fileName [str](https://docs.python.org/3/library/functions.html#str) 
###### Optional; TName of the Power Query Template (.pqt) file to be created.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### reportName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the report.
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model to connect to the report.
#### reportJson [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; The report.json file to be used to create the report.
#### themeJson [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; The theme.json file to be used for the theme of the report.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### bimFile [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; The model.bim file to be used to create the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
### Returns
###### A printout stating the success/failure of the operation.

---
## direct_lake_schema_compare
#### Checks that all the tables in a Direct Lake semantic model map to tables in their corresponding lakehouse and that the columns in each table exist.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.direct_lake_schema_compare(
            datasetName = 'AdventureWorks'
            ,workspaceName = ''
            #,lakehouseName = ''
            #,lakehouseWorkspaceName = ''
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The lakehouse used by the Direct Lake semantic model.
#### lakehouseWorkspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace in which the lakehouse resides.

---
## get_direct_lake_guardrails
#### Shows the guardrails for when Direct Lake semantic models will fallback to Direct Query based on Microsoft's online documentation.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_guardrails()
```
### Parameters
None

---
## get_directlake_guardrails_for_sku
#### Shows the guardrails for Direct Lake based on the SKU used by your workspace's capacity.
*Use the result of the 'get_sku_size' function as an input for this function's skuSize parameter.*
```python
import fabric_cat_tools as fct
fct.get_directlake_guardrails_for_sku(
            skuSize = ''
            )
```
### Parameters
#### skuSize [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Sku size of a workspace/capacity

---
## get_lakehouse_columns
#### Shows the tables and columns of a lakehouse and their respective properties.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_columns(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The lakehouse name.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.
---
## get_lakehouse_details
#### Shows the properties associated with a lakehouse.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_details(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The lakehouse name.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## get_lakehouse_tables
#### Shows the tables of a lakehouse and their respective properties.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_tables(
            lakehouseName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The lakehouse name.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## get_measure_dependencies
#### Shows all dependencies for all measures in a semantic model
```python
import fabric_cat_tools as fct
fct.get_measure_dependencies(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## get_semantic_model_bim
#### Extracts the Model.bim file for a given semantic model.
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## get_shared_expression
#### Dynamically generates the M expression used by a Direct Lake model for a given lakehouse.
```python
import fabric_cat_tools as fct
fct.get_shared_expression(
            lakehouseName = ''
            #,workspaceName = '' 
            )
```
### Parameters
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The lakehouse name.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## get_sku_size
#### Shows the SKU size for a workspace.
```python
import fabric_cat_tools as fct
fct.get_sku_size(
            workspaceName = '' 
            )
```
### Parameters
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## list_direct_lake_model_calc_tables
#### Shows the calculated tables and their respective DAX expression for a Direct Lake model (which has been migrated from import/DirectQuery.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### measureName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the measure to use for building a dependency tree.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## migrate_calc_tables_to_lakehouse
#### Creates delta tables in your lakehouse based on the DAX expression of a calculated table in an import/DirectQuery semantic model. The DAX expression encapsulating the calculated table logic is stored in the new Direct Lake semantic model as model annotations.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_lakehouse(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the import/DirectQuery semantic model.
#### newDatasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the Direct Lake semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## migrate_calc_tables_to_semantic_model
#### Creates new tables in the Direct Lake semantic model based on the lakehouse tables created using the 'migrate_calc_tables_to_lakehouse' function.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the import/DirectQuery semantic model.
#### newDatasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the Direct Lake semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## migrate_model_objects_to_semantic_model
#### Adds the rest of the model objects (besides tables/columns) and their properties to a Direct Lake semantic model based on an import/DirectQuery semantic model.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_model_objects_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the import/DirectQuery semantic model.
#### newDatasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the Direct Lake semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## migrate_tables_columns_to_semantic_model
#### Adds tables/columns to the new Direct Lake semantic model based on an import/DirectQuery semantic model.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_tables_columns_to_semantic_model(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the import/DirectQuery semantic model.
#### newDatasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the Direct Lake semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## refresh_calc_tables
#### Recreates the delta tables in the lakehouse based on the DAX expressions stored as model annotations in the Direct Lake semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.refresh_calc_tables(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### refreshType [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Type of processing to perform. Options: ('full', 'automatic', 'dataOnly', 'calculate', 'clearValues', 'defragment'). Default value: 'full'.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the column's table(s).
#### columnName [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the column(s).
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### measureName [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the measure(s).
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table(s).
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
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
### Parameters
#### reportName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the report.
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model to rebind to the report.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model and report reside.

---
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model currently binded to the reports.
#### newDatasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model to rebind to the reports.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic models and reports reside.
---
## resolve_lakehouse_name
#### Returns the name of the lakehouse for a given lakehouse Id.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_name(
        lakehouseId = ''
        #,workspaceName = '' 
        )
```
### Parameters
#### lakehouseId [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
###### Required; UUID object representing a lakehouse.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## resolve_lakehouse_id
#### Returns the ID of a given lakehouse.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_id(
        lakehouseName = 'MyLakehouse'
        #,workspaceName = '' 
        )
```
### Parameters
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Required; Name of the lakehouse.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## resolve_dataset_id
#### Returns the ID of a given semantic model.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_id(
        datasetName = 'MyReport'
        #,workspaceName = '' 
        )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
---
## resolve_dataset_name
#### Returns the name of a given semantic model ID.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_name(
        datasetId = ''
        #,workspaceName = '' 
        )
```
### Parameters
#### datasetId [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
###### Required; UUID object representing a semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## resolve_report_id
#### Returns the ID of a given report.
```python
import fabric_cat_tools as fct
fct.resolve_report_id(
        reportName = 'MyReport'
        #,workspaceName = '' 
        )
```
### Parameters
#### reportName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Required; Name of the report.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the report resides.

---
## resolve_report_name
#### Returns the name of a given report ID.
```python
import fabric_cat_tools as fct
fct.resolve_report_name(
        reportId = ''
        #,workspaceName = '' 
        )
```
### Parameters
#### reportId [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
###### Required; UUID object representing a report.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the report resides.

---
## show_unsupported_direct_lake_objects
#### Returns a list of a semantic model's objects which are not supported by Direct Lake based on [official documentation](https://learn.microsoft.com/power-bi/enterprise/directlake-overview#known-issues-and-limitations).
```python
import fabric_cat_tools as fct
fct.show_unsupported_direct_lake_objects(
        datasetName = 'AdventureWorks'
        #,workspaceName = '' 
        )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.

---
## update_direct_lake_model_lakehouse_connection
#### Remaps a Direct Lake semantic model's SQL Endpoint connection to a new lakehouse.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_model_lakehouse_connection(
            datasetName = ''
            #,lakehouseName = ''
            #,workspaceName = ''
            )
```
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Name of the lakehouse.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
#### lakehouseWorkspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.

---
## update_direct_lake_partition_entity
#### Remaps a table (or tables) in a Direct Lake semantic model to a table in a lakehouse.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
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
### Parameters
#### datasetName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the semantic model.
#### tableName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the table in the semantic model.
#### entityName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Required; Name of the lakehouse table to be mapped to the semantic model table.
#### workspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the semantic model resides.
#### lakehouseName [str](https://docs.python.org/3/library/stdtypes.html#str) 
###### Optional; Name of the lakehouse.
#### lakehouseWorkspaceName [str](https://docs.python.org/3/library/stdtypes.html#str)
###### Optional; The workspace where the lakehouse resides.



