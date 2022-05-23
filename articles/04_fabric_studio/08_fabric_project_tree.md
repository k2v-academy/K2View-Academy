# Fabric Project Tree

A Fabric project has a tree-like structure. Known as the **Project Tree**, it displays components in a hierarchical order. Each entity in the tree initiates a different action.

The **Project Tree** is displayed on the left side of the Fabric Studio window.

To initiate an action, right click on a component and select the action. For instance, right clicking on Broadway creates a new flow.

<studio>

A current active project in the Studio has its name displayed at the top of the Project Tree, i.e., in the below example, the current active project is Demo_6_5.

![image](../../articles/13_LUDB_viewer_and_studio_debug_capabilities/images/Logical_Units_Tree.png)

[Click for more information about Creating a New Project.](05_creating_a_new_project.md) 


### Project Tree Components

Each project has the following main components: 

* [Shared Objects](/articles/04_fabric_studio/12_shared_objects.md) used by all Logical Units and project references and may include the following sub-branches:
  * [Broadway](/articles/19_Broadway/01_broadway_overview.md)

  * [Database Types](/articles/05_DB_interfaces/03_DB_interfaces_overview.md), [Interfaces](/articles/05_DB_interfaces/01_interfaces_overview.md) 

  * [Java Functions](/articles/07_table_population/08_project_functions.md), [Globals](/articles/08_globals/01_globals_overview.md) 

  * Resources, files that can be saved as part of a project. 

  * Environments 

  * Templates

  * [Translations](/articles/09_translations/01_translations_overview_and_use_cases.md) 


* **Logical Units** - a collection of all [Logical Units](/articles/03_logical_units/01_LU_overview.md) defined in the project.

* **References** - reference information that can be used throughout the LU instances. **References** may include the following sub-branches:

  * Broadway

  * Java, Functions, Globals, Resources

  * [Tables](/articles/07_table_population/01_table_population_overview.md)

  * Translation

  * IID Finder

* **Web Services** - a collection of functions that can be exposed through Fabric’s Web Service layer. **Web Services** may include the following sub-components:

  * Broadway
  * Java
  * Resource files and Graphit objects.

</studio>

<web>

<img src="images/web/project_tree.png" />

Initiating an action may be done by any of the following three methods: 

- right-click on the context menu in the Project Tree 


- using the **Fabric** item (top menu bar)


- via **View > command Palette...** (top menu bar) 

### Project Tree Components

Each project has the following main components (under Project > Implementation): 

* **Logical Units / Data Products** - a collection of all [Logical Units / Data Products](/articles/03_logical_units/01_LU_overview.md) defined in the project. Of this collection, two *system* logical units - that exist by default in any project - are **References** and **Web Services**:
  * **References** - reference information that can be used throughout the logical units, such as [reference common tables](/articles/22_reference(commonDB)_tables/01_fabric_commonDB_overview.md).
  * **[Web Services](/articles/15_web_services_and_graphit/01_web_services_overview.md)** - a collection of functions that can be exposed through Fabric’s Web Service layer. Web Services may include [Java WS](), [Graphit WS]() and supportive [Broadway](/articles/19_Broadway/01_broadway_overview.md) flows.

* **[Shared Objects](/articles/04_fabric_studio/12_shared_objects.md)** - are used by all Logical Units and project references and may include the following sub-branches:
  * Broadway
  * [Interfaces](/articles/05_DB_interfaces/01_interfaces_overview.md)
  * [Custom Interface Types](/articles/05_DB_interfaces/03_DB_interfaces_overview.md)
  * [Java Functions](/articles/07_table_population/08_project_functions.md), [Globals](/articles/08_globals/01_globals_overview.md) 
  * Resources, files that can be saved as part of a project. 

* **lib** - Java library files, required by a project, such as utility JARs or JDBC drivers, that are not provided as part of the product. 

> Note: The *project-resources* folder resides at the project tree is not part of the Fabric project but it is a useful folder you can use at your workspace.

</web>

[Click for more information about UI Components and Menus.](01_UI_components_and_menus.md)

### Project Components Prefix Conventions 

Using a common prefix for each project component improves maintenance throughout a shared implementation.

The following table lists the recommended project component prefixes conventions:

<table>
<tbody>
<tr>
<td width="200">
<p><Strong>Component</Strong></p>
</td>
<td width="250">
<p><Strong>Recommended Prefix</Strong></p>
</td>
</tr>
<tr>
<td width="166">
<p>Function</p>
</td>
<td width="136">
<p>fn%</p>
</td>
</tr>
<tr>
<td width="166">
<p>Input Parameter</p>
</td>
<td width="136">
<p>i_%</p>
</td>
</tr>
<tr>
<td width="166">
<p>Output Parameters</p>
</td>
<td width="136">
<p>o_%</p>
</td>
</tr>
<tr>
<td width="166">
<p>Web Services</p>
</td>
<td width="136">
<p>ws%</p>
</td>
</tr>
<tr>
<td width="166">
<p>Table Population</p>
</td>
<td width="136">
<p>pop%</p>
</td>
</tr>
<tr>
<td width="166">
<p>Instance Group</p>
</td>
<td width="136">
<p>Ig%</p>
</td>
</tr>
</tbody>
</table>


Note that when using the above prefix conventions, it is also recommended to use meaningful names for the project’s components.

<studio>

[![Previous](/articles/images/Previous.png)](05_creating_a_new_project.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](06_adding_fabric_projects_to_version_control.md)

</studio>

<web>

[![Previous](/articles/images/Previous.png)](05_creating_a_new_project.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](11_fabric_studio_exporting_and_importing%20a_fabric_project.md.md)

</web>

