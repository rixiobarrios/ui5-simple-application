## UI5 Simple Application

Taken from this [video](https://www.youtube.com/watch?v=J9NMwsipMkw)

Step 1 - Build index.html file  
```
<!DOCTYPE html>
    <html lang="en">
    <head>
        <script id="sap-ui-bootstrap"
            src="https://sapui5.hana.ondemand.com/resources/sap-ui-core.js"
            data-sap-ui-theme="sap_belize"
            data-sap-ui-libs="sap.m"
            data-sap-ui-compatVersion="edge"
            data-sap-ui-async="true"
            data-sap-ui-oninit="module:sap/ui/demo/index"
            data-sap-ui-resourceroots='{
                "sap.ui.demo": "./"
                }'>
        </script>
    </head>
    <body class="sapUiBody" id="content">
        
    </body>
    </html>
```
 

Step 2 - Build the index.js file  
```
sap.ui.define([
            "sap/m/Button"

    ], function (Button) {
        "use strict";

        new Button({
            text: "Hello World"    
        }).placeAt("content");
    });
```

Step 3 - Spin a server

Step 4 - Install Node  
```npm init -y```

Step 5 - Install UI5 CLI  
```npm install --global @ui5/cli```

Step 6 - Create the webapp folder in the root and drag index.html and index.js into it

Step 7 - Run the ui5 init command  
```ui5 init```

Step 8 - Create manifest.json file in the webapp folder

Step 9 - Enter the following code into your manifest.json file  
```
{
    "sap.app": {
        "id": "ui5"
    }
}
```

Step 10 - Start the web server locally  
``` ui5 serve```

Step 11 - You should see the followwing message
```
Server started
URL: http://localhost:8080
```
Step 12 - Go to the following url  
http://localhost:8080/index.html

Step 13 - You should see the "hello World" message

Step 14 - Define controls in an XML file

Step 15 - Create App.view.xml file in your webapp folder

Step 16 - Enter the following code into your App.view.xml file  with a Text control
```
<mvc:View
    xnlns="sap.m"
    xnlns:mvc="sap.ui.core.mvc">
    <Text text="Hello World"/>
</mvc:View>    
```

Step 17 - Import the XML view in your index.js file and point it to our XML file 
```
sap.ui.define([
        "sap/m/Button",
        "sap/ui/core/mvc/XMLView"
], function (Button, XMLView) {
    "use strict";

    XMLView.create({
        viewName: "sap.iu.demo.App"
    }).then(function(oView) {
        oView.placeAt("content");
    })

    new Button({
        text: "Hello World"    
    }).placeAt("content");
});
```

App should display both "Hello World" messages with and without the button!