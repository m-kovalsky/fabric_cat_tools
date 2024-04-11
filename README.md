# fabric_cat_tools
This is a python library intended to be used in [Microsoft Fabric notebooks](https://learn.microsoft.com/fabric/data-engineering/how-to-use-notebook). This library was originally intended to contain functions used for [migrating semantic models to Direct Lake mode](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1). However, it quickly became apparent that functions within such a library could support many other useful activities in the realm of semantic models, reports, lakehouses and really anything Fabric-related. As such, this library contains a variety of functions ranging from running [Vertipaq Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analyzer) or the [Best Practice Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) against a semantic model to seeing if any [lakehouse tables hit Direct Lake guardrails](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_tables) and more.

Instructions for migrating import/DirectQuery semantic models to Direct Lake mode can be found [here](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1).

If you encounter any issues, please [raise a bug](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=bug_report.md&title=).

If you have ideas for new features/functions, please [request a feature](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=feature_request.md&title=).

## Click [here](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#version-history) to see a version history



## Install the .whl file in a Fabric notebook
```python
%pip install "https://raw.githubusercontent.com/m-kovalsky/fabric_cat_tools/main/fabric_cat_tools-0.2.5-py3-none-any.whl"
```

## Once installed, run this code to import the library into your notebook
```python
import fabric_cat_tools as fct
```

## Load fabric_cat_tools into a custom [Fabric environment](https://learn.microsoft.com/fabric/data-engineering/create-and-use-environment)
An even better way to ensure the fabric_cat_tools library is available in your workspace/notebooks is to load it as a library in a custom Fabric environment. If you do this, you will not have to run the above '%pip install' code every time in your notebook. Please follow the steps below.

#### Create a custom environment
1. Navigate to your Fabric workspace
2. Click 'New' -> More options
3. Within 'Data Science', click 'Environment'
4. Name your environment, click 'Create'

#### Add fabric_cat_tools as a library to the environment
1. Download the [latest](https://github.com/m-kovalsky/fabric_cat_tools/raw/main/fabric_cat_tools-0.2.5-py3-none-any.whl) fabric_cat_tools library
2. Within 'Custom Libraries', click 'upload'
3. Upload the .whl file which was downloaded in step 1
4. Click 'Save' at the top right of the screen
5. Click 'Publish' at the top right of the screen
6. Click 'Publish All'

#### Update your notebook to use the new environment (*must wait for the environment to finish publishing*)
1. Navigate to your Notebook
2. Select your newly created environment within the 'Environment' drop down in the navigation bar at the top of the notebook

# Function Categories

### Semantic Model
* [clear_cache](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clear_cache)
* [create_semantic_model_from_bim](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_semantic_model_from_bim)
* [get_semantic_model_bim](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_semantic_model_bim)
* [get_measure_dependencies](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_measure_dependencies)
* [measure_dependency_tree](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#measure_dependency_tree)
* [refresh_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#refresh_semantic_model)


### Report
* [report_rebind](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind)
* [report_rebind_all](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind_all)
* [create_report_from_reportjson](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_report_from_reportjson)
* [get_report_json](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_report_json)
* [export_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_report)
* [clone_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clone_report)
* [list_dashboards](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_dashboards)

### Model Optimization
* [vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analyzer)
* [import_vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#import_vertipaq_analyzer)
* [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa)

### Direct Lake Migration
* [create_pqt_file](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_pqt_file)
* [create_blank_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_blank_semantic_model)
* [migrate_field_parameters](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_field_parameters)
* [migrate_tables_columns_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_tables_columns_to_semantic_model)
* [migrate_calc_tables_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_calc_tables_to_semantic_model)
* [migrate_model_objects_to_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_model_objects_to_semantic_model)
* [migrate_calc_tables_to_lakehouse](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_calc_tables_to_lakehouse)
* [refresh_calc_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#refresh_calc_tables)
* [show_unsupported_direct_lake_objects](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#show_unsupported_direct_lake_objects)
* [update_direct_lake_partition_entity](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#update_direct_lake_partition_entity)
* [update_direct_lake_model_lakehouse_connection](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#update_direct_lake_model_lakehouse_connection)

### Direct Lake
* [check_fallback_reason](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#check_fallback_reason)
* [control_fallback](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#control_fallback)
* [direct_lake_schema_compare](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct_lake_schema_compare)
* [direct_lake_schema_sync](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct_lake_schema_sync)
* [get_direct_lake_lakehouse](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_direct_lake_lakehouse)
* [get_directlake_guardrails_for_sku](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_directlake_guardrails_for_sku)
* [get_direct_lake_guardrails](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_direct_lake_guardrails)
* [get_shared_expression](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_shared_expression)
* [get_direct_lake_sql_endpoint](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_direct_lake_sql_endpoint)
* [get_sku_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_sku_size)
* [list_direct_lake_model_calc_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_direct_lake_model_calc_tables)
* [warm_direct_lake_cache_perspective](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#warm_direct_lake_cache_perspective)
* [warm_direct_lake_cache_isresident](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#warm_direct_lake_cache_isresident)

### Lakehouse
* [get_lakehouse_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_tables)
* [get_lakehouse_columns](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_columns)
* [get_lakehouse_details](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_details)
* [export_model_to_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_model_to_onelake)
* [create_shortcut_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_shortcut_onelake)
* [delete_shortcut](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#delete_shortcut)
* [list_shortcuts](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_shortcuts)

### Add/remove objects from a semantic model
* [add_data_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_data_column)
* [add_field_parameter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_field_parameter)
* [add_hierarchy](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_hierarchy)
* [add_measure](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_measure)
* [add_relationship](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_relationship)
* [add_rls](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_rls)
* [add_role](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_role)
* [remove_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_column)
* [remove_measure](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_measure)
* [remove_table](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_table)

### Helper Functions
* [resolve_dataset_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_id)
* [resolve_dataset_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_name)
* [resolve_lakehouse_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_id)
* [resolve_lakehouse_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_name)
* [resolve_report_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_report_id)
* [resolve_report_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-files#resolve_report_name)

# Functions
## add_data_column
#### Adds a data column to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_data_column(
        datasetName = 'AdventureWorks'
        ,tableName = 'Internet Sales'
        ,columnName = 'SalesAmount'
        ,sourceColumn = 'SalesAmount'
        ,dataType =  'Int64'
        #,formatString = ''
        #,displayFolder = ''
        #,workspaceName = '' 
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the semantic model.
> 
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the table in which the column will reside.
>
> **columnName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the column.
>
> **sourceColumn** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the column in the source system.
>
> **dataType** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Data type of the column. Options: 'Int64', 'String', 'Double', 'Decimal', 'DateTime', 'Boolean'.
>
> **formatString** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Format string of the column.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Description of the column.
>
> **displayFolder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Display folder of the column.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The workspace where the semantic model resides.
>
### Returns
> A printout stating the success/failure of the operation.

---
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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the semantic model.
> 
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the field parameter table.
>
> **objects** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; List of columns/measures to be included in the field parameter. Columns are fully qualified 'TableName'[ColumnName] and measures are in square brackets [MeasureName].
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The workspace where the semantic model resides.
>
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the semantic model.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the table in which the hierarchy will reside.
>
> **hierarchyName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the hierarchy.
>
> **levels** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; List of columns to be included as levels in the hierarchy.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## add_measure
#### Adds a measure to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_measure(
        datasetName = 'AdventureWorks'
        ,tableName = 'Internet Sales'
        ,measureName = 'Sales Amount'
        ,expression =  "SUM( 'Internet Sales'[SalesAmount] )"
        #,displayFolder = ''
        #,formatString = ''
        #,workspaceName = '' 
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table in which the measure will reside.
>
> **measureName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; DAX expression for the measure.
>
> **displayFolder** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Display folder for the measure.
>
> **formatString** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Format string for the measure.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **fromTable** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table on the 'from' side of the relationship
>
> **toTable** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table on the 'to' side of the relationship
>
> **fromColumn** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column on the 'from' side of the relationship
>
> **toColumn** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column on the 'to' side of the relationship
>
> **fromCardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Cardinality on the 'from' side of the relationship. Options: ('Many', 'One', None').
>
> **toCardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Cardinality on the 'to' side of the relationship. Options: ('Many', 'One', None').
>
> **crossFilteringBehavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Setting for the cross filtering behavior of the relationship. Options: ('Automatic', 'OneDirection', 'BothDirections'). Default value: 'Automatic'.
>
> **securityFilteringBehavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Setting for the security filtering behavior of the relationship. Options: ('None', 'OneDirection', 'BothDirections'). Default value: 'OneDirection'.
>
> **isActive** [bool](https://docs.python.org/3/library/functions.html#bool)
> 
>> Optional; Setting for whether the relationship is active or not. Default value: True.
>
> **relyOnReferentialIntegrity** [bool](https://docs.python.org/3/library/functions.html#bool)
> 
>> Optional; Setting for the rely on referential integrity of the relationship. Default value: True.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **roleName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the role.
>
> **roleDescription** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Description of the role.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **roleName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the role to apply row level security.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table to apply row level security.
>
> **filterExpression** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; DAX expression for the row low level security.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> Pandas dataframe showing the tables in the semantic model and their fallback reason.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## clone_report
#### Makes a clone of a Power BI report
```python
import fabric_cat_tools as fct
fct.clone_report(
            reportName = 'MyReport'
            ,clonedReportName = 'MyNewReport'
            #,workspaceName = None
            #,targetWorkspace = None
            #,targetDatasetName = None
            )
```
### Parameters
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report to be cloned.
>
> **clonedReportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the new report.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the original report resides.
>
> **targetWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the new report will reside. Defaults to using the workspace in which the original report resides.
>
> **targetDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The semantic model from which the new report will be connected. Defaults to using the semantic model used by the original report.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **directLakeBehavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Setting for Direct Lake Behavior. Options: ('Automatic', 'DirectLakeOnly', 'DirectQueryOnly').
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **compatibilityLevel** [int](https://docs.python.org/3/library/functions.html#int)
> 
>> Optional; Setting for the compatibility level of the semantic model. Default value: 1604.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **fileName** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Optional; TName of the Power Query Template (.pqt) file to be created.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to connect to the report.
>
> **reportJson** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The report.json file to be used to create the report.
> 
> **themeJson** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The theme.json file to be used for the theme of the report.
> 
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **bimFile** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The model.bim file to be used to create the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## create_shortcut_onelake
#### Creates a [shortcut](https://learn.microsoft.com/fabric/onelake/onelake-shortcuts) to a delta table in OneLake.
```python
import fabric_cat_tools as fct
fct.create_shortcut_onelake(
            tableName = 'DimCalendar'
            ,sourceLakehouseName = 'Lakehouse1'
            ,sourceWorkspaceName = 'Workspace1'
            ,destinationLakehouseName = 'Lakehouse2'
            #,destinationWorkspaceName = ''
            ,shortcutName = 'Calendar'
            )
```
### Parameters
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The table name for which a shortcut will be created.
>
> **sourceLakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The lakehouse in which the table resides.
>
> **sourceWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The workspace where the source lakehouse resides.
>
> **destinationLakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The lakehouse where the shortcut will be created.
>
> **destinationWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the shortcut will be created. Defaults to the 'sourceWorkspaceName' parameter value.
>
> **shortcutName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name of the shortcut 'table' to be created. This defaults to the 'tableName' parameter value.

---
## delete_shortcut
#### Deletes a [OneLake shortcut](https://learn.microsoft.com/fabric/onelake/onelake-shortcuts).
```python
import fabric_cat_tools as fct
fct.delete_shortcut(
            shortcutName = 'DimCalendar'
            ,lakehouseName = 'Lakehouse1'
            ,workspaceName = 'Workspace1'
            )
```
### Parameters
> **shortcutName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The name of the OneLake shortcut to delete.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse in which the shortcut resides.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse used by the Direct Lake semantic model.
>
> **lakehouseWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.

---
## direct_lake_schema_sync
#### Shows/adds columns which exist in the lakehouse but do not exist in the semantic model (only for tables in the semantic model).
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.direct_lake_schema_sync(
     datasetName = 'AdvWorks'
    ,addToModel = True
    #,workspaceName = ''
    #,lakehouseName = ''
    #,lakehouseWorkspaceName = ''
    )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **addToModel** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds columns which exist in the lakehouse but do not exist in the semantic model. No new tables are added. Default value: False.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse used by the Direct Lake semantic model.
>
> **lakehouseWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.

---
## export_model_to_onelake
#### Exports a semantic model's tables to delta tables in the lakehouse. Creates shortcuts to the tables if a lakehouse is specified.
> [!IMPORTANT]
> This function requires:
> 
> [XMLA read/write](https://learn.microsoft.com/power-bi/enterprise/service-premium-connect-tools#enable-xmla-read-write) to be enabled on the Fabric capacity.
> 
> [OneLake Integration](https://learn.microsoft.com/power-bi/enterprise/onelake-integration-overview#enable-onelake-integration) feature to be enabled within the semantic model settings.
```python
import fabric_cat_tools as fct
fct.export_model_to_onelake(
            datasetName = 'AdventureWorks'
            ,workspaceName = None
            ,destinationLakehouseName = 'Lakehouse2'            
            ,destinationWorkspaceName = 'Workspace2'
            )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **destinationLakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse where shortcuts will be created to access the delta tables created by the export. If the lakehouse specified does not exist, one will be created with that name. If no lakehouse is specified, shortcuts will not be created.
>
> **destinationWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.

---
## export_report
#### Exports a Power BI report to a file in your lakehouse.
```python
import fabric_cat_tools as fct
fct.export_report(
            reportName = 'AdventureWorks'
            ,exportFormat = 'PDF'
            #,fileName = None
            #,bookmarkName = None
            #,pageName = None
            #,visualName = None
            #,workspaceName = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            reportName = 'AdventureWorks'
            ,exportFormat = 'PDF'
            #,fileName = 'Exports\MyReport'
            #,bookmarkName = None
            #,pageName = 'ReportSection293847182375'
            #,visualName = None
            #,workspaceName = None
            )
```
### Parameters
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **exportFormat** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The format in which to export the report. See this link for valid formats: https://learn.microsoft.com/rest/api/power-bi/reports/export-to-file-in-group#fileformat. For image formats, enter the file extension in this parameter, not 'IMAGE'.
>
> **fileName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name of the file to be saved within the lakehouse. Do **not** include the file extension. Defaults ot the reportName parameter value.
>
> **bookmarkName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of a bookmark within the report.
>
> **pageName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of the report page.
>
> **visualName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of a visual. If you specify this parameter you must also specify the pageName parameter.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.

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
> **skuSize** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Sku size of a workspace/capacity

---
## get_direct_lake_lakehouse
#### Identifies the lakehouse used by a Direct Lake semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_lakehouse(
            datasetName = 'AdventureWorks'
            #,workspaceName = ''
            #,lakehouseName = ''
            #,lakehouseWorkspaceName = ''            
            )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse used by the semantic model.
>
> **lakehouseWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

---
## get_direct_lake_sql_endpoint
#### Identifies the lakehouse used by a Direct Lake semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_sql_endpoint(
            datasetName = 'AdventureWorks'
            #,workspaceName = ''       
            )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
---
## get_lakehouse_details
#### Shows the properties associated with a lakehouse.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_details(
            lakehouseName = 'MyLakehouse'
            #,workspaceName = '' 
            )
```
### Parameters
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

---
## get_lakehouse_tables
#### Shows the tables of a lakehouse and their respective properties. Option to include additional properties relevant to Direct Lake guardrails.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_tables(
        lakehouseName = 'MyLakehouse'
        #,workspaceName = ''
        ,extended = True
        ,countRows = True)
```
### Parameters
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
>
> **extended** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds the following additional table properties \['Files', 'Row Groups', 'Table Size', 'Parquet File Guardrail', 'Row Group Guardrail', 'Row Count Guardrail'\]. Also indicates the SKU for the workspace and whether guardrails are hit. Default value: False.
>
> **countRows** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds an additional column showing the row count of each table. Default value: False.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

---
## get_report_json
#### Gets the report.json file content of a Power BI report
```python
import fabric_cat_tools as fct
fct.get_report_json(
            reportName = 'MyReport'
            #,workspaceName = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_report_json(
            reportName = 'MyReport'
            #,workspaceName = None
            ,saveToFileName = 'MyFileName'
            )
```
### Parameters
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
>
> **saveToFileName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying this parameter will save the report.json file to your lakehouse with the file name of this parameter.

---
## get_semantic_model_bim
#### Extracts the Model.bim file for a given semantic model.
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            datasetName = 'AdventureWorks'
            #,workspaceName = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            datasetName = 'AdventureWorks'
            #,workspaceName = None
            ,saveToFileName = 'MyFileName'
            )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **saveToFileName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying this parameter will save the model.bim file to your lakehouse with the file name of this parameter.

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
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

---
## import_vertipaq_analyzer
#### Imports and visualizes the vertipaq analyzer info from a saved .zip file in your lakehouse.
```python
import fabric_cat_tools as fct
fct.import_vertipaq_analyzer(
          folderPath = '/lakehouse/default/Files/VertipaqAnalyzer'
          ,fileName = 'Workspace Name-DatasetName.zip'
          )
```
### Parameters
> **folderPath** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Folder within your lakehouse in which the .zip file containing the vertipaq analyzer info has been saved.
>
> **fileName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; File name of the file which contains the vertipaq analyzer info.

---
## list_dashboards
#### Shows the dashboards within the workspace.
```python
import fabric_cat_tools as fct
fct.list_dashboards(
            #workspaceName = '' 
            )
```
### Parameters
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace name.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

---
## list_shortcuts
#### Shows the shortcuts within a lakehouse
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            datasetName = 'AdventureWorks'
            #,workspaceName = '' 
            )
```
### Parameters
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **measureName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure to use for building a dependency tree.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

---
## migrate_field_parameters
#### Migrates field parameters from one semantic model to another.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_field_parameters(
            datasetName = 'AdventureWorks'
            ,newDatasetName = ''
            #,workspaceName = '' 
            )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **refreshType** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Type of processing to perform. Options: ('full', 'automatic', 'dataOnly', 'calculate', 'clearValues', 'defragment'). Default value: 'full'.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column's table(s).
>
> **columnName** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column(s).
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **measureName** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure(s).
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table(s).
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to rebind to the report.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model and report reside.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model currently binded to the reports.
>
> **newDatasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to rebind to the reports.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic models and reports reside.
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
> **lakehouseId** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a lakehouse.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the lakehouse.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
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
> **datasetId** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **reportName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.

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
> **reportId** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a report.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.

---
## run_model_bpa
#### Runs the Best Practice Rules against a semantic model.
```python
import fabric_cat_tools as fct
fct.run_model_bpa(
        datasetName = 'AdventureWorks'
        #,workspaceName = ''
        ,extend = True
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **rulesDataFrame**
> 
>> Optional; A pandas dataframe including rules to be analyzed.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **extend** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Extends the best practice rules to run advanced rules which leverage DMVs.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouseWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

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
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **tableName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table in the semantic model.
>
> **entityName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the lakehouse table to be mapped to the semantic model table.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouseName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **lakehouseWorkspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.

---
## vertipaq_analyzer
#### Extracts the vertipaq analyzer statistics from a semantic model.
```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        datasetName = 'AdventureWorks'
        #,workspaceName = ''
        ,export = None
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        datasetName = 'AdventureWorks'
        #,workspaceName = ''
        ,export = 'zip'
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        datasetName = 'AdventureWorks'
        #,workspaceName = ''
        ,export = 'table'
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **export** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying 'zip' will export the results to a zip file in your lakehouse (which can be imported using the [import_vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#import_vertipaq_analyzer) function. Specifying 'table' will export the results to delta tables (appended) in your lakehouse. Default value: None.

---
## warm_direct_lake_cache_perspective
#### Warms the cache of a Direct Lake semantic model by running a simple DAX query against the columns in a perspective
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.warm_direct_lake_cache_perspective(
        datasetName = 'AdventureWorks'
        ,perspective = 'WarmCache'
        ,addDependencies = True
        #,workspaceName = '' 
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **perspective** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the perspective which contains objects to be used for warming the cache.
>
> **addDependencies** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Includes object dependencies in the cache warming process.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.

---
## warm_direct_lake_cache_isresident
#### Performs a refresh on the semantic model and puts the columns which were in memory prior to the refresh back into memory.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.warm_direct_lake_cache_isresident(
        datasetName = 'AdventureWorks'
        #,workspaceName = '' 
        )
```
### Parameters
> **datasetName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
---
---
## Direct Lake migration

The following process automates the migration of an import/DirectQuery model to a new [Direct Lake](https://learn.microsoft.com/power-bi/enterprise/directlake-overview) model. The first step is specifically applicable to models which use Power Query to perform data transformations. If your model does not use Power Query, you must migrate the base tables used in your semantic model to a Fabric lakehouse.

Check out [Nikola Ilic](https://twitter.com/DataMozart)'s terrific [blog post](https://data-mozart.com/migrate-existing-power-bi-semantic-models-to-direct-lake-a-step-by-step-guide/) on this topic!

Check out my [blog post](https://www.elegantbi.com/post/direct-lake-migration) on this topic!

### Prerequisites

* Make sure you [enable XMLA Read/Write](https://learn.microsoft.com/power-bi/enterprise/service-premium-connect-tools#enable-xmla-read-write) for your capacity
* Make sure you have a [lakehouse](https://learn.microsoft.com/fabric/onelake/create-lakehouse-onelake#create-a-lakehouse) in a Fabric workspace
* Enable the following [setting](https://learn.microsoft.com/power-bi/transform-model/service-edit-data-models#enable-the-preview-feature): Workspace -> Workspace Settings -> General -> Data model settings -> Users can edit data models in the Power BI service

### Instructions

1. Download this [notebook](https://github.com/m-kovalsky/fabric_cat_tools/blob/main/Migration%20to%20Direct%20Lake.ipynb). **Use version 0.2.1 or higher only.**
2. Make sure you are in the ['Data Engineering' persona](https://learn.microsoft.com/fabric/get-started/microsoft-fabric-overview#components-of-microsoft-fabric). Click the icon at the bottom left corner of your Workspace screen and select 'Data Engineering'
3. In your workspace, select 'New -> Import notebook' and import the notebook from step 1.
4. [Add your lakehouse](https://learn.microsoft.com/fabric/data-engineering/lakehouse-notebook-explore#add-or-remove-a-lakehouse) to your Fabric notebook
5. Follow the instructions within the notebook.

### The migration process

> [!NOTE]
> The first 4 steps are only necessary if you have logic in Power Query. Otherwise, you will need to migrate your semantic model source tables to lakehouse tables.

1. The first step of the notebook creates a Power Query Template (.pqt) file which eases the migration of Power Query logic to Dataflows Gen2.
2. After the .pqt file is created, sync files from your [OneLake file explorer](https://www.microsoft.com/download/details.aspx?id=105222), create a new Dataflows Gen2, and import the Power Query Template file.
3. Manually map each table to its destination (your lakehouse).
4. Publish the Dataflow Gen2 and wait for it to finish creating the delta lake tables in your lakehouse.
5. Back in the notebook, the next step will create your new Direct Lake semantic model with the name of your choice, taking all the relevant properties from the orignal semantic model and refreshing/framing your new semantic model.

> [!NOTE]
> As of version 0.2.1, calculated tables are also migrated to Direct Lake (as data tables with their DAX expression stored as model annotations in the new semantic model). Additionally, Field Parameters are migrated as they were in the original semantic model (as a calculated table).

6. Finally, you can easily rebind your all reports which use the import/DQ semantic model to the new Direct Lake semantic model in one click.

### Completing these steps will do the following:
* Offload your Power Query logic to Dataflows Gen2 inside of Fabric (where it can be maintained and development can continue).
* Dataflows Gen2 will create delta tables in your Fabric lakehouse. These tables can then be used for your Direct Lake model.
* Create a new semantic model in Direct Lake mode containing all the standard tables and columns, calculation groups, measures, relationships, hierarchies, roles, row level security, perspectives, and translations from your original semantic model.
* Viable calculated tables are migrated to the new semantic model as data tables. Delta tables are dynamically generated in the lakehouse to support the Direct Lake model. The calculated table DAX logic is stored as model annotations in the new semantic model.
* Field parameters are migrated to the new semantic model as they were in the original semantic model (as calculated tables). Any calculated columns used in field parameters are automatically removed in the new semantic model's field parameter(s).
* Non-supported objects are not transferred (i.e. calculated columns, relationships using columns with unsupported data types etc.).
* Reports used by your original semantic model will be rebinded to your new semantic model.

## Version History

- Version 0.2.5 (Apr 11, 2024)
    - Fixed [bug](https://github.com/m-kovalsky/fabric_cat_tools/issues/1) in [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) regarding models with no hierarchies
    - Added [list_shortcuts](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_shortcuts) function
    - Added [list_dashboards](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_dashboards) function
    - Added new rule to [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa): 'Set dimensions tables to dual mode instead of import when using DirectQuery on fact tables'
    - Added 'saveToFileName' parameter to [get_semantic_model_bim](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_semantic_model_bim)
    - Added 'saveToFileName' parameter to [get_report_json](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_report_json)
- Version 0.2.4 (Apr 8, 2024)
    - Added [create_shortcut_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_shortcut_onelake) function
    - Added [export_model_to_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_model_to_onelake) function
    - Added [delete_shortcut](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#delete_shortcut) function
    - Removed 'extend' paramter from the [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) function
    - Fixed bug in [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) function which duplicated violations on hierarchy objects
- Version 0.2.3 (Apr 8, 2024)
    - Added [export_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_report) function
    - Added [clone_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clone_report) function
    - Added [get_report_json](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_report_json) function
- Version 0.2.2 (Apr 4, 2024)
    - Fixed bug regarding how Field Parameters are created ([add_field_parameter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_field_parameter), [migrate_field_parameters](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#migrate_field_parameters))
    - Added escape clause for [get_shared_expression](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_shared_expression) if the SQL Endpoint has not yet been provisioned
    - Added functionality to [vertipaq_analzyer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analzyer) so that the column cardinality for Direct Lake semantic models is obtained by querying the lakehouse
