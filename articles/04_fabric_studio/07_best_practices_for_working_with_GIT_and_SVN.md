# Best Practices for Working with GIT and SVN

### How Do I Start Using Version Control?

To start working with Version Control, do either:

* Add a new project to **Version Control** and then check the **Add Project to Version Control** checkbox. 
   * Check out an existing project. 
   Make sure you have all the requirements, for example:
   * Type of configuration control for the project: GIT or SVN. 
   * Installation of the configuration control client: TortoiseGit or TortoiseSVN.
   * Project repository URL. 

Note that to check out a project, you must know the path of the checkout directory.

[Click for more information about Creating a New Fabric Project.](/articles/04_fabric_studio/05_creating_a_new_project.md)

[Click for more information about Adding Fabric Projects to Version Control.](/articles/04_fabric_studio/06_adding_fabric_projects_to_version_control.md)

### General Best Practices
When working with version control in Fabric projects, we recommend:
* Configuring the default project directory in General Preferences.
* Saving and committing the project baseline after creating a new project.
* The version control is controlled by username and password.
* When using a previous revision, click **Show Log** and then select the revision.

[Click for more information about User Preferences.](/articles/04_fabric_studio/04_user_preferences.md)

### Best Practices for Working with GIT

When working with Git in Fabric projects we recommend:
*  Using Git as the preferred version control. Git allows better collaboration, faster commit time, has no single point of failure and enables working offline on local branches without interruption.
* Pulling the latest version of the project before starting to change the code.
* Documenting committed changes for logging.
* To prevent impact on the work of others when adding new functionalities, creating a separate local branch using the Git **Switch** operation. Once the branch is created, the new functionality can be committed and tested. 
* After a functionality is tested, coordinating with others and then **merging** all local branch changes into the main branch.
* Resolving conflicts using the Git **diff** functionality.
* When working on large projects with many developers, designating one developer to be responsible for implementation and merging components. For example, LU schema changes.
* For projects that are required to deploy into multiple environments and / or work under CI / CD mode, add artifacts (*. json, *.jar, *.zip) generated by Fabric Studio to the Git repository and then deploy them using the command line.
  [Click for more information about Deployment from a Command Line.](/articles/16_deploy_fabric/03_offline_deploy.md)


### Best Practices for Working with SVN

When working with SVN in Fabric projects we recommend:
* Updating the project to the HEAD revision unless there is a specific reason for updating to a specific previous revision.
* Documenting changes that are committed in order to generate log messages. Include references to the issue’s ID. 
* To prevent conflicts, **do not use the SVN Lock option**. Only use the **Lock** option when additional changes are required over a longer period like more than a day of work.
* To resolve conflicts, downgrade the SVN revision to a previous one. Use the Update option and then use the Reverse Merge option to commit it.
* For projects that are required to deploy into multiple environments and / or work under CI / CD mode, check the *. json, *.jar, *.zip files, commit them into the SVN repository and then deploy them from the command line.
  [Click for more information about Deployment from a Command Line.](/articles/16_deploy_fabric/03_offline_deploy.md)  

[![Previous](/articles/images/Previous.png)](/articles/04_fabric_studio/06_adding_fabric_projects_to_version_control.md)[<img align="right" width="60" height="54" src="/articles/images/Next.png">](/articles/04_fabric_studio/08_fabric_project_tree.md)







