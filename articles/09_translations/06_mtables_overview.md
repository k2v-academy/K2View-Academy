# MTable Overview

### What Is an MTable?

An MTable is an object created in the Fabric memory from a CSV file. The purpose of an MTable is to keep reference data as part of the Fabric project and to enable a **fast in-memory** data lookup at run-time. It is recommended to use MTables for small static lists of reference data.

### How Can I Create an MTable?

To start creating an MTable, you should first upload a CSV file into the MTable folder in the Project Tree, under either an LU or References. 

Upon deployment, the MTable object is created in the Fabric memory, based on the CSV file's structure and the data. Other file types, apart from the CSV type, are ignored.

A CSV file can also be manually created in the Fabric Studio, under the MTable folder. Another way to create a new MTable or to update one that already exists in the Fabric memory is by using a MTableLoad Actor at run-time. [Click here for more information about MTable Actors.](/articles/19_Broadway/actors/09_MTable_actors.md)

### How Can I Use an MTable?

An MTable can be used when a flow, a Java function or a Web Service needs to look up data either by the given key(s) or without them, randomly. 

* In a flow, you can use one of the provided Actors that enables looking up the MTable data either by keys or without them, or loading data to an MTable. [Click here for more information about MTable Actors.](/articles/19_Broadway/actors/09_MTable_actors.md)
* In a Java code, various methods are exposed, enabling the use of MTables in Web Services, LU functions, etc. More information can be found at the Fabric online Javadoc, under *Common Java Utilities > MTable*.

Each MTable is accessible from any LU, regardless of its source CSV file location in the Project.

The data lookup can be performed by one or several MTable keys. The search index is created on-the-fly during the first select, based on the search keys. 

### Recommendations For MTables Storage Settings

By default, the MTables are created in the Fabric memory only, to enable a fast lookup of the required data. 

When you are required to make a joint query between an MTable's data and an LU's data, the MTables can be saved in a FabricDB schema. Another reason for saving the MTables in the FabricDB schema is the MTable size. 

* The definition of where to save the MTables is controlled by the configuration parameter FABRICDB_MTABLE_LIMIT in the [fabricdb] section of the config.ini and by default is set to -1 (memory only). It is recommended to keep the default setting when working with relatively small datasets.
* To save the MTables in both the Fabric memory and a FabricDB schema, set the parameter to a positive number that will indicate the number of MTable rows to be loaded into the memory. An MTable whose number of rows exceeds this set number, will be loaded only into the FabricDB schema.
* To save an MTable in a FabricDB schema only, without Fabric memory usage, update the parameter to zero.



[![Previous](/articles/images/Previous.png)](01_translations_overview_and_use_cases.md)

</web>

<studio>

[![Previous](/articles/images/Previous.png)](05_translations_code_examples.md)

</studio>