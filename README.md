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
* JavaScript remoting is a tool that front-end developers can use to make an AJAX request from a Visualforce page directly to an Apex controller. JavaScript remoting allows you to run asynchronous actions by decoupling the page from the controller and to perform tasks on the page without having to reload the entire page.
* JavaScript remoting is the most efficient way of calling the controller and passing data in from the page, because you can ensure that you’re passing only the data that you need each time that you make a call.
* Remote Objects is well-suited to pages that need to perform only simple Create-Read-Update-Delete, or “CRUD”, object access. JavaScript Remoting is better suited to pages that access higher-level server actions. Remote Objects lets you get up and running quickly without a lot of ceremony, while JavaScript Remoting is suited for more complex applications that require some up front API-style design work.

### Javascript Remoting
* Requires both JavaScript and Apex code
* Supports complex server-side application logic
* Handles complex object relationships better
* Uses network connections (even) more efficiently

### Visualforce Remote Objects
* Makes basic “CRUD” object access easy
* Doesn’t require any Apex code
* Supports minimal server-side application logic
* Doesn’t provide automatic relationship traversals; you must look up related objects yourself

1. Remote Objects components that specify which objects and fields to make accessible on the page.
2. jsShorthand attribute, which maps the full Salesforce API name to a simpler, shorter name to use in your JavaScript code. 
3. 

### Retrieving Records With Remote Objects
* Retrieve records by calling `retrieve()` on a Remote Object model instance.
* `retrieve()` requires two arguments, one for query criteria and one for a callback handler:
```javascript
RemoteObjectModel.retrieve({criteria}, callback_function)
```
* `criteria` can be a Remote Objects' query object or a function that returns one.  The following two calls are equivalent:
```javascript
var ct = new RemoteObjectModel();

// Empty callback functions for simplicity
ct.retrieve({where: {FirstName: {eq: 'Marc'}}}, function() {}); //query object

ct.retrieve(function() {
 return({where: {FirstName: {eq: 'Marc'}}});
 }, function() {}); // function returning query object
```
