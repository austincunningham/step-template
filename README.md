# Step Template

## Introduction 
This the base template for building a Workforc Management step. This is a simple form for first name 
last name and form results.  

## Using this template
Copy this repo and add to step directory in [raincatcher-angular](https://github.com/feedhenry-raincatcher/raincatcher-angularjs). Each step should have a form and results/view section . 
To customise the base step modify the html templates for 

*Form view*
    step-base/lib/angular/template/base-form.tpl.html

*Results view*  
    step-base/lib/angular/template/base.tpl.html

Once the html templates are edited you need to use grunt to build using [wfmTemplate](https://www.npmjs.com/package/fh-wfm-template-build) using the following command. 

    grunt wfmTemplate:build


## Adding step to raincatcher-angularjs demo/mobile
Add step to mobiles package.json as a package demo/mobile/package.json
 
    "@raincatcher/step-base": "0.0.1",

Add step to mobiles demo/mobile/src/app/app.js

    // apply a variable name to the module
    Var variableName = require(‘@raincatcher/step-base’);

    // add ngModule() for the module to angular.module array;
    variableName.ngModule();

Import the step scss for step-base into demo/mobile/src/sass/app.scss
    @import 'node_modules/@raincatcher/step-signature/lib/signature.scss';

## Adding step to raincatcher-angularjs demo/portal

Add step package to package.json
demo/portal/package.json    
E.g 
"@raincatcher/step-signature": "0.0.1",                

Add step to portal in angular.modules
demo/portal/src/app/main.js
E.g.
var signatureStep = require('@raincatcher/step-signature');

Add step definition to angular.modules
stepDefinitions
E.g 
stepDefinitions: [
    vehicleInspectionStep.definition,
    accidentStep.definition,
    signatureStep.definition ]


Also add step ngModule() in angular.modules
E.g. 
signatureStep.ngModule()

Import the step scss 
demo/portal/src/sass/portal.scss
E.g 
@import 'node_modules/@raincatcher/step-signature/lib/signature.scss';















