# TDM Database

TDM settings and TDM tasks are kept in a dedicated PostgreSQL DB. The TDM APIs and task execution processes connect to the TDM DB to get or update TDM settings or tasks.

The following table lists the TDM tables and their description.

<table width="900pxl">
<tbody>
<tr>
<td valign="top" width="200pxl"><strong>Table Name</strong></td>
<td valign="top" width="400pxl"><strong>Description</strong></td>
<td valign="top" width="300pxl"><strong>Table Category</strong></td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>permission_groups_mapping</td>
<td valign="top" width="400pxl">
        <p>Mapping of <a href="/articles/17_fabric_credentials/02_fabric_credentials_commands.md#create-role">Fabric roles</a> to TDM permission groups (admin, owner or tester).</p>
        <p>The relationship between Fabric roles and TDM permission groups is many-to-one.</p>
        <p><a href="/articles/TDM/tdm_gui/02_tdm_gui_user_types.md">Click for more about the TDM permission groups.</a></p>
    </td>
<td valign="top" width="300pxl">TDM Permission Groups (User Types)</td>
</tr>
<tr>    
<tr>
<td valign="top" width="200pxl"><h4>business_entities</td>
<td valign="top" width="400pxl">Business Entities list.</td>
<td valign="top" width="300pxl">Business Entity</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_lu_type_relation_eid</td>
<td valign="top" width="400pxl"><p>TDM relationships table. This table maps the source parent Entity ID to its source children Entity IDs per source environment. For example, Customer 1 has orders 56, 63 and 73 in the Production environment. This table is populated by a sync of the parent LU and is used to build the entities list of the children LUs during Load (copy) tasks.</p>
  <p><a href="/articles/TDM/tdm_implementation/06_tdm_implementation_support_hierarchy.md#tdm_lu_type_relation_eid">Click for more information about tdm_lu_type_relation_eid table.</a></p>  
  </td>
<td valign="top" width="300pxl">Business Entity</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_lu_type_rel_tar_eid</td>
<td valign="top" width="400pxl"><p>TDM relationship table for target IDs. This table maps the target parent Entity ID to its target children Entity IDs per target environment and is populated by a sync of the parent LU. The table is used to build the entities list of the children LUs for <strong>Delete and load entity</strong> or <strong>Delete entity without load</strong> tasks when the TDM task deletes parent entities and their related data from a target environment.</p>
  <p><a href="/articles/TDM/tdm_implementation/06_tdm_implementation_support_hierarchy.md#tdm_lu_type_rel_tar_eid">Click for more information about tdm_lu_type_rel_tar_eid.</a></p>
</td>
<td valign="top" width="300pxl">Business Entity</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>[LU_NAME]_params</td>
<td valign="top" width="400pxl"><p>Parameters table. Contains the list of all entities migrated into Fabric per LU. Each combination of an entity and a source environment has a specific record that holds the Entity ID (IID), source environment name and the list of parameters defined for the LU. For example, Customer Type. This table is created by a Fabric sync on each LU and is used to support a random selection and to select by parameters task selection methods.</p>
 <p><a href="/articles/TDM/tdm_implementation/07_tdm_implementation_parameters_handling.md">Click for more information about parameters handling.</a></p>
</td>
<td valign="top" width="300pxl">Business Entity</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_be_post_exe_process</td>
<td valign="top" width="400pxl">List of <a href = "/articles/TDM/tdm_gui/04_tdm_gui_business_entity_window.md#post-execution-processes-tab">post-execution processes</a> attached to each Business Entity. A post-execution process is executed at the end of the task execution process. For example, sending a mail to a user.</td>
<td valign="top" width="300pxl">Business Entity</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>product_logical_units</td>
<td valign="top" width="400pxl">
<ul>
<li>Maps a list of LUs in each Business Entity.</li>
<li>Maps the relationship of the LUs in a Business Entity.</li>
<li>Maps the link of the combined Business Entity and LU to a system (product).</li>
</ul>
  <p><a href="/articles/TDM/tdm_gui/06_be_product_tdmdb_tables.md#product_logical_units">Click for more information about this table.</a></p>  
</td>
<td valign="top" width="300pxl">Business Entity/System</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>products</td>
  <td valign="top" width="400pxl"><a href = "/articles/TDM/tdm_gui/05_tdm_gui_product_window.md">Products</a> (applications) list.</td>
<td valign="top" width="300pxl">Systems</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>environments</td>
<td valign="top" width="400pxl">TDM <a href="/articles/TDM/tdm_gui/07_tdm_gui_environment_overview.md">source and target environments</a>. Each record contains the environment name, environment type (source, target or both), and the environment name in Fabric.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>environment_owners</td>
<td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/08_environment_window_general_information.md#environment-owners">environment owner users</a> of each TDM environment.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>environment_products</td>
<td valign="top" width="400pxl">List of products (applications) attached to each <a href="/articles/TDM/tdm_gui/11_environment_products_tab.md">environment</a>. The connection details of an environment's interfaces are defined and saved in Fabric.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>environment_roles</td>
<td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/10_environment_roles_tab.md">roles and their permissions</a> per TDM environment.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>environment_role_users</td>
<td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/10_environment_roles_tab.md#testers">users attached to a role</a>.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_env_globals</td>
  <td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/12_environment_globals_tab.md">Global parameters</a> set on an environment level.</td>
<td valign="top" width="300pxl">TDM Environments</td>
</tr>
<tr>    
<td valign="top" width="200pxl"><h4>tdm_reserved_entities</td>
<td valign="top" width="400pxl"><a href="/articles/TDM/tdm_architecture/08_entity_reservation.md">Reserved Entities List.</a></td>
<td valign="top" width="300pxl">Reserved Entities</td>
</tr>    
<tr>
<td valign="top" width="200pxl"><h4>tasks</td>
  <td valign="top" width="400pxl"><a href="/articles/TDM/tdm_gui/25_task_tdmdb_tables.md#tasks">Tasks list</a>.</td>
<td valign="top" width="300pxl">Task</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_globals</td>
<td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/23_task_globals_tab.md">Global parameters set on a task level</a>.</td>
<td valign="top" width="300pxl">Task</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_ref_tables</td>
  <td valign="top" width="400pxl">List of <a href="/articles/TDM/tdm_gui/24_task_reference_tab.md">Reference tables</a> included in each TDM task.</td>
<td valign="top" width="300pxl">Task</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tasks_logical_units</td>
<td valign="top" width="400pxl">List of LUs included in each TDM task.</td>
<td valign="top" width="300pxl">Task</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_generate_task_field_mappings</td>
<td valign="top" width="400pxl">The data generation parameters of Generate tasks.</td> 
<td valign="top" width="300pxl">Task</td>
</tr>      
<tr>
<td valign="top" width="200pxl"><h4>task_exe_error_detailed</td>
<td valign="top" width="400pxl">TDM Execution detailed error table.</td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_execution_entities</td>
  <td valign="top" width="400pxl"><p>Detailed list of entities and the execution status of each task's execution.</p>
    <p>This table is used to generate the <a href="03a_task_execution_building_entity_list_on_tasks_LUs.md">entity list of the children LU of a task execution</a>.</p>
    <p>This table is also copied and stored in the <a href="/articles/TDM/tdm_implementation/04_fabric_tdm_library.md#tdm-lu">TDM LU</a> to display the <a href="/articles/TDM/tdm_gui/27_task_execution_history.md#task-execution---detailed-statistics">list of copied and failed entities and Reference tables </a> of the task execution.</p></td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_execution_list</td>
<td valign="top" width="400pxl">Holds the list of execution requests for each task's execution. A separate record is created for each LU and post-execution process.&nbsp;</td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_execution_override_attrs</td>
<td valign="top" width="400pxl">List of execution parameters - like environments or Globals - to be overridden on a given task execution.</p>
   <p>The list of the overridden parameters is concatenated into a JSON file and populated in the override_parameters column. </p>
   <p>For example: {"SOURCE_ENVIRONMENT_NAME":"ENV3","TARGET_ENVIRONMENT_NAME":"ENV3"}</td> 
<td valign="top" width="300pxl">Task Execution</td>        
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_execution_summary</td>
<td valign="top" width="400pxl">Summary information of each task's execution. A record is created for each task's execution.</td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_ref_exe_stats</td>
<td valign="top" width="400pxl">List of <a href="05_tdm_reference_processes.md#tdm-lu---tdmcopyreftablesfortdm-job">Reference tables</a> to be processed by the execution of a given task.</td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tasks_post_exe_process</td>
<td valign="top" width="400pxl">List of post-execution processes to be executed for each task's execution.</td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_seq_mapping</td>
  <td valign="top" width="400pxl"><p>Mapping of source and target sequences.</p>
    <p><a href="/articles/19_Broadway/actors/08_sequence_implementation_guide.md">Click for more information about sequence implementation</a>.</p></td>
<td valign="top" width="300pxl">Task Execution</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>task_exe_stats_detailed</td>
<td valign="top" width="400pxl">Detailed statistics of each task's execution.</td>
<td valign="top" width="300pxl">Task Execution Statistics</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>activities</td>
<td valign="top" width="400pxl">TDM activities log. A new record is created for each TDM activity, specifying its date, time, user, type (create or update), impacted TDM component and description.  </td>
<td valign="top" width="300pxl">TDM Activities</td>
</tr>
<tr>
<td valign="top" width="200pxl"><h4>tdm_general_parameters</td>
<td valign="top" width="400pxl"><a href="/articles/TDM/tdm_configuration/02_tdmdb_general_parameters.md">TDM general parameters.</a></td>
<td valign="top" width="300pxl">General TDM Parameters</td>
</tr>
</tbody>
</table>









[![Previous](/articles/images/Previous.png)](01_tdm_architecture.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](03_task_execution_processes.md)
