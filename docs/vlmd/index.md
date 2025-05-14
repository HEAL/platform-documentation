# Variable-level Metadata Submission  

The HEAL Data Platform contains variable-level metadata (VLMD) from two sources:

* [**Data Dictionaries:**](#data-dictionaries) these files describe each variable within a study's dataset
* [**HEAL CDEs (Common Data Elements):**](#heal-cdes-common-data-elements) these are validated and structured questionnaires used by investigators conducting research with human participants to harmonize the data collected across studies

!!! info 

     In order to submit any VLMD to the Platform, two conditions must be true:
     
     **1) The study must already be registered:** If your study is not yet registered on the HEAL Data Platform, please see our instructions for how to register your study before submitting VLMD. 
     
     <p align="center">[How to Register Your Study](../study-registration/index.md){ .md-button }</p>

     **2) You must have access to submit VLMD:** If you are the person who registered your study, you automatically have access. If someone else registered your study, you can follow the instructions below to request access to submit VLMD. 

     <p align="center">[How to Request Access to Submit VLMD](vlmd_request_access.md){ .md-button }</p>

## Data Dictionaries

Data Dictionaries, which contain variable-level metadata, describe each variable within a dataset. Examples of variable-level attributes include the variable name, description (or variable label), type, format, terminology, and source.

In order to submit a study’s data dictionary to the Platform, the data dictionary must conform to the HEAL [variable-level metadata schema](https://github.com/HEAL/heal-metadata-schemas/tree/main/variable-level-metadata-schema). The following instructions will demonstrate how to use the HEAL Data Utilities' VLMD tool to help you generate a HEAL-compliant data dictionary from your dataset or existing data dictionary, and then submit it to the Platform.

1. [How to Generate a HEAL-compliant Data Dictionary](vlmd_tools.md)

2. [How to Submit a HEAL-compliant Data Dictionary](vlmd_submission.md)

## HEAL CDEs (Common Data Elements)

HEAL CDEs are validated and structured questionnaires that include fields describing the human subject data collected, along with how the data was gathered, and how the response is represented in the dataset. HEAL investigators conducting research with human participants use CDEs to allow the data collected by different studies to be harmonized for further analyses. [*(To learn more about HEAL CDEs, visit this NIH page.)*](https://heal.nih.gov/data/common-data-elements)

* To report the CDEs your study used to the Platform, follow the instructions on [this page](vlmd_submit_CDE.md).  
