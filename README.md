# Javascript in Visualforce Pages
* The best method for including JavaScript in a Visualforce page is placing the JavaScript in a static resource, then calling it from there. `<apex:includeScript value="{!$Resource.MyJavascriptFile}"/>`
