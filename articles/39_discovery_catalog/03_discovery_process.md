<web>

# E2E Discovery Process

The K2View Discovery process is depicted in the below diagram and it includes the following major steps:

* Define an interface for a given data source and initiate the Discovery job (Crawler) in the Web Studio.
* The Crawler scans the data source, while identifying the existing entities and the relationships between them. The Crawler's output is the Discovery Schema.
* Next, a Plugin Framework is triggered automatically upon the Crawler completion. The Plugin Framework is a platform for executing predefined rules (plugins) and for enhancing the Discovery Schema accordingly. Examples of business rules are: 
  * Creating a link (relation) between 2 objects.
  * Profiling the field's data and categorizing it (e.g. email, phone, gender).
  * Determining whether a field should be considered a PII.


* Upon the Plugin Framework execution completion, the Discovery Schema is saved into the *neo4j* Graph DB. 

  * The Discovery Schema supports versioning. A new version is created when the Discovery job is executed and changes from the previous version are found.
* Once the process is completed, the Logical Unit schema can be created based on the process results.

![](images/DiscoveryE2E.png)



[![Previous](/articles/images/Previous.png)](02_catalog_vocabulary.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](04_plugin_framework.md) 

</web>
