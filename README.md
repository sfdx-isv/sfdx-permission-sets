# SFDX Permission Sets
A collection of SFDX-related permission sets and the package manifest required to deploy them to a Developer Hub org. Read below for installation instructions and description of what each permisison set does.


## Installation Instructions


### Step One: Clone this Repository
```bash
git clone https://github.com/sfdx-isv/sfdx-permission-sets.git
```

### Step Two: Connect the Salesforce CLI to your Developer Hub
*Skip this step if you've previously connected the Salesforce CLI in your environment to your Dev Hub.*
```bash
sfdx force:auth:web:login -a YOUR_DEVHUB_ALIAS
```

### Step Three: Deploy the SFDX Permission Sets to Your Developer Hub
```bash
sfdx force:mdapi:deploy -w 10 -d SFDX_Permission_Sets -u YOUR_DEVHUB_ALIAS
```

### Step Four: Assign the Appropriate SFDX Permission Sets to Your Users
*Permsets can also be assigned declaratively by going to **Setup->Users->Permission Sets**, opening the desired permission set, and clicking the **Manage Assignments** button.*
```bash
sfdx force:user:permset:assign -u YOUR_DEVHUB_ALIAS -n "SFDX_Developer" -o "some.user@your-devhub.org"
```

## Description of What Each Permission Set Does


#### SFDX_Admin
* Grants users the ability to create and manage **namespaced scratch orgs**, create and delete **second-generation packages**, and **promote** managed second-generation packages from **BETA to RELEASED**
* Available for users with the **Salesforce** license type only

#### SFDX_Developer
* Grants users the ability to create and manage **namespaced scratch orgs**
* Available for users with the **Salesforce**, **Salesforce Platform**, **Salesforce Developer**, and **SLAF** license types

#### SFDX_Package_Developer
* Grants users the ability to create and delete **second-generation packages**
* Available for users with the **Salesforce**, **Salesforce Platform**, **Salesforce Developer**, and **SLAF** license types

#### SFDX_Package_Promoter
* Grants users the ability to **promote** second-generation packages from **BETA to RELEASED**
* Available for users with the **Salesforce**, **Salesforce Platform**, **Salesforce Developer**, and **SLAF** license types
