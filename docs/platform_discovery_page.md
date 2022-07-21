
## Discovery Page

[The Discovery Page](https://healdata.org/discovery) provides users a venue to search and find studies and datasets displayed in the HEAL Platform. Users can browse through the publicly accessible study-level metadata without requiring authorization.

> Use text-based search, faceted search, and tags to rapidly and efficiently find relevant studies, discover new datasets across multiple resources, and easily export selected data files to the analysis workspace.

![DiscoveryLanding](img/discovery_landing.gif)

The Discovery Page of the HEAL Platform. Browse through datasets and study-level metadata and find studies using tags or the free text search field.

### Search Features

<!-- MBK: deleted the "Click here: these sections shoudl probably
be embedded into the subsequent sections or have their own sections -->
![DiscoveryFeatures](img/discovery_features.png)

Different features such as free text search bar and tags on the Discovery Page help navigating and refining the search.

1.  Free Text Search. Finding studies is made easy using keywords in the free text-based search bar or using tags. The free-text search bar can be used to search for study title, investigator name, or any keyword that is mentioned in the metadata of the study. Type in any keyword mentioned in the metadata, except for what is stored as Tags in "Study Characteristics".
2.  Study Characteristics. Click "Study Characteristics" to expand the search options. Find a range of tags in eight categories (Study Setting, Study Design, Pain, Data Type, Subject Characteristics, Intervention/Treatment, Substance Use, Data Resources) to narrow down any search. Selecting multiple tags work in a "OR" logic. Click on "Reset Selection" to start a new search.
3.  The total number of studies. Shows the amount of studies the HEAL Platform is currently displaying.
4.  Export Options. Login first to leverage the export options. Select one or multiple studies and 1) download the attached data files, 2) download a file manifest (for data files whose sizes exceed 250 MB), or 3) export the metadata and data files to a secure cloud environment "Workspaces" to start your custom data analysis in Python, R, or STATA.
5.  Studies. This feature presents all current studies on the HEAL Platform. Click on any study to show useful information about the study (metadata). 
6.  Data Availability. Filter on available, pending, and not-yet-available datasets.
7.  Documentation. This brings you to this page you are currently on.
8.  Login Page. Login on the HEAL Platform to leverage all features. [Read further here](platform_login.md).

### Find available Study-level Metadata

Finding available study-level metadata on the HEAL Platform is made easy by clicking on a study.

![DiscoveryStudyPageDatafiles](img/discovery_study_page_datafiles.png)

Clicking on any study will display the available study-level and dataset metadata.

### Find accessible Datasets

Users can select and filter studies from multiple resources and conduct analyses on the selected datasets in a workspace. Users can find search only available data they have access to by selecting the data access button in the top right corner of the study page and selecting “Data Availability" - "Available" as shown below. The Discovery Page will automatically update the list of studies that have available datasets.

![Access_Box_Select_Window](img/access_box_select_window.png)

Select the symbol next to Data Availability to open all options. Three options are available. Find available datasets by clicking on the “Available” button.

### Data Availability Options

Different options for Data Availability exist and will be explained below.

![Access_boxes](img/access_options.png)

Three options for Data Availability.

*   Available: This option will display only studies with datasets users have access to and entails all open-access studies. Studies can be selected and exported to a workspace or downloaded by clicking on the associated checkbox on the left-hand side of the study entry and selecting one of the options in the top right.  
      
![discovery_options](img/discovery_options.png)

Once available, each study can be selected and exported to workspace or downloaded.
      
*   Not available: This option will filter out all studies that will only have metadata but no datasets available. The checkbox next to the study will be greyed out and non-clickable.  
      
    ![Access_greyed_out_box](img/access_greyed_out_box.png)
    
    Studies will grey out if they're not available, have no data attached, users have no access to, or are in pending mode.
        
*   Pending: This option will display studies located on any data resource or repository, for which attached datasets will be added in the near future. The checkbox next to the study will be greyed out and non-clickable as shown above.  
      
 
### Select Files on the Discovery Page and bring them to the Workspace

![Discovery_exporting_to_workspace](img/discovery_exporting_to_workspace.gif)

The above gif shows the workflow used to select data files from the Discovery Page and bring them into the workspace using Jupyter Notebooks.  

1.  Log in on [healdata.org/login](https://healdata.org/login). Link your account to all FAIR repositories as described [here](#LinkingAccessTo).  
      
    
2.  Find and select the study by the project number (in this example: 1U2CDA050098-01\_a) on the [Discovery Page](https://healdata.org/discovery). Find other current open-access studies [here](#CurrentOAStudies).  
      
    
3.  Click the “Open in Workspace” button in the upper right corner. This step will create a manifest folder which you can find later in the Workspace’s folder "data/healdata.org".  
    ![static_notebook_bacpac](img/static_notebook_bacpac.png)
    
    Select the study and click on “Open in Workspace”.
    
      
      
    
4.  Choose a workspace flavor and click "Launch". This step may take several minutes.  
      
    
5.  Navigate to the `/pd/data/healdata.org/` folder and find the placeholder files there. Click on those placeholder files to find instructions how to download the files or see below.  
      
    
6.  From the directory `/pd`, users can now start a new notebook. Click “New” (upper right corner) or open a previously saved notebook on the landing drive to load the files into one of the cells, for example by running:


    > ! gen3 drs-pull object "guid"

    > import pandas as pd   

    > os.chdir('/pd')

    > demo_df = pd.read_csv('pd/demo_file.txt', sep='\t')

    > demo_df.head()


More information for instructions on importing data can be found in the sections ["Download Files to Workspaces"](#DownloadFilesSDKWorkspaces) and ["Workspaces"](#Workspaces).  
    
    
7.  Make sure to terminate the workspace when the work is finished to reduce computational costs.

- "pd" means persistent directory. Saved files outside this directory will be lost.  
- The manifest.json lists metadata of all exported files and can be used to download in [batches](#DownloadFilesSDKWorkspaces)  
- Note, that all exported data files will be saved in the `/pd/data/healdata.org/` folder.  
- Please also note, that the workspace mounts up to a maximum of 5 different manifests while the workspace is running but shows only the latest exported manifest in a newly launched workspace.  
- Terminating the workspace will result in the loss of all but the latests manifest.  
