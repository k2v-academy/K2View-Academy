<web>

# Catalog Application

### Overview

The Catalog is accessible from the [K2View Web Framework](/articles/30_web_framework/01_web_framework_overview.md) by selecting the **Catalog** application from the context menu. Upon opening, the application displays the data from *neo4j* Graph DB and it allows navigating from one level to another through a data model’s graph, expanding and/or collapsing various elements (nodes), searching for nodes, viewing their properties, and more.

The Catalog application includes the following parts, described in this article:

* [Main area](05_catalog_app.md#main-area), which displays the Catalog tree.
* [Menu bar](05_catalog_app.md#menu-bar), which allows to perform various activities. 
* [Properties tab](05_catalog_app.md#properties-tab), which displays the properties of the selected node or relation.

Additionally, this article includes the description of the Catalog's [deep linking](05_catalog_app.md#deep-linking) mechanism and the [Classifier Configuration screen](05_catalog_app.md#classifier-configuration).

### Main Area

**General Navigation**

The Catalog's main area enables navigation between different hierarchy levels, by expanding and collapsing various elements.

The initial view displays the Data Platform nodes (the data source interfaces defined in the Fabric project), for which the Discovery process is performed. In case the Discovery process hasn't been executed on any project interface, the main area would be empty. 

The Legend presents 3 types of nodes with their respective icons. 

<img src="images/catalog_app.png" style="zoom:75%;" />

**Catalog's Version**

When the catalog application opens, the latest **catalog version** is displayed by default. The version number is displayed in the upper-left corner of the main area. By clicking it, you can either: 

* Select another version from the drop-down list for viewing.
* Click the compare <img src="images/compare.png" style="zoom:75%;" /> icon to perform a versions comparison analysis.  

[Click here for more information regarding the Catalog Versioning](06_catalog_versioning.md).

**Data Platform and Schema's Context Menu**

Clicking on any Data Platform or Schema node opens the context menu, which allows performing the following actions:

<img src="images/dataplatform_collapsed_expanded.png" style="zoom: 67%;" />

* **Expand** <img src="images/expand.png" style="zoom:80%;" />or **Collapse** <img src="images/collapse.png" style="zoom:80%;" /> the next level elements. 
  
  * For example, clicking the <img src="images/expand.png" style="zoom:80%;" /> icon of the Data Platform expands all of its Schemas. 
  * A double-click on a selected node can either expand or collapse it.
  
* **Hide** <img src="images/hide.png" style="zoom:80%;" /> an element from the window. A hidden element can be unhidden either from the Actions menu (as explained further in this article) or by reloading the Catalog.

* **Focus** <img src="images/focus.png" style="zoom:80%;" /> on the next level elements. The difference between the Expand and Focus actions is that Focus dives into the next hierarchy level, eliminating other nodes from the screen.
  
  * For example, when<img src="images/focus.png" style="zoom:80%;" />is clicked on a Schema node, the Catalog will only display the Dataset nodes of the selected Schema. 
  
  * In the Focus view, the breadcrumbs are displayed in the upper-left corner of the main area, indicating your path within the Catalog tree. The breadcrumbs are clickable, which allows navigating up the tree.
  

<img src="images/breadcrumbs.png" style="zoom: 67%;" />

**Dataset Context Menu**

Clicking on any Dataset node opens its context menu, which includes the following actions:

* **Expand** <img src="images/expand.png" style="zoom:80%;" /> Dataset fields:

  * Click the <img src="images/expand.png" style="zoom:80%;" /> icon of the selected Dataset node to expand its fields. The Dataset node then changes its shape from a circle to a rectangle and displays field properties such as PK, FK and PII where applicable.

    ​	<img src="images/dataset_collapsed_expanded.png" style="zoom: 67%;" />

  * To simultaneously expand all Datasets on the screen, click the <img src="images/expand-fields.png" style="zoom:75%;" /> icon on the Catalog's legend:

    ​	<img src="images/legend.png" style="zoom: 67%;" />

  * To collapse an expanded Dataset, click the three dots in the corner of the node. To do so for all Dataset nodes together, click the <img src="images/eye.png" alt="." style="zoom:80%;" /> icon in the Catalog's legend.

* **Hide** <img src="images/hide.png" style="zoom:80%;" /> an element from the window.

### Menu Bar

The menu bar is a toolbar located at the top of the window. It includes the following choices:

* The **Actions** menu allows to:
  * **Edit** the catalog manually. [Click here for more information regarding the Manual Overrides](07_manual_overrides.md).
  * Open the **Classifier Configuration** screen, in order to update the profiling rules. This screen is described [further in this article](05_catalog_app.md#classifier-configuration). 
  * View and unhide the **hidden nodes**. Selecting a node from this list returns it back to the Catalog tree.
* **Search** <img src="images/search.png" style="zoom:80%;" />the catalog. [Click here for more information regarding the Catalog Search](08_search_catalog.md). 
* **Expand**, **collapse** and **hide**, triggering the same activities as using the node's context menu. Multiple element selection is supported.  
* **Layout selection** <img src="images/layout.png" style="zoom:80%;" />, selecting the Catalog layout. Centered (default), vertical or horizontal layouts are supported.
* **Navigation map** <img src="images/navigation.png" style="zoom:80%;" />, opening the Catalog's mini-map and navigation panel. 
* **Zoom in / out**, adjusting the zoom of the view.

### Properties Tab

The Properties Tab displays the selected element's name, the icon of the type and the element's properties.

​	<img src="images/properties.png" style="zoom: 67%;" />

Each element has different properties. For example, a FIELD has properties such as Column Size and Source Data Type identified by the Crawler, and PII and Classification identified by the plugins.

Clicking the property name or the <img src="C:\K2View-Academy\articles\39_fabric_catalog\images\info.png" style="zoom:80%;"/> icon next to the element's name opens the More Info pop-up window, providing more details about the property. For example, the property's Origin, which can be the Crawler, one of the plugins or manual.

When the selected element is a relation (link) between two objects in the Catalog tree, the relation properties are displayed. Note that in case of more than one *refers_to* relations between two datasets, the Catalog tree displays one link only. However the Properties Tab displays the details of all relations as shown below:

<img src="images/properties_two_links.png" style="zoom: 75%;" />

### Deep Linking

The Catalog application supports deep linking from the data platform to the field level. When navigating the Catalog tree and clicking the nodes, the path to the node is added to the application URL using the following format:

~~~
/app/catalog/<version>/<data platform>/<schema>/<dataset>/<field>
~~~

The version should be either the word **latest** or **V** with the version number (e.g. V13).

This link can be shared as it sends another user straight to a specific in-app location, saving time and energy while trying to locate a particular node.

### Classifier Configuration

The Classifier Configuration pop-up screen allows to view and update the profiling rules that are used by the Catalog Classification built-in plugins (click [here](04_plugin_framework.md#built-in-plugins) to get more details about these plugins).

The rules are saved in the Discovery/MTable folder in the project tree.

​	<img src="images/classifier.png" style="zoom: 67%;" />







[![Previous](/articles/images/Previous.png)](04a_catalog_integration_with_fabric.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](06_catalog_versioning.md) 

</web>