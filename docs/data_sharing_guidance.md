# Packaging Your Data for Success

## Introduction

This documentation describes general principles for sharing data with the research community in a manner consistent with NIH's 2023 Data Management and Sharing Policy, and with additional HEAL program requirements[^1]. These principles should apply to nearly all HEAL-compliant repositories, some of which impose their own specific requirements for how these principles are to be implemented. 

Why align with requirements to manage and share your data?:

1. NIH and HEAL requirements maximize data usability by making them Findable, Accessible, Interoperable, Reusable (FAIR).[^2]
2. Following good data sharing practices can make your lab more efficient by helping you to organize and document your data, reducing the chance of errors, and making individual and collaborative work with colleagues easy and organized; and
3. Identifying and learning to use the latest, appropriate technologies can reduce the time and effort required to manage your data.

To help you get started, we have identified minimal requirements and additional best practices to increase the scientific and analytic value of your datasets. 

## Data Packaging: What to Share and When

The 2023 NIH policy defines scientific data that must be shared as "the recorded factual material commonly accepted in the scientific community as of sufficient quality to validate and replicate research findings." This definition ties data sharing directly to your own analytic work (i.e., the data you share should permit someone to replicate your own published results) and includes not only data but other materials necessary for replication such as analysis code.

Data repositories define _open access data_ to be data which may be accessed or downloaded directly without going through a request and approval process. In contrast, _controlled access data_ require that users submit a request which is then reviewed prior to granting approval (e.g., by a data access committee). In cases where a complete dataset requires controlled access to protect confidentiality, we encourage whenever possible creating a second version of the dataset containing only a subset of the data that can be made openly accessible. It is well-established that openly accessible datasets are used much more frequently than controlled access datasets.

!!! note

    A third category is _registered access_, which requires a user to register with a repository before downloading or accessing a dataset. This requirement is imposed by the repository (e.g., to track dataset usage), and does not typically represent a major impediment to data use.

When packaging your dataset, it can be helpful to keep your data sharing goal in mind. Three common goals are:

1. **Replicating published analyses**: Sharing just those data needed to replicate findings in a specific published work (e.g., paper, poster, report), which often includes only a subset of the data generated over the course of a study but also requires sharing derived variables or the code for generating them.
2. **Data archiving**: Sharing an entire dataset generated over the course of a study to permit secondary users to plan and perform their own, independent analyses. Unlike the case above, this requires less attention to derived variables but greater attention to the steps required to protect confidentiality while at the same time retaining as much scientific and analytic value as possible.
3. **Participating in a collaborative project**: Submitting data from one site or study intended primarily to be analyzed and/or archived together with similar data from other sites or studies (e.g., as part of a planned meta- or mega-analysis or for archiving with a domain-specific repository). This typically requires preparing a dataset that meets very specific requirements, and may require harmonization.

While each of these goals has somewhat different needs and requirements, there are several general principles that apply across all of them. These are described below, organized into a set of minimal requirements followed by a list of additional best practices. We also provide several tips that you may find helpful when preparing and packaging your data for sharing.

### **Required items**

These items are required to enable others to use your shared data.

1. **Study-level metadata**: A human-readable file (e.g., a README file) identifying the study or project that generated the dataset and describing the terms (including any restrictions) governing use of the data.
2. **File-level metadata**: A file manifest identifying each data file included together with a brief description of what it contains and any other information needed to use and interpret the data (e.g., what measurement techniques and protocol(s), including software names and versions, were used to generate the files).
3. **Variable-level metadata**: For tabular data (e.g., one row for each observation with each column representing a different variable), one or more files describing each all variable included in the dataset including the variable name,title and/or description, and measurement units or possible values (e.g., possible responses for a patient reported outcome).
3. **Data file(s)**: The file(s) containing the shared data; these may contain raw, preprocessed data, post-processed or curated data, or files prepared for analysis

Example of a high-quality dataset accompanied by sufficient information to access and replicate published findings: [NIDA-CTN-0095A2: Reducing Stigma toward People with Opioid Use Disorder among Primary Care Clinicians at NIDA Data Share](https://datashare.nida.nih.gov/study/nida-ctn-0095a2)

### **Best Practices - A Little More Goes a Long Way**

_The following additional steps can add substantial scientific and analytic value to a shared dataset:_

1. Include persistent identifiers (e.g., DOIs) to publication(s) generated from the data; this not only aids in replication but can also provide additional documentation for the data with little or no extra work. 
2. Include additional variable-level metadata, such as links to the source of specific items (e.g., Common Data Element (CDE) repository, NIH's PhenX Toolkit, or a specific measurement instrument).
3. Include protocol(s) for executing the study, including procedures for collecting, processing (including QC, cleaning, and curation), and managing the data.
4. Include code that may be executed to translate raw file(s) together with corresponding variable-level metadata (when applicable) into commonly used analytic formats such as Stata, R, SAS, Pandas/Python, etc.
5. Include code to perform specific data transformations (e.g., generate derived variables or reorganize data to facilitate a specific analysis).
6. Include pipelines to validate assertions about the data such as skip patterns (e.g., instances where a specific item is skipped based on responses to a previous item).
7. Combine data, metadata, and code into a _[data package](https://datapackage.org/)_—a specially organized folder containing one or more data files and corresponding JSON- or YAML-formatted metadata files. Data packages make it easy to validate data, to transform data, to read data into analytic software packages, and to share data.

## Helpful Tips

A FAIR data package contains both the data files you intend to share and sufficient information for secondary users to understand and use those data files. As noted above, this additional information may include protocols, data collection instruments, code for manipulating or analyzing the data, discipline-specific metadata files describing the data, and additional documentation. 

### **Recommended file formats**

1. **Data files should be in a non-proprietary, commonly-used format** such as CSV files with commas or tabs as delimiters and a header row containing column (i.e., variable) names. Nearly all software for data collection and/or data management is capable of exporting to CSV format, and this ensures that the data may be read by the widest possible range of software, both now and in the future. Data representing responses from a fixed set of choices (e.g., Yes/No items or individual items from a Likert scale) may be recorded as text labels (e.g., "Yes" or "No") or as integer codes, where the mapping between integers and labels is provided in an accompanying schema (see Item 2 immediately below).
2. **Variable-level metadata (VLMD) should be provided in machine-readable form**. The best way to do this is with a JSON- or YAML-format schema, though a data dictionary in CSV format may in some cases also be acceptable. The HEAL Data Ecosystem requires that variable-level metadata (VLMD) schemas include at a minimum the variable name and description, while also strongly encouraging inclusion of the following (for each variable): a title (i.e., a human-readable label for the variable), datatype (e.g., integer, float, date, string, boolean, etc.), and possible responses for each variable (e.g., range, list of choices, or constraints). Examples of valid and invalid VLMD files are available [here](https://github.com/HEAL/heal-metadata-schemas/tree/main/variable-level-metadata-schema/examples). Note: All variable-level metadata submitted to the HEAL Data Platform must adhere to this specification, and it is also strongly recommended when submitting data to a repository.

### **Data Curation and Quality Control** 

1. In addition to the VLMD described above, it is best practice for all data to be accompanied by the following minimal study-level metadata (e.g., in the README file):
    1. Name of investigator(s)
    2. Funding agency and grant number
    3. Usage requirements and/or restrictions, including suggested acknowledgement
    4. Reference to corresponding publication, if applicable
2. Similarly, it is best practice for all data files to be accompanied by the following file-level metadata (e.g., in the file manifest):
    1. Title
    2. Description
    3. Version identifier (so a dataset can be clearly identified and distinguished from prior or subsequent versions)
    4. Any additional information necessary to read the file (e.g., choice of delimiter, use of quotation marks, encoding)
    5. MD5 checksum or equivalent (to verify the file has been transferred accurately and not modified)
3. **If a schema is provided, data should be valid when checked programmatically against that schema**. A useful way to think about a data dictionary (or more generally, a VLMD schema) is that it represents a set of assertions about a dataset. The validity of these assertions can be checked automatically using available software tools (e.g., [Frictionless data management framework for Python](https://framework.frictionlessdata.io/)). This allows: 1) data curators to confirm that curation steps are being executed correctly, 2) secondary data users to verify that there have been no changes or modifications made prior to receiving the data, and 3) users to harmonize these data with additional data.

**For human subjects studies**:

1. **Investigators engaged in human subjects research are responsible for ensuring that they have consent from research participants and IRB approval to share data and that data are deidentified and shared in a manner consistent with the language used in their consent form(s) and any applicable institutional requirements. In general**:
    - All direct identifiers must be removed. Direct identifiers are fields that contain information that are sufficient to identify a study participant, either by providing the study participant's identity or by providing information that can be used to link to other data that contain the study participant's identity. These identifiers include, but are not limited to, names, social security numbers, home addresses, email addresses, phone numbers, medical record numbers, credit card numbers and license plate numbers.
    - All dates must be shifted to reduce the risk of deductive disclosure. For example, those using REDCap to collect data have the option of shifting dates by a random amount between 0 and 364 days back in time, with a constant shift being used for all dates pertaining to the same individual.
    - Any open-ended responses should be removed; these can be coded into a clearly defined set of categories if it's necessary to preserve some of the information for analysis.
    - Local participant IDs should be replaced with standardized, anonymous identifiers; this breaks any link between local materials and the shared dataset.
    - The resulting dataset should be reviewed by an expert at your institution (e.g., a data curation or archiving expert at your institutional library) to identify and mitigate any additional potential disclosure risks.
2. **All missing values should be consistently coded using a clearly defined set of categories such as the following**:
    - Don't know (participant reports that they do not know the answer to the question)
    - Refused (participant indicates that they prefer not to answer the question)
    - No answer (self-administered item left blank by participant)
    - Legitimately skipped (item does not apply to this participant and/or timepoint)
    - Not collected (item not administered, either intentionally or unintentionally)
    - Missing in error (datum not available for any other reason)

In cases where this information was not recorded, the corresponding value should be left blank (i.e., the empty string). Such information should ideally always be recorded and provided when sharing data, since blank values can make a dataset difficult if not impossible to analyze.

## Data Sharing Resources
- [HEAL VLMD schema](https://github.com/HEAL/heal-metadata-schemas/blob/main/variable-level-metadata-schema/schemas/data-dictionary.json)
- [Examples of valid and invalid VLMD](https://github.com/HEAL/heal-metadata-schemas/tree/main/variable-level-metadata-schema/examples)
- [Components of a README](https://datamanagement.hms.harvard.edu/collect-analyze/documentation-metadata/readme-files#:~:text=README%20Files%20are%20a%20common,Explore%20additional%20Documentation%20%26%20Metadata%20practices.)
- [HEAL-compliant repositories](https://www.healdatafair.org/resources/guidance/selection)
- [NIH Data Management & Sharing Policy Overview](https://sharing.nih.gov/data-management-and-sharing-policy/about-data-management-and-sharing-policies/data-management-and-sharing-policy-overview#after)
- [NIH Data Management Resource](https://sharing.nih.gov/data-management-and-sharing-policy/data-management)
- [Curating Research Artifacts to Support Scientific Integrity](https://curating4reproducibility.org/)
- [HEAL Stewards Sensitive Data Guidance](https://www.healdatafair.org/sensitive-data)
- [Metadata in the HEAL Data Ecosystem](https://www.healdatafair.org/resources/metadata)

## References
[^1]: National Institutes of Health (2020). Final NIH Policy for Data Management and Sharing. [https://grants.nih.gov/grants/guide/notice-files/NOT-OD-21-013.html](https://grants.nih.gov/grants/guide/notice-files/NOT-OD-21-013.html).
[^2]: Wilkinson, M.D., Dumontier, M., Aalbersberg, Ij.J., Appleton, G., Axton, M., Baak, A., Blomberg, N., Boiten, J.-W., da Silva Santos, L.B., Bourne, P.E., et al. (2016). The FAIR Guiding Principles for scientific data management and stewardship. Scientific Data 3, 160018. [https://doi.org/10.1038/sdata.2016.18](https://doi.org/10.1038/sdata.2016.18).