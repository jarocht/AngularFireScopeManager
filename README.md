# AngularFireScopeManager
A simple embeddable webpage for tracking and managing project scopes using AngularJS and FireBase

## Deployment and Usage Guide
### Prerequisites
1. A Firebase account
2. A way to host the individual pages

### Firebase Setup
#### Data Structure
The data for the scope manager is stored using the Firebase API. 
More importantly that data must have a certain data structure. 
For this project that structure is as follows:
##### Types
* types
  * int: "Text"

###### For Example:
* types
  * 1 : "New Customer"
  * 2 : "Existing Customer"

##### Scopes
* scopes
  * engineer name
    * hours: int
    * rank: int
    * title: "text"
    * records
      * record objects

###### For Example:
* scopes
  * "Tim Jaroch"
    * hours: 4
    * rank: 1
    * title: "Manager"
    * records
      * record objects

##### Record objects
* records
  * recordHashId
    * customerName: "text"
    * engagementManager: "text"
    * forecast: int
    * gearsId: "text"
    * priority: int
    * typeNumber: int
    * typeText: "text"
    
###### For Example:
* records
  * -Ji_HL_mmBY0HPP_kMy1
    * customerName: "Microsoft"
    * engagementManager: "John Adams"
    * forecast: 2.3
    * gearsId: "12345"
    * priority: 5
    * typeNumber: 1
    * typeText: "New Customer"

You will not need to actually create the record entries as the applet does that for you.
#### Authentication
You will also need an authentication key to keep your data protected.
https://www.firebase.com/docs/web/guide/login/anonymous.html

### HTML Modification
Next you'll need to update all of the html files with your Firebase URL and Token.
```
var authToken = "<YOUR-TOKEN-HERE>";
var baseUrl = "<YOUR-FIREBASE-URL-HERE>";
```
### Deploy
Now all you need to do is host the html files on a web server. Similarly, since all of the javascript is completely self contained, you can host them inside of an iframe or Confluence Macro.
