# Javascript in Visualforce Pages
* The best method for including JavaScript in a Visualforce page is placing the JavaScript in a static resource, then calling it from there. `<apex:includeScript value="{!$Resource.MyJavascriptFile}"/>`
* When using JavaScript within an expression, you need to escape quotes using a backslash (\). For example: 
`onclick="{!IF(false, 'javascript_call(\"js_string_parameter\")', 'else case')}"`
* A DOM ID is constructed from a combination of the id attribute of the component and the id attributes of all components that contain the element.
* `<apex:page>
    <apex:includeScript value="{!$Resource.jquery}"/>
</apex:page>`

## JavaScript Remoting for Apex Controllers
* Use JavaScript remoting in Visualforce to call methods in Apex controllers from JavaScript. Create pages with complex, dynamic behavior that isn’t possible with the standard Visualforce AJAX components.
* Features implemented using JavaScript remoting require three elements:
    * The remote method invocation you add to the Visualforce page, written in JavaScript.
    * The remote method definition in your Apex controller class. This method definition is written in Apex, but there are some important differences from normal action methods.
    * The response handler callback function you add to or include in your Visualforce page, written in JavaScript.
