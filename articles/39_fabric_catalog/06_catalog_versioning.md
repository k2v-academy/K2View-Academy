<web>

# Catalog Versioning

The Catalog supports **versioning** - ability to create a new Catalog version in the  *neo4j* Graph DB every time the Discovery process runs and finds differences comparing to the previous version.

Then, using the Catalog application a user can view each version separately or check the differences between two selected versions, as described below.

Note that if the Discovery process doesn't identify any changes in the data source or in the plugins settings, a new version is not created.

Additional trigger for version creation is editing of the catalog manually. [Click for more information about the manual overrides](07_manual_overrides.md).

### Version View

By default, the Catalog displays the latest version. To view any version, select a version number from the list: 

<img src="images/versions.png" style="zoom:75%;" />

The coloring scheme of the standard view is blue. 

### Version Comparison

To compare two versions, click the comparison <img src="images/compare.png" style="zoom:75%;" /> icon in the version's drop-down list. 

The differences between the two versions are indicated using the colors, as follows:
* The new elements are green, the removed elements are red, and the updated elements are blue.
* When a property is updated, it is displayed twice –  the new value is highlighted by green, the removed one is red.
* All unchanged entities and relations are grey.

To return to the regular view mode, select a version from the list.





[![Previous](/articles/images/Previous.png)](05_catalog_app.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](07_manual_overrides.md) 

</web>