
# Discovery Page

[The Discovery Page](https://healdata.org/portal/discovery) provides users a venue to search and find studies and datasets displayed in the HEAL Platform. Users can browse through the publicly accessible study-level metadata without requiring authorization.

> Use text-based search, faceted search, and tags to rapidly and efficiently find relevant studies, discover new datasets across multiple resources, and easily export selected data files to the analysis workspace.

![DiscoveryLanding](img/discovery_landing.gif)

The Discovery Page of the HEAL Platform. Browse through datasets and study-level metadata and find studies using tags or the free text search field.

## Search Features

![DiscoveryFeatures](img/discovery_features.png)

Different features such as free text search bar and tags on the Discovery Page help navigating and refining the search.

1.  **Free Text Search:** Finding studies is made easy using keywords in the free text-based search bar or using tags. The free-text search bar can be used to search for studies of interest:  

    1. **Full Text Search:** The default search is a full-text search for study title, investigator name, or any keyword that is mentioned in the metadata of the study (see also #3 below for filtering options).  
    2. **Restrict Search to Selected Fields:** Click the radio button to restrict your search to specific fields in the variable-level metadata (VLMD). You can restrict your search of VLMD in several ways:  

        * Restricting search to **HEAL CDE name** permits a search for studies using a specific tool (e.g., "Generalized Anxiety Disorder-2" or "GAD"), or studies using tools with a word or phrase in the CDE name (e.g., "pain").  
        * Restricting search to **variable source and/or ID** allows a search for studies using specific controlled vocabulary and phrases. For example, you can check this box to search for studies that used specific elements, e.g.,  by searching "CDISC C103705," which refers to [PHQ-9 - Little Interest or Pleasure in Doing Things](https://evsexplore.semantics.cancer.gov/evsexplore/concept/ncit/C103705) from the Clinical Data Interchange Standards Consortium (CDISC).  
        * Restricting search to **variable title**, **name**, or **description** permits a search of specifically these fields from data dictionaries submitted for studies. For example, looking at the [example data dictionary template](https://github.com/HEAL/heal-metadata-schemas/blob/main/variable-level-metadata-schema/examples/valid/template_submission.csv), we can see that the Substance Use section of the dictionary includes a variable about heroin use. The title of this variable (which is the human-friendly name of the variable) is "Heroin Days Used." However, the variable name (which is the encoded name of the variable) is "SU4." The description of this variable is "During the past 30 days how many days did you use heroin (alone or mixed with other drugs)?".  

2.  **Data Repository:** To filter studies by specific data repositories used by a study, click the Data Repository button (2A), which will reveal a Data Repository field (2B) in which you may select repositories of interest. If you select multiple repositories, it will use an "OR" logic to filter studies that have reported any of those repositories.  
3.  **Filters:** Click "Filters" to expand the options to filter studies by different study metadata tags. Find a range of metadata tags (e.g., Study Type, Data Type, Subject Type, Age, and HEAL CDE) to narrow down any search. Selecting multiple tags can work in either an "AND" or "OR" logic, depending on the selection at the top of the Filters drawer. Click on "Reset Filters" to deselect all filters and start over.  
4.  **Total number of studies:** This shows the number of studies the HEAL Data Platform is currently displaying that match the various search and filter criteria selected.  
5.  **Data Access Options:** Log in first to leverage the export options. Select one or multiple studies by checking the checkbox at the beginning of the study row and you can then: 1) download the attached data files *(available for studies where possible)*; 2) download a file manifest (especially useful for data files whose sizes exceed 250 MB); or 3) export the metadata and data files to secure cloud environment "Workspaces" to start your custom data analysis in Python, R, or Stata.  
6.  **Studies:** This feature presents all current studies on the HEAL Data Platform. Click on any study to show useful information about the study (metadata).  
7.  **Data Availability:** Filter studies based on whether their data has the status Waiting (no dataset shared yet), Available (dataset shared and is open access), Request Access (dataset is shared but requires authorization from the host repository for access) and Not Available (no data will be shared for this study).  
8.  **Documentation:** This brings you to home page for the documentation (including this page you are currently on).  
9.  **Login Page:** Log in on the HEAL Data Platform to leverage all features. [Read further here](logging-in.md).  

## Study Page  

You can view the study page by clicking on a study in the search results, which will open a drawer with the study page on the right.  

![DiscoveryStudyPageDatafiles](img/discovery_study_page_datafiles.png)

The study page defaults to open the Summary tab, but there are 4 tabs in the study page:

* **Summary tab:** Includes information about the study, with selected study-level metadata tags listed at the bottom (reflecting metadata reported in the CEDAR form). *(Shown in figure above)*
* **Data tab:** Provides buttons to download variable-level metadata, study-level metadata, a manifest of the metadata files, or download all files. *Note: you must be logged in to use some of these features.*  This tab will also display a link to the data in the repository if it has been provided to the platform.  
    
    ![Study Page - Data tab](img/discovery_study_page_datatab.png)

* **Cite tab:** Provides citation information for the study on the platform and for the study data in the repository
    
    ![Study Page - Cite tab](img/discovery_study_page_citetab.png)

* **Related Studies tab:** Shows other very-closely-related studies on the platform that share the same NIH serial number ([read more about NIH serial numbers here](https://www.nimh.nih.gov/funding/grant-writing-and-application-process/research-funding-frequently-asked-questions-faqs#content_4)). Most studies will not have any related studies listed.  
    
    ![Study Page - Related Studies tab](img/discovery_study_page_relatedstudies.png)


## Find available Study-level Metadata

You can find available study-level metadata for a study on the HEAL Platform from the study page. There are two ways to see the metadata. 

* The study page opens on the Summary tab, which includes information about the study with selected study-level metadata tags listed at the bottom (see figure in [Study Page](#study-page), above).  
* The Data tab on the study page includes a button to download study-level metadata (see Data tab figure, above).

## Find accessible Datasets

On the Discovery page, users can filter for studies that have data available through the platform using the Data Availability filter in the right-most column of the search results. Click on Data Availability (#1), then select only the Available box (#2) to find data that is available and that you have access to through the platform, then click OK (#3). The Discovery Page will automatically update the list of studies that have available datasets.  

![Access_Box_Select_Window](img/access_box_select_window.png)

The filter allows you to check more than one availability status, and uses an "OR" logic to filter studies. To interpret the different availability status options, please see the next section.  

### Data Availability Options

![Access_boxes](img/access_options.png){: style="height:250px"}

**Waiting:**  
"Waiting" is the default data availability status for studies added to the platform. This status means:  

* Data have not yet been submitted to a repository; or, 
* The repository has not yet released the data; or, 
* The study team has not yet provided the link to the data to the HEAL Data Platform. (To [submit a data link, see our documentation about this](reporting-repo.md/#get-the-permalink-to-your-study))

**Available:**
"Available" means you are now able to access these data via the HEAL Data Platform, by [downloading them](downloading_files.md/#download-data-files-from-the-discovery-page) and/or by [importing them in a workspace](workspaces/heal_workspaces.md)

**Request Access:**
"Request Access" means that the data has been deposited in a repository and is available. To access the data, you will first need to visit the host repository to request access to it, following the repository’s standard procedures. Once that is complete, authorized users can then [bring these data into a HEAL workspace for analysis](workspaces/heal_workspaces.md).

**Not Available:**
"Not Available" means that no data will be made available for this study.
 
## Select Files on the Discovery Page and bring them to the Workspace

![Discovery_exporting_to_workspace](img/discovery_exporting_to_workspace.gif)

The above gif shows the workflow used to select data files from the Discovery Page and bring them into the workspace using Jupyter Notebooks.  

1.  Log in at <https://healdata.org/portal/login>. Link your account to all FAIR repositories as described [here](platform_request_access.md#linking-access-to-fair-enabled-repositories).  
      
    
2.  Find and select the study by the project number (in this example: 1U2CDA050098-01\_a) on the [Discovery Page](https://healdata.org/portal/discovery). Find other current open-access studies [here](platform_request_access.md#current-open-access-studies).  
      
    
3.  Click the "Open in Workspace" button in the upper right corner. This step will create a manifest folder which you can find later in the Workspace’s folder "data/healdata.org".  
    ![static_notebook_bacpac](img/static_notebook_bacpac.png)
    
    Select the study and click on "Open in Workspace".
    
      
      
    
4.  Choose a workspace flavor and click "Launch". This step may take several minutes.  
      
    
5.  Navigate to the `/pd/data/healdata.org/` folder and find the placeholder files there. Click on those placeholder files to find instructions how to download the files or see below.  
      
    
6.  From the directory `/pd`, users can now start a new notebook. Click "New" (upper right corner) or open a previously saved notebook on the landing drive to load the files into one of the cells, for example by running:


    > ! gen3 drs-pull object "guid"

    > import pandas as pd   

    > os.chdir('/pd')

    > demo_df = pd.read_csv('pd/demo_file.txt', sep='\t')

    > demo_df.head()


More information for instructions on importing data can be found in the sections ["Download Files to Workspaces"](downloading_files.md#download-data-files-in-workspaces-using-the-python-sdk) and ["Workspaces"](platform_workspaces.md).  
    
    
7.  Make sure to terminate the workspace when the work is finished to reduce computational costs.

- "pd" means persistent directory. Saved files outside this directory will be lost.  
- The manifest.json lists metadata of all exported files and can be used to download in [batches](downloading_files.md#download-data-files-in-workspaces-using-the-python-sdk)  
- Note, that all exported data files will be saved in the `/pd/data/healdata.org/` folder.  
- Please also note, that the workspace mounts up to a maximum of 5 different manifests while the workspace is running but shows only the latest exported manifest in a newly launched workspace.  
- Terminating the workspace will result in the loss of all but the latests manifest.  
