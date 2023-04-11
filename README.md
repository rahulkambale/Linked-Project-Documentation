
# LinkedERP Demo Project Documentation 

# IndexV
* [NetSuite Integration Setup Guide](#NetSuite-Integration-Setup-Guide)
* [Script Types](#Script-types)
* [Whom to Approach](#Whom-to-Approach)
* [About us](#🚀-About-us)

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

## Client Script 
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
## User Event Script
```
/**
 *@NApiVersion 2.x
 *@NScriptType UserEventScript
 */
define([], function() {

    function beforeLoad(context) {
        
    }

    function beforeSubmit(context) {
        
    }

    function afterSubmit(context) {
        
    }

    return {
        beforeLoad: beforeLoad,
        beforeSubmit: beforeSubmit,
        afterSubmit: afterSubmit
    }
});

```
## Schedule Script

```
/**
 *@NApiVersion 2.x
 *@NScriptType ScheduledScript
 */
define([], function() {

    function execute(context) {
        
    }

    return {
        execute: execute
    }
});

```
## Suitelet Script

```
/**
 *@NApiVersion 2.x
 *@NScriptType Suitelet
 */
define([], function() {

    function onRequest(context) {
        
    }

    return {
        onRequest: onRequest
    }
});

```
## RESTlet Script
```
/**
 *@NApiVersion 2.x
 *@NScriptType Restlet
 */
define([], function() {

    function _get(context) {
        
    }

    function _post(context) {
        
    }

    function _put(context) {
        
    }

    function _delete(context) {
        
    }

    return {
        get: _get,
        post: _post,
        put: _put,
        delete: _delete
    }
});

```
## PORTlet Script
```
/**
 *@NApiVersion 2.x
 *@NScriptType Portlet
 */
define([], function() {

    function render(params) {
        
    }

    return {
        render: render
    }
});

```
## Map Reduce Script
```
/**
 *@NApiVersion 2.x
 *@NScriptType MapReduceScript
 */
define([], function() {

    function getInputData() {
        
    }

    function map(context) {
        
    }

    function reduce(context) {
        
    }

    function summarize(summary) {
        
    }

    return {
        getInputData: getInputData,
        map: map,
        reduce: reduce,
        summarize: summarize
    }
});

```
## Mass Update Script
```
/**
 *@NApiVersion 2.0
 *@NScriptType MassUpdateScript
 */
define([], function() {

    function each(params) {
        
    }

    return {
        each: each
    }
});

```
## Workflow Action Script
```
/**
 *@NApiVersion 2.x
 *@NScriptType WorkflowActionScript
 */
define([], function() {

    function onAction(scriptContext) {
        
    }

    return {
        onAction: onAction
    }
});

```
## Bundle Install
```
/**
 *@NApiVersion 2.0
 *@NScriptType BundleInstallationScript
 */
define([], function() {

    function checkPrerequisites() {
        if (!runtime.isFeatureInEffect({ feature: 'TIMEOFFMANAGEMENT' }))
            throw 'The TIMEOFFMANAGEMENT feature must be enabled. Please enable the feature and try again.';
    }

    return {
        beforeInstall: function beforeInstall(params) {
            checkPrerequisites();
        },
        beforeUpdate: function beforeUpdate(params) {
            checkPrerequisites();
        }
    }
});

```

## Whom to Approach
|MODE|CONTACT TO|
|---|---|
|SALES|<a href="https://www.linkedin.com/in/amitd-rathod/"> AMIT</a>|
|TECHNICAL|<a href="https://www.linkedin.com/in/vaughan-robey-9671272a/"> VAUGHAN</a>|

---

## 🚀 About us
<img src="https://linkederp.com/wp-content/uploads/2022/04/INKFISH-logo-social-with-tagline.png"  width="50" height="50">
We are a NetSuite Partner and work in the reselling of technological solutions that put people first. Our ethos, embedded in our logo, is to interlink people and processes with technology, helping to realise superior solutions that deliver positive bottom line results.
