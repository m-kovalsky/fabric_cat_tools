# fabric_cat_tools
This is a python library intended to be used in [Microsoft Fabric notebooks](https://learn.microsoft.com/fabric/data-engineering/how-to-use-notebook). This library was originally intended to contain functions used for [migrating semantic models to Direct Lake mode](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1). However, it quickly became apparent that functions within such a library could support many other useful activities in the realm of semantic models, reports, lakehouses and really anything Fabric-related. As such, this library contains a variety of functions ranging from running [Vertipaq Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analyzer) or the [Best Practice Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) against a semantic model to seeing if any [lakehouse tables hit Direct Lake guardrails](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_tables) and more.

Instructions for migrating import/DirectQuery semantic models to Direct Lake mode can be found [here](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1).

If you encounter any issues, please [raise a bug](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=bug_report.md&title=).

If you have ideas for new features/functions, please [request a feature](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=feature_request.md&title=).

## Install the .whl file in a Fabric notebook
```python
%pip install "https://raw.githubusercontent.com/m-kovalsky/fabric_cat_tools/main/fabric_cat_tools-0.3.0-py3-none-any.whl"
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
1. Download the [latest](https://github.com/m-kovalsky/fabric_cat_tools/raw/main/fabric_cat_tools-0.3.0-py3-none-any.whl) fabric_cat_tools library
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
* [cancel_dataset_refresh](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#cancel_dataset_refresh)

### Report
* [report_rebind](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind)
* [report_rebind_all](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind_all)
* [create_report_from_reportjson](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_report_from_reportjson)
* [get_report_json](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_report_json)
* [export_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_report)
* [clone_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clone_report)
* [list_dashboards](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_dashboards)
* [launch_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#launch_report)

### Model Optimization
* [vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analyzer)
* [import_vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#import_vertipaq_analyzer)
* [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa)
* [model_bpa_rules](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#model_bpa_rules)


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
* [list_lakehouses](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_lakehouses)
* [export_model_to_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_model_to_onelake)
* [create_shortcut_onelake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_shortcut_onelake)
* [delete_shortcut](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#delete_shortcut)
* [list_shortcuts](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_shortcuts)
* [optimize_lakehouse_tables](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#optimize_lakehouse_tables)

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
        dataset = 'AdventureWorks'
        ,table_name = 'Internet Sales'
        ,column_name = 'SalesAmount'
        ,source_column = 'SalesAmount'
        ,data_type =  'Int64'
        #,format_string = ''
        #,display_folder = ''
        #,workspace = '' 
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the semantic model.
> 
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the table in which the column will reside.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the column.
>
> **source_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the column in the source system.
>
> **data_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Data type of the column. Options: 'Int64', 'String', 'Double', 'Decimal', 'DateTime', 'Boolean'.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Format string of the column.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Description of the column.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Display folder of the column.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## add_field_parameter
#### Adds a [field parameter](https://learn.microsoft.com/power-bi/create-reports/power-bi-field-parameters) to a semantic model.
```python
import fabric_cat_tools as fct
fct.add_field_parameter(
            dataset = 'AdventureWorks'
            ,table_name = 'Parameter'
            ,objects = ["[Sales Amount]", "[Order Qty]", "'Internet Sales'[Color]"]
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the semantic model.
> 
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str) 
>
>> Required; Name of the field parameter table.
>
> **objects** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; List of columns/measures to be included in the field parameter. Columns are fully qualified 'TableName'[ColumnName] and measures are in square brackets [MeasureName].
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,table_name = 'Geography'
            ,hierarchy_name = 'Geography Hierarchy'
            ,levels = ['Continent', 'Country', 'City']
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the semantic model.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the table in which the hierarchy will reside.
>
> **hierarchy_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the hierarchy.
>
> **levels** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; List of columns to be included as levels in the hierarchy.
>
> **workspace_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
        dataset = 'AdventureWorks'
        ,table_name = 'Internet Sales'
        ,measure_name = 'Sales Amount'
        ,expression =  "SUM( 'Internet Sales'[SalesAmount] )"
        #,display_folder = ''
        #,format_string = ''
        #,workspace = '' 
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table in which the measure will reside.
>
> **measure_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; DAX expression for the measure.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Display folder for the measure.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Format string for the measure.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,from_table = 'Internet Sales'
            ,from_column = 'ProductKey'
            ,to_table = 'Product'
            ,to_column = 'ProductKey'
            ,from_cardinality = 'Many'
            ,to_cardinality = 'One'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **from_table** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table on the 'from' side of the relationship
>
> **to_table** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table on the 'to' side of the relationship
>
> **from_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column on the 'from' side of the relationship
>
> **to_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column on the 'to' side of the relationship
>
> **from_cardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Cardinality on the 'from' side of the relationship. Options: ('Many', 'One', None').
>
> **to_cardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Cardinality on the 'to' side of the relationship. Options: ('Many', 'One', None').
>
> **cross_filtering_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Setting for the cross filtering behavior of the relationship. Options: ('Automatic', 'OneDirection', 'BothDirections'). Default value: 'Automatic'.
>
> **security_filtering_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Setting for the security filtering behavior of the relationship. Options: ('None', 'OneDirection', 'BothDirections'). Default value: 'OneDirection'.
>
> **is_active** [bool](https://docs.python.org/3/library/functions.html#bool)
> 
>> Optional; Setting for whether the relationship is active or not. Default value: True.
>
> **rely_on_referential_integrity** [bool](https://docs.python.org/3/library/functions.html#bool)
> 
>> Optional; Setting for the rely on referential integrity of the relationship. Default value: True.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,role_name = 'Reader'
            ,role_description = 'This role is for...'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **role_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the role.
>
> **role_description** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Description of the role.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,role_name = 'Reader'
            ,table_name = 'UserGeography'
            ,filter_expression = "'UserGeography'[UserEmail] = USERPRINCIPALNAME()"
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **role_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the role to apply row level security.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table to apply row level security.
>
> **filter_expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; DAX expression for the row low level security.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## cancel_dataset_refresh
#### Cancels the refresh of a semantic model which was executed via the [Enhanced Refresh API](https://learn.microsoft.com/power-bi/connect-data/asynchronous-refresh).
```python
import fabric_cat_tools as fct
fct.cancel_dataset_refresh(
            dataset = 'MyReport'
            #,request_id = None
            #,workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **request_id** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The [request id](https://learn.microsoft.com/power-bi/connect-data/asynchronous-refresh#response-properties) of a semantic model refresh. Defaults to finding the latest active refresh of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            report = 'MyReport'
            ,cloned_report = 'MyNewReport'
            #,workspace = None
            #,target_workspace = None
            #,target_dataset = None
            )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report to be cloned.
>
> **cloned_report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the new report.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the original report resides.
>
> **target_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the new report will reside. Defaults to using the workspace in which the original report resides.
>
> **target_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,direct_lake_behavior = 'DirectLakeOnly'            
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **direct_lake_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Setting for Direct Lake Behavior. Options: ('Automatic', 'DirectLakeOnly', 'DirectQueryOnly').
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            #,workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **compatibility_level** [int](https://docs.python.org/3/library/functions.html#int)
> 
>> Optional; Setting for the compatibility level of the semantic model. Default value: 1605.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            #,file_name = 'PowerQueryTemplate'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **file_name** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Optional; TName of the Power Query Template (.pqt) file to be created.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            report = 'MyReport'
            ,dataset = 'AdventureWorks'
            ,report_json = ''
            #,theme_json = ''
            #,workspace = ''
            )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to connect to the report.
>
> **report_json** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The report.json file to be used to create the report.
> 
> **theme_json** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The theme.json file to be used for the theme of the report.
> 
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            ,bim_file = ''
            #,workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **bim_file** [Dict](https://docs.python.org/3/library/typing.html#typing.Dict) or [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The model.bim file to be used to create the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            table_tame = 'DimCalendar'
            ,source_lakehouse = 'Lakehouse1'
            ,source_workspace = 'Workspace1'
            ,destination_lakehouse = 'Lakehouse2'
            #,destination_workspace = ''
            ,shortcut_name = 'Calendar'
            )
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The table name for which a shortcut will be created.
>
> **source_lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The lakehouse in which the table resides.
>
> **sourceWorkspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The workspace where the source lakehouse resides.
>
> **destination_lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The lakehouse where the shortcut will be created.
>
> **destination_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the shortcut will be created. Defaults to the 'sourceWorkspaceName' parameter value.
>
> **shortcut_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name of the shortcut 'table' to be created. This defaults to the 'tableName' parameter value.
>
### Returns
> A printout stating the success/failure of the operation.

---
## delete_shortcut
#### Deletes a [OneLake shortcut](https://learn.microsoft.com/fabric/onelake/onelake-shortcuts).
```python
import fabric_cat_tools as fct
fct.delete_shortcut(
            shortcut_name = 'DimCalendar'
            ,lakehouse = 'Lakehouse1'
            ,workspace = 'Workspace1'
            )
```
### Parameters
> **shortcut_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The name of the OneLake shortcut to delete.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse in which the shortcut resides.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
>
### Returns
> A printout stating the success/failure of the operation.

---
## direct_lake_schema_compare
#### Checks that all the tables in a Direct Lake semantic model map to tables in their corresponding lakehouse and that the columns in each table exist.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.direct_lake_schema_compare(
            dataset = 'AdventureWorks'
            ,workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse used by the Direct Lake semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.
>
### Returns
> Shows tables/columns which exist in the semantic model but do not exist in the corresponding lakehouse.

---
## direct_lake_schema_sync
#### Shows/adds columns which exist in the lakehouse but do not exist in the semantic model (only for tables in the semantic model).
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.direct_lake_schema_sync(
     dataset = 'AdvWorks'
    ,add_to_model = True
    #,workspace = ''
    #,lakehouse = ''
    #,lakehouse_workspace = ''
    )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **add_to_model** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds columns which exist in the lakehouse but do not exist in the semantic model. No new tables are added. Default value: False.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse used by the Direct Lake semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.
>
### Returns
> A list of columns which exist in the lakehouse but not in the Direct Lake semantic model. If lakehouseName is specified, a printout stating the success/failure of the operation is returned.

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
            dataset = 'AdventureWorks'
            ,workspace = None
            ,destination_lakehouse = 'Lakehouse2'            
            ,destination_workspace = 'Workspace2'
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **destination_lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse where shortcuts will be created to access the delta tables created by the export. If the lakehouse specified does not exist, one will be created with that name. If no lakehouse is specified, shortcuts will not be created.
>
> **destination_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse resides.
>
### Returns
> A printout stating the success/failure of the operation.

---
## export_report
#### Exports a Power BI report to a file in your lakehouse.
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks'
            ,export_format = 'PDF'
            #,file_name = None
            #,bookmark_name = None
            #,page_name = None
            #,visual_name = None
            #,workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks'
            ,export_format = 'PDF'
            #,file_name = 'Exports\MyReport'
            #,bookmark_name = None
            #,page_name = 'ReportSection293847182375'
            #,visual_name = None
            #,workspace = None
            )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **export_format** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The format in which to export the report. See this link for valid formats: https://learn.microsoft.com/rest/api/power-bi/reports/export-to-file-in-group#fileformat. For image formats, enter the file extension in this parameter, not 'IMAGE'.
>
> **file_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name of the file to be saved within the lakehouse. Do **not** include the file extension. Defaults ot the reportName parameter value.
>
> **bookmark_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of a bookmark within the report.
>
> **page_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of the report page.
>
> **visual_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of a visual. If you specify this parameter you must also specify the pageName parameter.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
>
### Returns
> A printout stating the success/failure of the operation.

---
## get_direct_lake_guardrails
#### Shows the guardrails for when Direct Lake semantic models will fallback to Direct Query based on Microsoft's online documentation.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_guardrails()
```
### Parameters
None
### Returns
> A table showing the Direct Lake guardrails by SKU.

---
## get_directlake_guardrails_for_sku
#### Shows the guardrails for Direct Lake based on the SKU used by your workspace's capacity.
*Use the result of the 'get_sku_size' function as an input for this function's skuSize parameter.*
```python
import fabric_cat_tools as fct
fct.get_directlake_guardrails_for_sku(
            sku_size = ''
            )
```
### Parameters
> **sku_size** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Sku size of a workspace/capacity
### Returns
> A table showing the Direct Lake guardrails for the given SKU.

---
## get_direct_lake_lakehouse
#### Identifies the lakehouse used by a Direct Lake semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.get_direct_lake_lakehouse(
            dataset = 'AdventureWorks'
            #,workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''            
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse used by the semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
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
            dataset = 'AdventureWorks'
            #,workspace = ''       
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A string containing the SQL Endpoint ID for a Direct Lake semantic model.

---
## get_lakehouse_columns
#### Shows the tables and columns of a lakehouse and their respective properties.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_columns(
            lakehouse = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A pandas dataframe showing the tables/columns within a lakehouse and their properties.

---
## get_lakehouse_tables
#### Shows the tables of a lakehouse and their respective properties. Option to include additional properties relevant to Direct Lake guardrails.
```python
import fabric_cat_tools as fct
fct.get_lakehouse_tables(
        lakehouse = 'MyLakehouse'
        #,workspace = ''
        ,extended = True
        ,count_rows = True)
```
### Parameters
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
>
> **extended** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds the following additional table properties \['Files', 'Row Groups', 'Table Size', 'Parquet File Guardrail', 'Row Group Guardrail', 'Row Count Guardrail'\]. Also indicates the SKU for the workspace and whether guardrails are hit. Default value: False.
>
> **count_rows** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Adds an additional column showing the row count of each table. Default value: False.
### Returns
> A pandas dataframe showing the delta tables within a lakehouse and their properties.

---
## get_measure_dependencies
#### Shows all dependencies for all measures in a semantic model
```python
import fabric_cat_tools as fct
fct.get_measure_dependencies(
            dataset = 'AdventureWorks'
            #,workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A pandas dataframe showing all dependencies for all measures in the semantic model.

---
## get_report_json
#### Gets the report.json file content of a Power BI report
```python
import fabric_cat_tools as fct
fct.get_report_json(
            report = 'MyReport'
            #,workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_report_json(
            report = 'MyReport'
            #,workspace = None
            ,save_to_file_name = 'MyFileName'
            )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
>
> **save_to_file_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying this parameter will save the report.json file to your lakehouse with the file name of this parameter.
### Returns
> The report.json file for a given Power BI report.

---
## get_semantic_model_bim
#### Extracts the Model.bim file for a given semantic model.
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            dataset = 'AdventureWorks'
            #,workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            dataset = 'AdventureWorks'
            #,workspace = None
            ,save_to_file_name = 'MyFileName'
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **save_to_file_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying this parameter will save the model.bim file to your lakehouse with the file name of this parameter.
### Returns
> The model.bim file for a given semantic model.

---
## get_shared_expression
#### Dynamically generates the M expression used by a Direct Lake model for a given lakehouse.
```python
import fabric_cat_tools as fct
fct.get_shared_expression(
            lakehouse = ''
            #,workspace = '' 
            )
```
### Parameters
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse name.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A string showing the expression which can be used to connect a Direct Lake semantic model to its SQL Endpoint.

---
## get_sku_size
#### Shows the SKU size for a workspace.
```python
import fabric_cat_tools as fct
fct.get_sku_size(
            workspace = '' 
            )
```
### Parameters
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A string containing the SKU size for a workspace.

---
## import_vertipaq_analyzer
#### Imports and visualizes the vertipaq analyzer info from a saved .zip file in your lakehouse.
```python
import fabric_cat_tools as fct
fct.import_vertipaq_analyzer(
          folder_path = '/lakehouse/default/Files/VertipaqAnalyzer'
          ,file_name = 'Workspace Name-DatasetName.zip'
          )
```
### Parameters
> **folder_path** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Folder within your lakehouse in which the .zip file containing the vertipaq analyzer info has been saved.
>
> **file_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; File name of the file which contains the vertipaq analyzer info.

---
## launch_report
#### Shows a Power BI report within a Fabric notebook.
```python
import fabric_cat_tools as fct
fct.launch_report(
          report = 'MyReport'
          #,workspace = None
          )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the report.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name of the workspace in which the report resides.

---
## list_dashboards
#### Shows the dashboards within the workspace.
```python
import fabric_cat_tools as fct
fct.list_dashboards(
            #workspace = '' 
            )
```
### Parameters
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace name.
### Returns
> A pandas dataframe showing the dashboards which exist in the workspace.

---
## list_direct_lake_model_calc_tables
#### Shows the calculated tables and their respective DAX expression for a Direct Lake model (which has been migrated from import/DirectQuery.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            dataset = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A pandas dataframe showing the calculated tables which were migrated to Direct Lake and whose DAX expressions are stored as model annotations.

---
## list_lakehouses
#### Shows the properties associated with lakehouses in a workspace.
```python
import fabric_cat_tools as fct
fct.list_lakehouses(
            workspace = None
            )
```
### Parameters
> **workspaceName** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A pandas dataframe showing the properties of a all lakehouses in a workspace.

---
## list_shortcuts
#### Shows the shortcuts within a lakehouse
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            dataset = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A pandas dataframe showing the shortcuts which exist in a given lakehouse and their properties.

---
## measure_dependency_tree
#### Shows a measure dependency tree of all dependent objects for a measure in a semantic model.
```python
import fabric_cat_tools as fct
fct.measure_dependency_tree(
            dataset = 'AdventureWorks'
            ,measure_name = 'Sales Amount'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **measure_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure to use for building a dependency tree.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A tree view showing the dependencies for a given measure within the semantic model.

---
## migrate_calc_tables_to_lakehouse
#### Creates delta tables in your lakehouse based on the DAX expression of a calculated table in an import/DirectQuery semantic model. The DAX expression encapsulating the calculated table logic is stored in the new Direct Lake semantic model as model annotations.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_lakehouse(
            dataset = 'AdventureWorks'
            ,new_dataset = 'AdventureWorksDL'
            #,workspace = ''
            #,new_dataset_workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace to be used by the Direct Lake semantic model.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse to be used by the Direct Lake semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## migrate_calc_tables_to_semantic_model
#### Creates new tables in the Direct Lake semantic model based on the lakehouse tables created using the 'migrate_calc_tables_to_lakehouse' function.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_calc_tables_to_semantic_model(
            dataset = 'AdventureWorks'
            ,new_dataset = 'AdventureWorksDL'
            #,workspace = ''
            #,new_dataset_workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace to be used by the Direct Lake semantic model.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse to be used by the Direct Lake semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## migrate_field_parameters
#### Migrates field parameters from one semantic model to another.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_field_parameters(
            dataset = 'AdventureWorks'
            ,new_dataset = ''
            #,workspace = ''
            #,new_dataset_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace to be used by the Direct Lake semantic model.
### Returns
> A printout stating the success/failure of the operation.

---
## migrate_model_objects_to_semantic_model
#### Adds the rest of the model objects (besides tables/columns) and their properties to a Direct Lake semantic model based on an import/DirectQuery semantic model.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_model_objects_to_semantic_model(
            dataset = 'AdventureWorks'
            ,new_dataset = ''
            #,workspace = ''
            #,new_dataset_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace to be used by the Direct Lake semantic model.
### Returns
> A printout stating the success/failure of the operation.

---
## migrate_tables_columns_to_semantic_model
#### Adds tables/columns to the new Direct Lake semantic model based on an import/DirectQuery semantic model.
> [!NOTE]
> This function is specifically relevant for import/DirectQuery migration to Direct Lake
```python
import fabric_cat_tools as fct
fct.migrate_tables_columns_to_semantic_model(
            dataset = 'AdventureWorks'
            ,new_dataset = 'AdventureWorksDL'
            #,workspace = ''
            #,new_dataset_workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the import/DirectQuery semantic model.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the Direct Lake semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace to be used by the Direct Lake semantic model.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The lakehouse to be used by the Direct Lake semantic model.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## model_bpa_rules
#### Shows the default Best Practice Rules for the semantic model used by the [run_model_bpa](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) function
```python
import fabric_cat_tools as fct
fct.model_bpa_rules()
```
### Returns
> A pandas dataframe showing the default semantic model best practice rules.

---
## optimize_lakehouse_tables
#### Runs the [OPTIMIZE](https://docs.delta.io/latest/optimizations-oss.html) function over the specified lakehouse tables.
```python
import fabric_cat_tools as fct
fct.optimize_lakehouse_tables(
            tables = ['Sales', 'Calendar']
            #,lakehouse = None
            #,workspace = None
        )
```
```python
import fabric_cat_tools as fct
fct.optimize_lakehouse_tables(
            tables = None
            #,lakehouse = 'MyLakehouse'
            #,workspace = 'MyNewWorkspace'
        )
```
### Parameters
> **tables** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name(s) of the lakehouse delta table(s) to optimize. If 'None' is entered, all of the delta tables in the lakehouse will be queued to be optimized.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the lakehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## refresh_calc_tables
#### Recreates the delta tables in the lakehouse based on the DAX expressions stored as model annotations in the Direct Lake semantic model.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.refresh_calc_tables(
            dataset = 'AdventureWorks'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## refresh_semantic_model
#### Performs a refresh on a semantic model.
```python
import fabric_cat_tools as fct
fct.refresh_semantic_model(
            dataset = 'AdventureWorks'
            ,refresh_type = 'full'
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **refresh_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Type of processing to perform. Options: ('full', 'automatic', 'dataOnly', 'calculate', 'clearValues', 'defragment'). Default value: 'full'.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## remove_column
#### Removes a column (or multiple columns) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_column(
            dataset = 'AdventureWorks'
            ,table_name = ['Internet Sales', 'Geography']
            ,column_name = ['SalesAmount', 'GeographyKey']
            #,workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column's table(s).
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the column(s).
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## remove_measure
#### Removes a measure (or multiple measures) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_measure(
            dataset = 'AdventureWorks'
            ,measure_name = ['Sales Amount', 'Order Quantity']
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **measure_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the measure(s).
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## remove_table
#### Removes a table (or multiple tables) in a semantic model.
```python
import fabric_cat_tools as fct
fct.remove_table(
            dataset = 'AdventureWorks'
            ,table_name = ['Internet Sales', 'Geography']
            #,workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table(s).
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## report_rebind
#### Rebinds a report to a semantic model.
```python
import fabric_cat_tools as fct
fct.report_rebind(
            report = ''
            ,dataset = ''
            #,report_workspace = ''
            #,dataset_workspace = ''
            )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to rebind to the report.
>
> **report_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
>
> **dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## report_rebind_all
#### Rebinds all reports in a workspace which are bound to a specific semantic model to a new semantic model.
```python
import fabric_cat_tools as fct
fct.report_rebind_all(
            dataset = ''
            ,new_dataset = ''
            #,dataset_workspace = '' 
            #,new_dataset_workspace = '' 
            #,report_workspace = '' 
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model currently binded to the reports.
>
> **new_dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model to rebind to the reports.
>
> **dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the original semantic model resides.
>
> **new_dataset_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the new semantic model resides.
>
> **report_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the reports reside.
### Returns
> A printout stating the success/failure of the operation.

---
## resolve_lakehouse_name
#### Returns the name of the lakehouse for a given lakehouse Id.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_name(
        lakehouse_id = ''
        #,workspace = '' 
        )
```
### Parameters
> **lakehouse_id** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a lakehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A string containing the lakehouse name.

---
## resolve_lakehouse_id
#### Returns the ID of a given lakehouse.
```python
import fabric_cat_tools as fct
fct.resolve_lakehouse_id(
        lakehouse = 'MyLakehouse'
        #,workspace = '' 
        )
```
### Parameters
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the lakehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A string conaining the lakehouse ID.

---
## resolve_dataset_id
#### Returns the ID of a given semantic model.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_id(
        dataset = 'MyReport'
        #,workspace = '' 
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
> A string containing the semantic model ID.

---
## resolve_dataset_name
#### Returns the name of a given semantic model ID.
```python
import fabric_cat_tools as fct
fct.resolve_dataset_name(
        dataset_id = ''
        #,workspace = '' 
        )
```
### Parameters
> **dataset_id** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A string containing the semantic model name.

---
## resolve_report_id
#### Returns the ID of a given report.
```python
import fabric_cat_tools as fct
fct.resolve_report_id(
        report = 'MyReport'
        #,workspace = '' 
        )
```
### Parameters
> **report** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the report.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
### Returns
> A string containing the report ID.

---
## resolve_report_name
#### Returns the name of a given report ID.
```python
import fabric_cat_tools as fct
fct.resolve_report_name(
        report_id = ''
        #,workspace = '' 
        )
```
### Parameters
> **report_id** [UUID](https://docs.python.org/3/library/uuid.html#uuid.UUID)
> 
>> Required; UUID object representing a report.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
### Returns
> A string containing the report name.

---
## run_model_bpa
#### Runs the Best Practice Rules against a semantic model.
```python
import fabric_cat_tools as fct
fct.run_model_bpa(
        dataset = 'AdventureWorks'
        #,workspace = ''
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **rules_dataframe**
> 
>> Optional; A pandas dataframe including rules to be analyzed.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A visualization showing objects which violate each [Best Practice Rule](https://github.com/microsoft/Analysis-Services/tree/master/BestPracticeRules) by rule category.

---
## show_unsupported_direct_lake_objects
#### Returns a list of a semantic model's objects which are not supported by Direct Lake based on [official documentation](https://learn.microsoft.com/power-bi/enterprise/directlake-overview#known-issues-and-limitations).
```python
import fabric_cat_tools as fct
fct.show_unsupported_direct_lake_objects(
        dataset = 'AdventureWorks'
        #,workspace = '' 
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A list of objects (tables/columns/relationships) within the semantic model which are currently not supported by Direct Lake mode.

---
## update_direct_lake_model_lakehouse_connection
#### Remaps a Direct Lake semantic model's SQL Endpoint connection to a new lakehouse.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_model_lakehouse_connection(
            dataset = ''
            #,lakehouse = ''
            #,workspace = ''
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## update_direct_lake_partition_entity
#### Remaps a table (or tables) in a Direct Lake semantic model to a table in a lakehouse.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_partition_entity(
            dataset = 'AdventureWorks'
            ,table_name = 'Internet Sales'
            ,entity_name = 'FACT_InternetSales'
            #,workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''            
            )
```
```python
import fabric_cat_tools as fct
fct.update_direct_lake_partition_entity(
            dataset = 'AdventureWorks'
            ,table_name = ['Internet Sales', 'Geography']
            ,entity_name = ['FACT_InternetSales', 'DimGeography']
            #,workspace = ''
            #,lakehouse = ''
            #,lakehouse_workspace = ''            
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the table in the semantic model.
>
> **entity_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the lakehouse table to be mapped to the semantic model table.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the lakehouse resides.
### Returns
> A printout stating the success/failure of the operation.

---
## vertipaq_analyzer
#### Extracts the vertipaq analyzer statistics from a semantic model.
```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks'
        #,workspace = ''
        ,export = None
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks'
        #,workspace = ''
        ,export = 'zip'
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks'
        #,workspace = ''
        ,export = 'table'
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **export** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Specifying 'zip' will export the results to a zip file in your lakehouse (which can be imported using the [import_vertipaq_analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#import_vertipaq_analyzer) function. Specifying 'table' will export the results to delta tables (appended) in your lakehouse. Default value: None.
### Returns
> A visualization of the Vertipaq Analyzer statistics.

---
## warm_direct_lake_cache_perspective
#### Warms the cache of a Direct Lake semantic model by running a simple DAX query against the columns in a perspective
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.warm_direct_lake_cache_perspective(
        dataset = 'AdventureWorks'
        ,perspective = 'WarmCache'
        ,add_dependencies = True
        #,workspace = '' 
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **perspective** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the perspective which contains objects to be used for warming the cache.
>
> **add_dependencies** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Includes object dependencies in the cache warming process.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## warm_direct_lake_cache_isresident
#### Performs a refresh on the semantic model and puts the columns which were in memory prior to the refresh back into memory.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.warm_direct_lake_cache_isresident(
        dataset = 'AdventureWorks'
        #,workspace = '' 
        )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.
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
2. After the .pqt file is created, sync files from your [OneLake file explorer](https://www.microsoft.com/download/details.aspx?id=105222)
3. Navigate to your lakehouse (this is critical!). From your lakehouse, create a new Dataflows Gen2, and import the Power Query Template file. Doing this step from your lakehouse will automatically set the destination for all tables to this lakehouse (instead of having to manually map each one).
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
