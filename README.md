# Javascript in Visualforce Pages
* The best method for including JavaScript in a Visualforce page is placing the JavaScript in a static resource, then calling it from there. `<apex:includeScript value="{!$Resource.MyJavascriptFile}"/>`
* When using JavaScript within an expression, you need to escape quotes using a backslash (\). For example: 
`onclick="{!IF(false, 'javascript_call(\"js_string_parameter\")', 'else case')}"`
* A DOM ID is constructed from a combination of the id attribute of the component and the id attributes of all components that contain the element.
* `<apex:page>
    <apex:includeScript value="{!$Resource.jquery}"/>
</apex:page>`
