# Google Cloud Storage Interface 

Google Cloud Storage interface type is used to define the connections between a blob storage and a data stream.

When creating an [Interface Listener for a Broadway flow](/articles/19_Broadway/09_broadway_integration_with_Fabric.md#interface-listener-for-broadway-flows), an Google Cloud Storage interface is needed to detect new files added to the storage.

To create a new Google Cloud Storage interface, do the following:

<studio>

1. Go to **Project Tree** > **Shared Objects**, right click **Interfaces**, select **New Interface** and then select **Google Cloud Storage** from the **File System** section to open the **New Interface** window.

   ![image](images/14_gcs_1.png)
   
2. Populate the connection's settings and click **Save**.
</studio>

<web>
1. Go to **Project Tree** > **Shared Objects**, right click **Interfaces**, select **New Interface** and then select **Google Cloud Storage** from the **Interface Type** dropdown menu to open the **New Interface** window.

2. Enter a suitable name for your new Google Cloud Storage Interface, then click **Create**
  
   ![image](images/14_gcs_WEB1.png)

3. Populate the connection's settings and click **Save**.

   ![image](images/14_gcs_WEB2.png)

</web>


### Connection Settings

<table>
<tbody>
<tr>
<td width="300pxl"><strong>Parameter</strong></td>
<td width="600pxl"><strong>Description</strong></td>
</tr>
<tr>
<td><strong>Bucket name</strong></td>
<td>The name of the bucket.</td>
</tr>
<tr>
<td><strong>Project ID</strong></td>
<td>Project ID.</td>
</tr>
<tr>
<td><strong>Location ID</strong>&nbsp;</td>
<td>Location ID.</td>
</tr>
<tr>
<td><strong>Credentials file</strong></td>
<td>The location of the credentials file.</td>
</tr>
<p>Test Connection. Click to test the connection.</p>
<studio>
<p>Add an Interface Listener as a Broadway job. Click to create an Interface Listener job under the specified Logical Unit.</p>
</studio>
</td>
</tr>
</tbody>
</table>






<studio>

### Example of Using an Google Cloud Storage Interface

To create an [Interface Listener](/articles/19_Broadway/09_broadway_integration_with_Fabric.md#interface-listener-for-broadway-flows) Job that runs on an Google Cloud Storage interface, do the following: 

1. Create an interface using an **Google Cloud Storage** interface type.

2. Click the **Add interface listener as Broadway job** link in the Interface window and select the [Logical Unit](/articles/03_logical_units/01_LU_overview.md) from the list to open the Jobs window. 

3. Create a Broadway flow either under Shared Objects or under the same Logical Unit. The flow reads data from a file using the predefined interface and populates it into the DB. 

<img src="/articles/19_Broadway/images/file_read_listener.png" alt="images" style="zoom:80%;" />

* Note that the **interface** and the **path** input arguments of the **FileRead** Actor are defined as [External link type](/articles/19_Broadway/03_broadway_actor_window.md#actors-inputs-and-outputs). Their values are passed from the defined interface by the Listener.
* In the Jobs window, select the **Broadway flow** and **Execution mode** and then save the job.

![images](images/02_sftp_2.PNG)

5. [Deploy the LU](/articles/16_deploy_fabric/02_deploy_from_Fabric_Studio.md) to activate the Listener.

</studio>

### Using the InterfaceListener Actor 

The **InterfaceListener** Actor enables the flow in which it is instantiated to listen to Google Cloud Storage interface and trigger another Broadway flow upon arrival of a new file on the interface.

To create an Interface Listener job from a Broadway flow, add the **InterfaceListener** Actor to the flow.

<img src="images/12_interfaceListenerActor_1.PNG" alt="images" style="zoom:80%;" />

Fill in the following parameters in the Actor's Properties tab:

- **flowName**, the flow to be triggered by the Interface Listener.
- **interfaceName**, the interface that is being listened and used to trigger the flow defined above, once a new file is detected on the file system to which the interface points.

- **affinity**, sets which node/DC name IP address is to be used to run the Interface Listener job.

- **params**, refer to the arguments that can be passed to the flow. For example, multiple parameters can be parsed as a key/value object from an external link or from a **Const** or **JavaScript** Actor.



[![Previous](/articles/images/Previous.png)](13_blob_interface.md)