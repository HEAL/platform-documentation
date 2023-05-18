## How to Generate HEAL-compliant Data Dictionaries
Or, Using healdata-utils (or something expressing a utility) to Generate HEAL-compliant Data Dictionaries

In order to submit a data dictionary to the Platform, the data dictionary must conform to the HEAL variable-level metadata schema. This page will show you how to use a tool we’ve created (healdata-utils) to help you generate a HEAL-compliant data dictionary.  

!!! info
A current version of Python will be required to run the HEAL Data Utilities (healdata-utils).
Please see our python installation instructions for more help.

### Virtual Environment Set Up

We highly recommend installing the HEAL Data Utilities in a virtual environment. There are several software dependencies that will be installed along with the healdata-utils; a virtual environment allows you to successfully install these packages without affecting other software already on your computer. You can learn more about creating virtual environments with Python [here](https://docs.python.org/3/library/venv.html).  

Create a Project Folder
```mkdir my_project/```
```cd my_project ```
Create Input and Output Folders
```mkdir input```
```mkdir output ```
Create Virtual Environment
```python -m venv venv –upgrade-deps```
Activate Virtual Environment
For MacOS and Linux: source venv/bin/activate
For Windows: venv\Scripts\activate.bat
If you would like to deactivate your virtual environment at any time, use the command: ```deactivate```

### Install the HEAL Data Utilities

Now that we’ve created and activated our virtual environment, we can install the HEAL Data Utilities.

```pip install healdata-utils```

Next, to confirm that the HEAL Data Utilities package was installed correctly:

```which vlmd```
The installation path should look like something like this:

```/Users/my_username/path_to_project_folder/my_project/venv/bin/vlmd```

## Generate a HEAL Data Dictionary

Now that the HEAL Data Utilities python package has been successfully installed, it can be used to generate a HEAL data dictionary. The command `vlmd` will be used to call the healdata-utils python package.

To confirm installation and to see the different options:

```vlmd --help```

[image](imgs/healtdata-utils_options.png/)

Note that the only required flag is `--filepath`, the path to the file you want to convert to a HEAL data dictionary.

Here is how you would generate a HEAL Data Dictionary with a data dictionary downloaded from RedCap:

For MacOS and Linux:

```vlmd --filepath ./input/example_redcap_demo.redcap.csv --inputtype redcap.csv --outputdir ./output/heal-vlmd-from-redcap.csv```

For Windows:

```

Summary of CLI
mkdir my_project
cd my_project
python -m venv venv
source venv/bin/activate
mkdir input
mkdir output
Download Your Redcap.csv Data Dictionary into the my_project/input/ folder
pip install healdata-utils --pre
vlmd --help
vlmd --filepath ./input/example_redcap_demo.redcap.csv --inputtype redcap.csv --outputdir ./output/heal-vlmd-from-redcap.csv
