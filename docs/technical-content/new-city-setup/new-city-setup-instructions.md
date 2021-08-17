### README
This repository contains files that customize the Police Data Manager (PDM) product.


# *New City Setup Instructions*

We’re so glad you have decided to use our Police Data Manager tool! This guide is meant to provide instructions for setting up your Police Data Manager and Instance Files locally in order to use and customize the tool for your desired city.



## GETTING STARTED


### Introduction

Follow this [link](https://publicdataworks.github.io/pdm-docs/business-content/introduction-to-police-data-manager.html) to view the introduction to the Police Data Manager tool.

### Clone Police Data Manager Repository

Follow this [link](https://github.com/PublicDataWorks/police_data_manager.git) to view and clone the **police_data_manager** Repository in Github.


## SETTING UP INSTANCE FILES REPO


### Clone Instance Files Repository

Follow this [link](https://github.com/PublicDataWorks/instance_files_pm.git) to view and clone the **instance_files_pm** Repository in Github.


### Test & View Locally

In order to test PDM locally, you can setup the `INSTANCE_FILES_DIR` environment variable on your local machine to point it to the `instance-files` directory within this repository. This will allow the PDM application to read from this absolute path and tailor the application to your cities requirements.

**How?**

Add absolute path of your instance-files folder location in whatever file you use ( .profile, .zshrc, etc) we will be using .zshrc for this example
* In your terminal, navigate inside the instance-files folder after cloning the repo
* enter the command `pwd`  and copy path that is outputted
* open the environment file ( .profile, .zshrc, etc) with your desired text editor and set your INSTANCE_FILES_DIR environment variable.
  * In terminal: open ~/.zshrc
  * In file: export INSTANCE_FILES_DIR=“`paste path here`”
* enter the command `source ~/.zshrc`
  * tip: exit out your terminals for source to take effect. To double check reopen your terminal and enter `echo $INSTANCE_FILES_DIR` , you should see the path that you pasted.


## CHANGE CITY INSTANCES

The below checklist is required for displaying your specific city’s details in the Police Data Manager tool. 

**Helpful Tip:** In your editor of choice, search in the **instance-files** folder for any occurrences of the below dummy data. **All** of these occurrences must be substituted with your new city’s data.


### Letter Templates

*Feel free to change any of the content of the letter templates to best reflect your city’s or organization’s current misconduct letter templates or information.*

Located in **/instance-files/letterBody.tpl**


* Change `Office of the Police Monitor (PM)` to reflect the name of your organization.
* Change `Grenville City` to reflect your city name.
* Change `Code Section 1-2212 (the Police Monitors Ordinance)` to reflect your city's ordinance code.
* Change all occurrences of `PM` to reflect your organization’s acronyms. 
* Change all occurrences of `GCPD` to reflect your city's police department.
* Change the contact `John A Simms or Nina S Ambroise` to reflect the name(s) of your organization’s Police Monitor(s) and Complaint Intake Specialist(s).

Located in **/instance-files/referralLetterPdf.tpl**



* Substitute the below information with your organization name, address, phone, and fax (if applicable). 

```
OFFICE OF THE POLICE MONITOR 
966 Morningview Lane | Grenville, WI | 53540 
Phone (641) 892-7222| Fax (414) 335-3049
```


* Change the name `JOHN A SIMMS` and title `POLICE MONITOR` to reflect the name(s) of your organization’s police monitor(s).

Located in **/instance-files/complainantLetterPdf.tpl**



* Substitute the below information with your organization name, address, phone, and fax (if applicable). 

```
OFFICE OF THE POLICE MONITOR 
966 Morningview Lane | Grenville, WI | 53540 
Phone (641) 892-7222| Fax (414) 335-3049
```


* Change the name `JOHN A SIMMS` and title `POLICE MONITOR` to reflect the name(s) of your organization’s police monitor(s).
* Change all occurrences of `PM` to reflect your organization’s acronyms. 
* Change all occurrences of `GCPD` to reflect your city's police department.
* Change `Grenville City` to reflect your city name.
* Change the number `(641) 892-7222` to reflect your organization’s number.
* Change the email `policemonitor@pm.ex` to reflect your organization’s email.
* Change the name `Nina S Ambroise` and title `Complaint Intake Consultant` to reflect your organization’s intake specialist’s name and title. 


### Letter Signatures

Located in /**instance-files/images**



* Delete `john_a_simms.png` and add a PNG of your police monitor’s signature (or whoever will be signing off on letters).

Located in **instance-files/content.json**



* Change the below to reflect the name and signature file of your police monitor (or whoever will be signing off on letters). 
```
"JOHN": {`
   "name": "John A Simms",`
   "signature": "file:/app/src/instance-files/images/john_a_simms.png"
```


### Letterhead Logos

Located in **/instance-files/images**



* Change the **icon.ico** file to reflect your organization’s icon.

    *Image size: 828 × 755 pixels*

* Change the **header_text.png** file to reflect your city and organization name.

    *Image size: 1079 × 158 pixels*


Located in **/instance-files**



* Change the **favicon.ico** file to reflect your organization’s icon (i.e. same as icon.ico).

Located in **/instance-files/public**



* Change the **favicon.ico** file to reflect your organization’s icon (i.e. same as icon.ico).


### Letter Defaults

Located in **/instance-files/helpers.js**



* Change all occurrences of `PM` to reflect your organization’s acronyms. 

Located in /**instance-files/referralLetterDefaults.js**



* Change the name `Karla A Coriell` to reflect the name of your city’s Deputy Superintendent.
* Change `Grenville City` to reflect your city name.
* Change the address `128 Central Avenue\nGrenville, WI 53540` to reflect your city’s police department address.
* Change the name of the sender `John A Simms` to reflect the name of your organization’s Police Monitor (or whoever will be signing off on letters).
* Change title, and number of the sender `\nPolice Monitor\n231-873-5975` to reflect the title, and number of your organization’s Police Monitor (or whoever will be signing off on letters).
* Change the signature of your sender from `john_a_simms.png` to the name of the file used for your sender’s signature. 


### Default Constants

Located in **/instance-files/constants.js**



* Change the value of **ORGANIZATION** from `PM` to the acronym of your organization.
* Change the value of **ORGANIZATION_TITLE** from `Office of the Police Monitor` to the name of your organization.
* Change the value of **CITY** from `City of Grenville` to the name of your city.
* Change the value of **PD** from `GCPD` to the  acronym of your city’s police department.


### Seed Files

Located in **instance-files/localstack-seed-files**

Replace the following files with your own or edit with your specific city’s data:



* allegations.csv
* caseNoteActions.csv
* civilianTitles.csv
* classificationOptions.csv
* districts.csv
* genderIdentities.csv
* howDidYouHearAboutUsSources.csv
* intakeSources.csv
* officerHistoryOptions.csv
* officerSeedData.csv
* raceEthnicities.csv
* recommendedActions.csv


### Other

Located in **instance-files/tests/e2e/nightwatch.conf.js**



* Change the value of the **pd_address** from `Location: 966 Morningview Lane, Grenville, WI 53540` to your police department’s address.
* Change the value of the ci **launch_url** from `https://pm-ci.herokuapp.ex/` to the link of your heroku app in CI. 
* Change the value of the staging **launch_url** from `https://pm-staging.herokuapp.ex/` to the link of your heroku app in CI. 

Located in **instance-files/tag-glossary.json**



* Change all occurrences of `PM` to reflect your organization’s acronyms. 
* Change all occurrences of `GCPD` to reflect your city's police department.


## OTHER RESOURCES


### Contact App Maintainers

Follow this [link](https://publicdataworks.github.io/pdm-docs/common-content/communications.html) to get in contact with the maintainers of the application.


### FAQ

Follow this [link](https://publicdataworks.github.io/pdm-docs/technical-content/faq.html) to view the useful technical tools and FAQ.
