# fabric_cat_tools
This is a python library intended to be used in [Microsoft Fabric notebooks](https://learn.microsoft.com/fabric/data-engineering/how-to-use-notebook). This library was originally intended to contain functions used for [migrating semantic models to Direct Lake mode](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1). However, it quickly became apparent that functions within such a library could support many other useful activities in the realm of semantic models, reports, lakehouses and really anything Fabric-related. As such, this library contains a variety of functions ranging from running [Vertipaq Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#vertipaq_analyzer) or the [Best Practice Analyzer](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_model_bpa) against a semantic model to seeing if any [lakehouse tables hit Direct Lake guardrails](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_lakehouse_tables) and more.

Instructions for migrating import/DirectQuery semantic models to Direct Lake mode can be found [here](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#direct-lake-migration-1).

If you encounter any issues, please [raise a bug](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=bug_report.md&title=).

If you have ideas for new features/functions, please [request a feature](https://github.com/m-kovalsky/fabric_cat_tools/issues/new?assignees=&labels=&projects=&template=feature_request.md&title=).

## Install the .whl file in a Fabric notebook
```python
%pip install "https://raw.githubusercontent.com/m-kovalsky/fabric_cat_tools/main/fabric_cat_tools-0.3.3-py3-none-any.whl"
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
1. Download the [latest](https://github.com/m-kovalsky/fabric_cat_tools/raw/main/fabric_cat_tools-0.3.3-py3-none-any.whl) fabric_cat_tools library
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
* [get_model_calc_dependencies](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_model_calc_dependencies)
* [measure_dependency_tree](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#measure_dependency_tree)
* [refresh_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#refresh_semantic_model)
* [cancel_dataset_refresh](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#cancel_dataset_refresh)
* [run_dax](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#run_dax)
* [get_object_level_security](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_object_level_security)
* [translate_semantic_model](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#translate_semantic_model)

### Report
* [report_rebind](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind)
* [report_rebind_all](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#report_rebind_all)
* [create_report_from_reportjson](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_report_from_reportjson)
* [get_report_json](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_report_json)
* [export_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#export_report)
* [clone_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clone_report)
* [list_dashboards](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_dashboards)
* [launch_report](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#launch_report)
* [generate_embedded_filter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#generate_embedded_filter)

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
* [create_warehouse](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#create_warehouse)
* [update_item](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#update_item)
* [list_dataflow_storage_accounts](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_dataflow_storage_accounts)
* [list_warehouses](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#list_warehouses)


### Helper Functions
* [resolve_dataset_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_id)
* [resolve_dataset_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_dataset_name)
* [resolve_lakehouse_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_id)
* [resolve_lakehouse_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_lakehouse_name)
* [resolve_report_id](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#resolve_report_id)
* [resolve_report_name](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-files#resolve_report_name)

### [Tabular Object Model](https://learn.microsoft.com/analysis-services/tom/introduction-to-the-tabular-object-model-tom-in-analysis-services-amo?view=asallproducts-allversions) ([TOM](https://learn.microsoft.com/dotnet/api/microsoft.analysisservices.tabular.model?view=analysisservices-dotnet))
#### 'All' functions for non-parent objects within TOM
* [all_columns](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_columns)
* [all_measures](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_measures)
* [all_partitions](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_partitions)
* [all_hierarchies](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_hierarchies)
* [all_levels](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_levels)
* [all_calculation_items](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_calculation_items)
* [all_rls](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#all_rls)

#### 'Add' functions
* [add_calculated_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_calculated_column)
* [add_calculated_table](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_calculated_table)
* [add_calculated_table_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_calculated_table_column)
* [add_calculation_group](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_calculation_group)
* [add_calculation_item](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_calculation_item)
* [add_data_column](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_data_column)
* [add_entity_partition](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_entity_partition)
* [add_expression](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_expression)
* [add_field_parameter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_field_parameter)
* [add_hierarchy](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_hierarchy)
* [add_m_partition](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_m_partition)
* [add_measure](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_measure)
* [add_perspective](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_perspective)
* [add_relationship](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_relationship)
* [add_role](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_role)
* [add_table](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_table)
* [add_translation](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_translation)

#### 'Set' functions
* [set_direct_lake_behavior](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_direct_lake_behavior)
* [set_is_available_in_mdx](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_is_available_in_mdx)
* [set_ols](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_ols)
* [set_rls](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_rls)
* [set_summarize_by](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_summarize_by)
* [set_translation](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_translation)

#### 'Remove' functions
* [remove_object](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_object)
* [remove_translation](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_translation)

#### 'Used-in' and dependency functions
* [used_in_relationships](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_relationships)
* [used_in_hierarchies](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_hierarchies)
* [used_in_levels](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_levels)
* [used_in_sort_by](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_sort_by)
* [used_in_rls](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_rls)
* [used_in_calc_item](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_in_calc_item)
* [depends_on](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#depends_on)
* [referenced_by](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#referenced_by)
* [fully_qualified_measures](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#fully_qualified_measures)
* [unqualified_columns](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#unqualified_columns)

#### Vertipaq Analyzer data functions
* [remove_vertipaq_annotations](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_vertipaq_annotations)
* [set_vertipaq_annotations](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_vertipaq_annotations)
* [row_count](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#row_count)
* [used_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#used_size)
* [data_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#data_size)
* [dictionary_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#dictionary_size)
* [total_size](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#total_size)
* [cardinality](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#cardinality)

#### Perspectives
* [in_perspective](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#in_perspective)
* [add_to_perspective](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#add_to_perspective)
* [remove_from_perspective](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_from_perspective)
  
#### Annotations
* [get_annotations](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_annotations)
* [set_annotation](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_annotation)
* [get_annotation_value](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_annotation_value)
* [remove_annotation](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_annotation)
* [clear_annotations](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clear_annotations)

#### Extended Properties
* [get_extended_properties](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_extended_properties)
* [set_extended_property](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#set_extended_property)
* [get_extended_property_value](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#get_extended_property_value)
* [remove_extended_property](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#remove_extended_property)
* [clear_extended_properties](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#clear_extended_properties)

#### Misc
* [is_direct_lake](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#is_direct_lake)
* [is_field_parameter](https://github.com/m-kovalsky/fabric_cat_tools?tab=readme-ov-file#is_field_parameter)


# Functions
## cancel_dataset_refresh
#### Cancels the refresh of a semantic model which was executed via the [Enhanced Refresh API](https://learn.microsoft.com/power-bi/connect-data/asynchronous-refresh).
```python
import fabric_cat_tools as fct
fct.cancel_dataset_refresh(
            dataset = 'MyReport',
            #request_id = None,
            #workspace = None
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
            dataset = 'AdventureWorks',
            #workspace = None
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
            dataset = 'AdventureWorks',
            #workspace = '' 
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
            report = 'MyReport',
            cloned_report = 'MyNewReport',
            #workspace = None,
            #target_workspace = None,
            #target_dataset = None
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
            dataset = 'AdventureWorks',
            direct_lake_behavior = 'DirectLakeOnly',
            #workspace = None
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
            dataset = 'AdventureWorks',
            #workspace = None
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
            dataset = 'AdventureWorks',
            #file_name = 'PowerQueryTemplate',
            #workspace = None
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
            report = 'MyReport',
            dataset = 'AdventureWorks',
            report_json = '',
            #theme_json = '',
            #workspace = None
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
            dataset = 'AdventureWorks',
            bim_file = '',
            #workspace = ''
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
            table_name = 'DimCalendar',
            source_lakehouse = 'Lakehouse1',
            source_workspace = 'Workspace1',
            destination_lakehouse = 'Lakehouse2',
            #destination_workspace = '',
            shortcut_name = 'Calendar'
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
## create_warehouse
#### Creates a warehouse in Fabric.
```python
import fabric_cat_tools as fct
fct.create_warehouse(
            warehouse = 'MyWarehouse',
            workspace = None
            )
```
### Parameters
> **warehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the warehouse.
>
> **description** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Optional; Description of the warehouse.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the warehouse will reside.
### Returns
> A printout stating the success/failure of the operation.

---
## delete_shortcut
#### Deletes a [OneLake shortcut](https://learn.microsoft.com/fabric/onelake/onelake-shortcuts).
```python
import fabric_cat_tools as fct
fct.delete_shortcut(
            shortcut_name = 'DimCalendar',
            lakehouse = 'Lakehouse1',
            workspace = 'Workspace1'
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
            dataset = 'AdventureWorks',
            workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''
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
     dataset = 'AdvWorks',
     add_to_model = True,
    #workspace = '',
    #lakehouse = '',
    #lakehouse_workspace = ''
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
> A list of columns which exist in the lakehouse but not in the Direct Lake semantic model. If 'add_to_model' is set to True, a printout stating the success/failure of the operation is returned.

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
            dataset = 'AdventureWorks',
            workspace = None,
            destination_lakehouse = 'Lakehouse2',
            destination_workspace = 'Workspace2'
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
            report = 'AdventureWorks',
            export_format = 'PDF',
            #file_name = None,
            #bookmark_name = None,
            #page_name = None,
            #visual_name = None,
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks',
            export_format = 'PDF',
            #file_name = 'Exports\MyReport',
            #bookmark_name = None,
            #page_name = 'ReportSection293847182375',
            #visual_name = None,
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks',
            export_format = 'PDF',
            #page_name = 'ReportSection293847182375',
            #report_filter = "'Product Category'[Color] in ('Blue', 'Orange') and 'Calendar'[CalendarYear] <= 2020",
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks',
            export_format = 'PDF',
            #page_name = ['ReportSection293847182375', 'ReportSection4818372483347'],
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.export_report(
            report = 'AdventureWorks',
            export_format = 'PDF',
            #page_name = ['ReportSection293847182375', 'ReportSection4818372483347'],
            #visual_name = ['d84793724739', 'v834729234723847'],
            #workspace = None
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
> **page_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of the report page.
>
> **visual_name** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The name (GUID) of a visual. If you specify this parameter you must also specify the page_name parameter.
>
> **report_filter** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; A report filter to be applied when exporting the report. Syntax is user-friendly. See above for examples.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the report resides.
>
### Returns
> A printout stating the success/failure of the operation.

---
## generate_embedded_filter
#### Runs a DAX query against a semantic model.
```python
import fabric_cat_tools as fct
fct.generate_embedded_filter(
            filter = "'Product'[Product Category] = 'Bikes' and 'Geography'[Country Code] in (3, 6, 10)"       
            )
```
### Parameters
> **filter** [str](https://docs.python.org/3/library/stdtypes.html#str)
### Returns
> A string converting the filter into an [embedded filter](https://learn.microsoft.com/power-bi/collaborate-share/service-url-filters)

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
            dataset = 'AdventureWorks',
            #workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''            
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
            dataset = 'AdventureWorks',
            #workspace = None
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
            lakehouse = 'AdventureWorks',
            #workspace = None
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
        lakehouse = 'MyLakehouse',
        ,workspace = '',
        extended = True,
        count_rows = True)
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
>
> **export** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; If specified as True, the resulting dataframe will be exported to a delta table in your lakehouse.
### Returns
> A pandas dataframe showing the delta tables within a lakehouse and their properties.

---
## get_measure_dependencies
#### Shows all dependencies for all measures in a semantic model
```python
import fabric_cat_tools as fct
fct.get_measure_dependencies(
            dataset = 'AdventureWorks',
            #workspace = None
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
## get_model_calc_dependencies
#### Shows all dependencies for all objects in a semantic model
```python
import fabric_cat_tools as fct
fct.get_model_calc_dependencies(
            dataset = 'AdventureWorks',
            #workspace = None
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
> A pandas dataframe showing all dependencies for all objects in the semantic model.

---
## get_object_level_security
#### Shows a list of columns used in object level security.
```python
import fabric_cat_tools as fct
fct.get_object_level_security(
        dataset = 'AdventureWorks',
        workspace = '')
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The semantic model name.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A pandas dataframe showing the columns used in object level security within a semantic model.

---
## get_report_json
#### Gets the report.json file content of a Power BI report.
```python
import fabric_cat_tools as fct
fct.get_report_json(
            report = 'MyReport',
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_report_json(
            report = 'MyReport',
            #workspace = None,
            save_to_file_name = 'MyFileName'
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
            dataset = 'AdventureWorks',
            #workspace = None
            )
```
```python
import fabric_cat_tools as fct
fct.get_semantic_model_bim(
            dataset = 'AdventureWorks',
            #workspace = None,
            save_to_file_name = 'MyFileName'
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
            lakehouse = '',
            #workspace = '' 
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
          folder_path = '/lakehouse/default/Files/VertipaqAnalyzer',
          file_name = 'Workspace Name-DatasetName.zip'
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
          report = 'MyReport',
          #workspace = None
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
## list_dataflow_storage_accounts
#### Shows the dataflow storage accounts.
```python
import fabric_cat_tools as fct
fct.list_dataflow_storage_accounts()
```
### Parameters
None
### Returns
> A pandas dataframe showing the accessible dataflow storage accounts.
> 
---
## list_direct_lake_model_calc_tables
#### Shows the calculated tables and their respective DAX expression for a Direct Lake model (which has been migrated from import/DirectQuery.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.list_direct_lake_model_calc_tables(
            dataset = 'AdventureWorks',
            #workspace = '' 
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
fct.list_shortcuts(
            lakehouse = 'MyLakehouse',
            #workspace = '' 
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
## list_warehouses
#### Shows the warehouss within a workspace.
```python
import fabric_cat_tools as fct
fct.list_warehouses(
            #workspace = None
            )
```
### Parameters
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace name.
### Returns
> A pandas dataframe showing the warehouses which exist in a given workspace and their properties.

---
## measure_dependency_tree
#### Shows a measure dependency tree of all dependent objects for a measure in a semantic model.
```python
import fabric_cat_tools as fct
fct.measure_dependency_tree(
            dataset = 'AdventureWorks',
            measure_name = 'Sales Amount',
            #workspace = '' 
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
            dataset = 'AdventureWorks',
            new_dataset = 'AdventureWorksDL',
            #workspace = '',
            #new_dataset_workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''
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
            dataset = 'AdventureWorks',
            new_dataset = 'AdventureWorksDL',
            #workspace = '',
            #new_dataset_workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''
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
            dataset = 'AdventureWorks',
            new_dataset = '',
            #workspace = '',
            #new_dataset_workspace = ''
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
            dataset = 'AdventureWorks',
            new_dataset = '',
            #workspace = '',
            #new_dataset_workspace = ''
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
            dataset = 'AdventureWorks',
            new_dataset = 'AdventureWorksDL',
            #workspace = '',
            #new_dataset_workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''
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
            tables = ['Sales', 'Calendar'],
            #lakehouse = None,
            #workspace = None
        )
```
```python
import fabric_cat_tools as fct
fct.optimize_lakehouse_tables(
            tables = None,
            #lakehouse = 'MyLakehouse',
            #workspace = None
        )
```
### Parameters
> **tables** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name(s) of the lakehouse delta table(s) to optimize. If 'None' is entered, all of the delta tables in the lakehouse will be queued to be optimized.
>
> **lakehouse** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Name of the lakehouse.
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
            dataset = 'AdventureWorks',
            #workspace = None
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
    dataset = 'AdventureWorks',
    refresh_type = 'full',
    workspace = None
)
```
```python
import fabric_cat_tools as fct
fct.refresh_semantic_model(
    dataset = 'AdventureWorks',
    tables = ['Sales', 'Geography'],
    workspace = None
)
```
```python
import fabric_cat_tools as fct
fct.refresh_semantic_model(
    dataset = 'AdventureWorks',
    partitions = ["'Sales'[Sales - 2024]", "'Sales'[Sales - 2023]"],
    workspace = None
)
```
```python
import fabric_cat_tools as fct
fct.refresh_semantic_model(
    dataset = 'AdventureWorks',
    tables = ['Geography'],
    partitions = ["'Sales'[Sales - 2024]", "'Sales'[Sales - 2023]"],
    workspace = None
)
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model. If no tables/partitions are specified, the entire semantic model is refreshed.
>
> **tables** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Tables to refresh.
>
> **partitions** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Partitions to refresh. Must be in "'Table'[Partition]" format.
>
> **refresh_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; Type of processing to perform. Options: ('full', 'automatic', 'dataOnly', 'calculate', 'clearValues', 'defragment'). Default value: 'full'.
>
> **retry_count** [int](https://docs.python.org/3/library/stdtypes.html#int)
> 
>> Optional; Number of retry attempts. Default is 0.
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
            report = '',
            dataset = '',
            #report_workspace = '',
            #dataset_workspace = ''
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
            dataset = '',
            new_dataset = '',
            #dataset_workspace = '' ,
            #new_dataset_workspace = '' ,
            #report_workspace = '' 
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
        lakehouse_id = '',
        #workspace = '' 
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
        lakehouse = 'MyLakehouse',
        #workspace = '' 
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
        dataset = 'MyReport',
        #workspace = '' 
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
        dataset_id = '',
        #workspace = '' 
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
        report = 'MyReport',
        #workspace = '' 
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
        report_id = '',
        #workspace = '' 
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
## run_dax
#### Runs a DAX query against a semantic model.
```python
import fabric_cat_tools as fct
fct.run_dax(
            dataset = 'AdventureWorks',
            dax_query = 'Internet Sales',
            user_name = 'FACT_InternetSales',
            #workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **dax_query** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; The DAX query to be executed.
>
> **user_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A pandas dataframe with the results of the DAX query.

---
## run_model_bpa
#### Runs the Best Practice Rules against a semantic model.
```python
import fabric_cat_tools as fct
fct.run_model_bpa(
        dataset = 'AdventureWorks',
        #workspace = None
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
>
> **return_dataframe** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Returns a pandas dataframe instead of the visualization.
>
> **export** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Exports the results to a delta table in the lakehouse.
### Returns
> A visualization showing objects which violate each [Best Practice Rule](https://github.com/microsoft/Analysis-Services/tree/master/BestPracticeRules) by rule category.

---
## show_unsupported_direct_lake_objects
#### Returns a list of a semantic model's objects which are not supported by Direct Lake based on [official documentation](https://learn.microsoft.com/power-bi/enterprise/directlake-overview#known-issues-and-limitations).
```python
import fabric_cat_tools as fct
fct.show_unsupported_direct_lake_objects(
        dataset = 'AdventureWorks',
        #workspace = None
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
## translate_semantic_model
#### Translates names, descriptions, display folders for all objects in a semantic model.
```python
import fabric_cat_tools as fct
fct.translate_semantic_model(
            dataset = 'AdventureWorks',
            languages = ['it_IT', 'fr-FR'],
            #workspace = None
            )
```
### Parameters
> **dataset** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Name of the semantic model.
>
> **languages** [str](https://docs.python.org/3/library/stdtypes.html#str) or [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; [Language code(s)](https://learn.microsoft.com/azure/ai-services/translator/language-support) to translate.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the semantic model resides.
### Returns
> A printout stating the success/failure of the operation.

---
## update_direct_lake_model_lakehouse_connection
#### Remaps a Direct Lake semantic model's SQL Endpoint connection to a new lakehouse.
> [!NOTE]
> This function is only relevant to semantic models in Direct Lake mode.
```python
import fabric_cat_tools as fct
fct.update_direct_lake_model_lakehouse_connection(
            dataset = '',
            #lakehouse = '',
            #workspace = ''
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
            dataset = 'AdventureWorks',
            table_name = 'Internet Sales',
            entity_name = 'FACT_InternetSales',
            #workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''            
            )
```
```python
import fabric_cat_tools as fct
fct.update_direct_lake_partition_entity(
            dataset = 'AdventureWorks',
            table_name = ['Internet Sales', 'Geography'],
            entity_name = ['FACT_InternetSales', 'DimGeography'],
            #workspace = '',
            #lakehouse = '',
            #lakehouse_workspace = ''            
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
## update_item
#### Creates a warehouse in Fabric.
```python
import fabric_cat_tools as fct
fct.update_item(
            item_type = 'Lakehouse',
            current_name = 'MyLakehouse',
            new_name = 'MyNewLakehouse',
            #description = 'This is my new lakehouse',
            #workspace = None
            )
```
### Parameters
> **item_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Required; Type of item to update. Valid options: 'DataPipeline', 'Eventstream', 'KQLDatabase', 'KQLQueryset', 'Lakehouse', 'MLExperiment', 'MLModel', 'Notebook', 'Warehouse'.
>
> **current_name** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Required; Current name of the item.
>
> **new_name** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Required; New name of the item.
>
> **description** [str](https://docs.python.org/3/library/functions.html#str)
> 
>> Optional; New description of the item.
>
> **workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace where the item resides.
### Returns
> A printout stating the success/failure of the operation.

---
## vertipaq_analyzer
#### Extracts the vertipaq analyzer statistics from a semantic model.
```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks',
        #workspace = '',
        export = None
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks',
        #workspace = '',
        export = 'zip'
        )
```

```python
import fabric_cat_tools as fct
fct.vertipaq_analyzer(
        dataset = 'AdventureWorks',
        #workspace = '',
        export = 'table'
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
>
> **lakehouse_workspace** [str](https://docs.python.org/3/library/stdtypes.html#str)
> 
>> Optional; The workspace in which the lakehouse used by a Direct Lake semantic model resides.
>
> **read_stats_from_data** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
> 
>> Optional; Setting this parameter to true has the function get Column Cardinality and Missing Rows using DAX (Direct Lake semantic models achieve this using a Spark query to the lakehouse).
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
        dataset = 'AdventureWorks',
        perspective = 'WarmCache',
        add_dependencies = True,
        #workspace = None
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
        dataset = 'AdventureWorks',
        #workspace = None
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

# fabric_cat_tools.TOM Functions
## add_calculated_column
#### Adds a calculated column to a table within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_calculated_column(
)
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table where the column will be added.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the calculated column.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The DAX expression for the calculated column.
>
> **data_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The data type of the calculated column.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The formats strinf for the column.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the column to be hidden if True. Default value: False.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the column.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The display folder for the column.
>
> **data_category** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The data category of the column.
>
> **key** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Marks the column as the primary key of the table. Default value: False.
>
> **summarize_by** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Sets the value for the Summarize By property of the column.
>
### Returns
> 

---
## add_calculated_table
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_calculated_table(
```
### Parameters
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The DAX expression for the table.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the table.
>
> **data_category** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The data category of the table.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the table to be hidden if True. Default value: False.
>
### Returns
> A printout...

---
## add_calculated_table_column
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_calculated_table_column(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the column will reside.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column.
>
> **source_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The source column for the column.
>
> **data_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The data type of the column.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The format string of the column.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the column to be hidden if True. Default value: False.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the column.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The display folder for the column.
>
> **data_category** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The data category of the column.
>
> **key** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Marks the column as the primary key of the table. Default value: False.
>
> **summarize_by** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Sets the value for the Summarize By property of the column.
>
### Returns
> A printout...

---
## add_calculation_group
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_calculation_group(
```
### Parameters
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
> **precedence** [int](https://docs.python.org/3/library/stdtypes.html#int)
>
>> Optional;
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional;
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the calculation group to be hidden if True. Default value: False.
>
### Returns
> A printout...

---
## add_calculation_item
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_calculation_item(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
> **calculation_item_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
> **ordinal** [int](https://docs.python.org/3/library/stdtypes.html#int)
>
>> Optional;
>
> **format_string_expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional;
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional;
>
### Returns
> A printout...

---
## add_data_column
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_data_column(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the column will exist.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column.
>
> **source_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column in the source.
>
> **data_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The data type of the column.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The format string of the column.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the column to be hidden if True. Default value: False.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the column.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The display folder for the column.
>
> **data_category** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The data category of the column.
>
> **key** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Marks the column as the primary key of the table. Default value: False.
>
> **summarize_by** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Sets the value for the Summarize By property of the column.
>
### Returns
> A printout...

---
## add_entity_partition
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_entity_partition(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which to place the entity partition.
>
> **entity_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the lakehouse table.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The expression to use for the partition. This defaults to using the existing 'DatabaseQuery' expression within the Direct Lake semantic model.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the partition.
>
### Returns
> A printout...

---
## add_expression
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_expression(
```
### Parameters
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the expression.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The M-code encapsulating the logic for the expression.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the expression.
>
### Returns
> A printout...

---
## add_field_parameter
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_field_parameter(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the field parameter.
>
> **objects** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; A list of columns/tables to place in the field parameter. Columns must be fully qualified (i.e. "'Table Name'[Column Name]" and measures must be unqualified (i.e. "[Measure Name]").
>
### Returns
> A printout...

---
## add_hierarchy
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_hierarchy(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the hierarchy will reside.
>
> **hierarchy_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the hierarchy.
>
> **columns** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; A list of columns to use in the hierarchy. Must be ordered from the top of the hierarchy down (i.e. ["Continent", "Country", "City"]).
>
> **levels** [list](https://docs.python.org/3/library/stdtypes.html#list) of [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; A list of levels to use in the hierarchy. These will be the displayed name (instead of the column names). If omitted, the levels will default to showing the column names.
>
> **hierarchy_description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the hierarchy.
>
> **hierarchy_hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the hierarchy to be hidden if True. Default value: False.
>
### Returns
> A printout...

---
## add_m_partition
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_m_partition(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the partition will reside.
>
> **partition_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the M partition.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The M-code encapsulating the logic of the partition.
>
> **mode** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The storage mode for the partition. Default value: 'Import'.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the partition.
>
### Returns
> A printout...

---
## add_measure
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_measure(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the measure will reside.
>
> **measure_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the measure.
>
> **expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The DAX expression encapsulating the logic of the measure.
>
> **format_string** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The format string of the measure.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Sets the measure to be hidden if True. Default value: False.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the measure.
>
> **display_folder** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The display folder for the measure.
>
### Returns
> A printout...

---
## add_perspective
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_perspective(
```
### Parameters
> **perspective_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the perspective.
>
### Returns
> A printout...

---
## add_relationship
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_relationship(
```
### Parameters
> **from_table** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table on the 'from' side of the relationship.
>
> **from_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column on the 'from' side of the relationship.
>
> **to_table** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table on the 'to' side of the relationship.
>
> **to_column** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column on the 'to' side of the relationship.
>
> **from_cardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The cardinality of the 'from' side of the relationship. Options: ['Many', 'One', 'None'].
>
> **to_cardinality** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The cardinality of the 'to' side of the relationship. Options: ['Many', 'One', 'None'].
>
> **cross_filtering_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Setting for the cross filtering behavior of the relationship. Options: ('Automatic', 'OneDirection', 'BothDirections'). Default value: 'Automatic'.
>
> **is_active** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; Setting for whether the relationship is active or not. Default value: True.
>
> **security_filtering_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; Setting for the security filtering behavior of the relationship. Options: ('None', 'OneDirection', 'BothDirections'). Default value: 'OneDirection'.
>
> **rely_on_referential_integrity** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional; ; Setting for the rely on referential integrity of the relationship. Default value: False.
>
### Returns
> A printout...

---
## add_role
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_role(
```
### Parameters
> **role_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the role.
>
> **model_permission** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The [model permission](https://learn.microsoft.com/dotnet/api/microsoft.analysisservices.tabular.modelpermission?view=analysisservices-dotnet) of the role. Default value: 'Reader'.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The description of the role.
>
### Returns
> A printout...

---
## add_table
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_table(
```
### Parameters
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table.
>
> **description** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The descrition of the table.
>
> **data_category** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Optional; The data category of the table.
>
> **hidden** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Optional;  Sets the table to be hidden if True. Default value: False.
>
### Returns
> A printout...

---
## add_to_perspective
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_to_perspective(
```
### Parameters
> **object**
>
>> Required;
>
> **perspective_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the perspective.
>
### Returns
> A printout...

---
## add_translation
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.add_translation(
```
### Parameters
> **language** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The [language code](https://learn.microsoft.com/azure/ai-services/translator/language-support) to add to the semantic model.
>
### Returns
> A printout...

---
## all_calculation_items
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_calculation_items(
```
### Parameters
None
### Returns
> A printout...

---
## all_columns
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_columns(
```
### Parameters
None
### Returns
> A printout...

---
## all_hierarchies
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_hierarchies(
```
### Parameters
None
### Returns
> A printout...

---
## all_levels
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_levels(
```
### Parameters
None
### Returns
> A printout...

---
## all_measures
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_measures(
```
### Parameters
None
### Returns
> A printout...

---
## all_partitions
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_partitions(
```
### Parameters
None
### Returns
> A printout...

---
## all_rls
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.all_rls(
```
### Parameters
None
### Returns
> A printout...

---
## cardinality
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.cardinality(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## clear_annotations
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.clear_annotations(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## clear_extended_properties
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.clear_extended_properties(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## data_size
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.data_size(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## depends_on
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.depends_on(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies** Pandas dataframe
>
>> Required;
>
### Returns
> A printout...

---
## dictionary_size
#### Obtains the 
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.dictionary_size(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## fully_qualified_measures
#### Shows all fully-qualified measures referenced by a given measure's DAX expression.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.fully_qualified_measures(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies**
>
>> Required;
>
### Returns
> A printout...

---
## get_annotation_value
#### Obtains the annotation value for a given object's annotation in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.get_annotation_value(
```
### Parameters
> **object**
>
>> Required;
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the annotation.
>
### Returns
> A printout...

---
## get_annotations
#### Obtains all of the annotations for a given object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.get_annotations(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## get_extended_properties
#### Obtains all of the extended properties for a given object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.get_extended_properties(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## get_extended_property_value
#### Obtains the extended property value for an object's extended property.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.get_extended_property_value(
```
### Parameters
> **object**
>
>> Required;
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the extended property.
>
### Returns
> A printout...

---
## in_perspective
#### Identifies whether an object is in a given perspective.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.in_perspective(
```
### Parameters
> **object**
>
>> Required;
>
> **perspective_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
### Returns
> A printout...

---
## is_direct_lake
#### Identifies whether a semantic model is in Direct Lake mode.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.is_direct_lake(
```
### Parameters
None
### Returns
> True/False

---
## is_field_parameter
#### Identifies whether a table is a field parameter.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.is_field_parameter(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
### Returns
> True/False

---
## records_per_segment
#### Obtains the records per segment of a partition within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.records_per_segment(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## referenced_by
#### Shows the objects referenced by a given object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.referenced_by(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies**
>
>> Required;
>
### Returns
> A printout...

---
## remove_annotation
#### Removes the annotation from an object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_annotation(
```
### Parameters
> **object**
>
>> Required;
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the annotation.
>
### Returns
> A printout...

---
## remove_extended_property
#### Removes the extended property from an object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_extended_property(
```
### Parameters
> **object**
>
>> Required;
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the extended property.
>
### Returns
> A printout...

---
## remove_from_perspective
#### Removes an object (table, column, measure or hierarchy) from a perspective.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_from_perspective(
```
### Parameters
> **object**
>
>> Required;
>
> **perspective_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
### Returns
> A printout...

---
## remove_object
#### Removes an object from a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_object(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## remove_translation
#### Removes a translation for an object in a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_translation(
```
### Parameters
> **object**
>
>> Required;
>
> **language** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The [language code](https://learn.microsoft.com/azure/ai-services/translator/language-support).
>
### Returns
> A printout...

---
## remove_vertipaq_annotations
#### Removes the annotations set using the [set_vertipaq_annotations] function.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.remove_vertipaq_annotations(
```
### Parameters
None
### Returns
> A printout...

---
## row_count
#### Obtains the row count of a table or partition within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.row_count(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## set_annotation
#### Sets an annotation on an object within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_annotation(
```
### Parameters
> **object**
>
>> Required;
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The annotation name.
>
> **value** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The annotation value.
>
### Returns
> A printout...

---
## set_direct_lake_behavior
#### Sets the 'DirectLakeBehavior' property for a Direct Lake semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_direct_lake_behavior(
```
### Parameters
> **direct_lake_behavior** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The [DirectLakeBehavior](https://learn.microsoft.com/dotnet/api/microsoft.analysisservices.tabular.directlakebehavior?view=analysisservices-dotnet) value.
>
### Returns
> A printout...

---
## set_extended_property
#### Sets an extended property on an object within the semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_extended_property(
```
### Parameters
> **object**
>
>> Required;
>
> **extended_property_type** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The type of extended property to set. Options: ['Json', 'String'].
>
> **name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the extended property.
>
> **value** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The value of the extended property.
>
### Returns
> A printout...

---
## set_is_available_in_mdx
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_is_available_in_mdx(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the column resides.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column.
>
> **value** [bool](https://docs.python.org/3/library/stdtypes.html#bool)
>
>> Required; The value to set for the [IsAvailableInMDX](https://learn.microsoft.com/dotnet/api/microsoft.analysisservices.tabular.column.isavailableinmdx?view=analysisservices-dotnet#microsoft-analysisservices-tabular-column-isavailableinmdx) property.
>
### Returns
> A printout...

---
## set_ols
#### Sets object level security for a given role/column within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_ols(
```
### Parameters
> **role_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the role.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column.
>
> **permission** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required;
>
### Returns
> A printout...

---
## set_rls
#### Sets the row level security expression for a given role/table within a semantic model.
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_rls(
```
### Parameters
> **role_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the role.
>
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table to place row level security.
>
> **filter_expression** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The DAX expression containing the row level security logic.
>
### Returns
> A printout...

---
## set_summarize_by
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_summarize_by(
```
### Parameters
> **table_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the table in which the column resides.
>
> **column_name** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The name of the column.
>
> **value** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The summarize by property of the column.
>
### Returns
> A printout...

---
## set_translation
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_translation(
```
### Parameters
> **object**
>
>> Required;
>
> **language** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The [language code](https://learn.microsoft.com/azure/ai-services/translator/language-support) in which to translate the object property.
>
> **property** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The property to translate. One of the following values: ['Name', 'Description', 'Display Folder'].
>
> **value** [str](https://docs.python.org/3/library/stdtypes.html#str)
>
>> Required; The translation value.
>
### Returns
> A printout...

---
## set_vertipaq_annotations
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.set_vertipaq_annotations(
```
### Parameters
None
### Returns
> A printout...

---
## total_size
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.total_size(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## unqualified_columns
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.unqualified_columns(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_calc_item
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_calc_item(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_hierarchies
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_hierarchies(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_levels
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_levels(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_relationships
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_relationships(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_rls
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_rls(
```
### Parameters
> **object**
>
>> Required;
>
> **dependencies**
>
>> Required;
>
### Returns
> A printout...

---
## used_in_sort_by
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_in_sort_by(
```
### Parameters
> **column**
>
>> Required;
>
### Returns
> A printout...

---
## used_size
####
```python
import fabric_cat_tools as fct
from fabric_cat_tools.TOM import connect_semantic_model

with connect_semantic_model(dataset='', workspace=None, readonly=False) as tom:
	tom.used_size(
```
### Parameters
> **object**
>
>> Required;
>
### Returns
> A printout...




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
