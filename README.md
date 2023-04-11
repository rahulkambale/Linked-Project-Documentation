
# LinkedERP Demo Project Documentation 

# IndexV
* [NetSuite Integration Setup Guide](#NetSuite-Integration-Setup-Guide)
* [Script Types](#Script-types)
* [Step 3](#step-3)
* [Step 4](#step-4)
* [Step 5](#step-5)
* [Step 6](#step-6)

# NetSuite Integration Setup Guide  
Step 1: [Create a Integration Record.](#Create-a-Integration-Record.)  
Step 2: [Enable Token Based Authentication](#Enable-Token-Based-Authentication).  
Step 3: [Create a Token Role](#Create-a-Token-Role)  
Step 4: [Add Token Management Permissions](#Add-Token-Management-Permissions)  
Step 5: [Enable View Permissions for Token Manager](#Enable-View-Permissions-for-Token-Manager)  
Step 6: [Create Access Tokens](#Create-Access-Tokens)  
Step 7: [Capture Account ID](#Capture-Account-ID)   


## Script Types
>  
Here are the Script Types with templates of SuiteScripts  
[Client Script](#Client-Script)  
[User Event Script](#User-Event-Script)  
[Schedule Script](#Schedule-Script)  
[Suitelet Script](#Suitelet-Script)  
[RESTlet Script](#RESTlet-Script)  
[PORTlet Script](#PORTlet-Script)  
[Map Reduce Script](#Map-Reduce-Script)  
[Mass Update Script](#Mass-Update-Script)  
[Workflow Action Script](#Workflow-Action-Script)  
[Bundle Install](#Bundle-Install)  


# Create a Integration Record.
* _Click on_ **Setup** on the top navigation bar
* *Click on* **Integration** on the left hand navigation, and select **Manage Integrations**
* Click **New** to set up a new integration record
* NetSuite Integration Setup Guide
* Enter **“Leapfin”** under Name for the integration
* Ensure the State of the integration is set to Enabled
* Under Authentication, check “Token-Based Authentication”
* Click **Save**
* Capture the **Consumer Key** and **Consumer Secret** immediately. They only appear once!

# Enable Token Based Authentication
* Click on **Setup** on the top navigation bar
* Under Setup, navigate to Company > Setup Tasks > Enable Features > SuiteCloud > Manage Authentication
* Make sure **Token Based Authentication** is checked and enabled.
* Scroll down and make sure you **Save** the new setting.

# Create a Token Role
* Click on **Setup** on the top navigation bar
* Under Setup, navigate to Users/Roles > Manage Roles > New
* Enter “Token Manager” as name of the new role
* Navigate down the page to **Permissions > Setup** and add the following permissions:
* User Access Token: Full
* Access Token Management: Full
* Web Services: Full
* Click **Save**

# Add Token Management Permissions
* Click on **Setup** on the top navigation bar
* Under Setup, navigate to **Users/Roles > Manage Users**
* Select your user
* Navigate down the page to **Access > Roles** and add the token role you just created (Token Manager)
* Click **Save**

# Enable View Permissions for Token Manager
* Click on the new Token Manager role you just created
* Scroll down and ensure you enable the following View permissions:
**Transactions:**

> Bills -> View
Credit Memo -> View
Find Transactions -> View
Invoice -> View
Refund Returns -> View
Sales Order -> View
View Payment Events -> View

**Lists:**

> Customers -> View
Items -> View

# Create Access Tokens
* Click on **Setup** on the top navigation bar
* Under Setup, navigate to Users/Roles > Access Tokens > New
* Create a new token with the following settings:
* Application Name: Leapfin
* User: Select your user name
* Role: Select the new role your created (Token Manager)
* Click Save
* Capture the **Token ID** and **Token Secret** immediately! They only appear once!

# Capture Account ID
* Click on **Setup** on the top navigation bar
* Under Setup, navigate to Integration > Web Services Preferences
* Capture **Account ID** on the top left of the screen

## client 
```
/**
 *@NApiVersion 2.x
 *@NScriptType ClientScript
 */
define([], function() {

    function pageInit(context) {
        // By the time page loads. Data will be set or business logic is executed.        
    }

    function saveRecord(context) {
        
    }

    function validateField(context) {
        
    }

    function fieldChanged(context) {
        // When value is Inserted in field and move cursor to other field, the business logic will be executed.
    }

    function postSourcing(context) {
        // After getting data from different record. (e.g selecting sku from list)
    }

    function lineInit(context) {
        
    }

    function validateDelete(context) {
        
    }

    function validateInsert(context) {
        
    }

    function validateLine(context) {
        
    }

    function sublistChanged(context) {
        
    }

    return {
        pageInit: pageInit,
        saveRecord: saveRecord,
        validateField: validateField,
        fieldChanged: fieldChanged,
        postSourcing: postSourcing,
        lineInit: lineInit,
        validateDelete: validateDelete,
        validateInsert: validateInsert,
        validateLine: validateLine,
        sublistChanged: sublistChanged
    }
});

```
## map/reduce  
## mass update  
## portlet 
## RESTlet scheduled  
## Suitelet  
## user event  
## workflow action  
## bundle installation  
## SDF installation
