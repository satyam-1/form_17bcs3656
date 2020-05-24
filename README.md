# Meraki Dashboard with Google Scripts & Forms

## Overview

This learning lab demonstrates the power of Meraki APIs with Google Scripts and Forms.

By building a simple Google Form and attaching a script written in JavaScript, a Meraki Dashboard administrator can easily be created. This is incredibly helpful when running workshops that require several administrators to have access to a lab network.

# Instructions
## Create a Google Form
https://forms.google.com

### The first two questions should be as follows:
- Email
- Name

[SAMPLE]

<img src="images/Meraki API Registration Form Screenshot.png" alt="Form" width=400/>

## Link the form to a Google Script

<img src="images/GoogleScriptsMenu.png" alt="Google Scripts Menu" width=400/>


## Add a Trigger to launch the script when the Form is submitted.

<img src="images/GoogleScriptsTriggersMenu.png" alt="Triggers Menu" width=400/>

### Configure the trigger
- Run: **onFormSubmit**
- Events: **From form**
- --> On form submit

<img src="images/GoogleScriptsTriggers.png" alt="Triggers" width=600/>

## Test the API calls
Several additional functions are included in this code to allow you to test with sample data and collect information.  
- Run --> *Select a **test** function*

<img src="images/GoogleScriptsRunMenu.png" alt="Run Menu" width=400/>

Feel free to modify the sample JSON data defined in the `testAddMerakiAdmin` function.

```
function testAddMerakiAdmin(){
  var data = {
    "name":"Google Scripts Demo",
    "email":"GoogleScriptsDemo@meraki.com", // change this to an email you have access to!
    "orgAccess":"full"
  };
  addMerakiAdmin(API_KEY,ORG_ID,SHARD,data);
}
```


## View the results
- View --> Logs

<img src="images/GoogleScriptsLogsMenu.png" alt="Logs Menu" width=400/>




## Google Form
Now that the API calls are working, test the Google Form by hitting the preview button.

<img src="images/Google Form Preview button.png" alt="Logs" width=300/>

Complete the form with a valid email address.

<img src="images/GoogleScriptsForm.png" alt="Logs" width=400/>

If everything worked, you should get an email from Meraki asking to complete the admin account verification.



## Verify Meraki account is created
- Meraki Dashboard   > Organization   > Administrators

## SUCCESS!
With Google Apps, you do not even need to host a server to run the application\.



### Meraki API Resources
http://developers.meraki.com/
