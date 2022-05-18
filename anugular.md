## Angular
* Angular is a framework which allows you to create reactive, single page applicdcations. This sounds great, but
* A Single Page Application (SPA)
  * you can see that we seem to visit different pages, but in the end, our page never changes.
  * It's only one HTML file and a bunch of JavaScript code we got from the server and everything which you see here
  * every change, is rendered in the browser.
* It gives the user a very reactive user experience (UX).
* JavaScript is much faster than having to reach out to a server for every page change and for every new piece of data you want to display.
* Therefore, this approach allows you to create web applications which look and feel almost like mobile applications; very fast!
* If you do need some data from a server, you simply load it in the background so that the user never leaves this experience of having a reactive web application to use.
## So, how is this done?
* Well, JavaScript changes the DOM, changes whatever is displayed here (in the browser), by changing the HTML code during runtime (so to say). That is why you never see the refresh icon on the top-left spin; because we're only changing the currently-loaded page. You can even see that if you inspect the source code of a page like this.
* source code of the web app (develeoper mode) wont show all the content thats getting displayed

## Angular version
* angularjs(angular 1) -> angular 2 is totally different
* now anugular 2,4,.....14 new version every 6 months: All backward compatitle
*  its simply referred as Angular now
## CLI & NodeJs
* install nodejs
* npm install -g @angular/cli@latest
* ng new my-first-app --no-strict (create project)
* ng serve (run application)
  *  run on default port 4200
```
<input type="text" [(ngModel)]="name">
<p>{{name}}</p>
import form module also in app.module.ts
import { FormsModule } from '@angular/forms';
```
## What is typescript
* Typescript, really is just a superset of JavaScript.
* It offers more features than vanilla JavaScript, like classes, interfaces and, very important, which gives it the name, types; strong typing.
* So, you define in Typescript if a certain variable is a number, a string or something else.
* There, you have dynamic typing.
* in typescript assigning wrong type gives error
* typescript doesnt run in browser, so its compiled in CLI to JavaScript
## adding bootstrap
* npm install --save bootstrap@3
* edit angular.json
  * add boostrap.css to styles section
## How it works
* index.html holds app-root tag which defines the applications
* ng new my-01-app --no-strict
* npm install --save bootstrap@3
* ng serve
* app.component.ts file defines the selector
```
  selector: 'app-root',
```
* when you run ng serve, the index.html is rebuild by cli to inject the scripts which binds app-root from the component folder
* main.ts ties all of these together, below line tell the module
```
import { AppModule } from './app/app.module';
```  
* this app.module.ts file refer to app.component.ts file which has html and css references
```
import { AppComponent } from './app.component';
```
* entire application is split into reusable component
  * header
  * body
  * menu  
* all components are reusable
## Component
* component is typescript class
* create new folder under app folder(server)
 * server.component.ts
 * add the newly created component into app.module.ts
 ```
 import { Component } from "@angular/core";
 @Component{(
   selector: 'app-server',
   templateUrl: './server.component.html'
 )}
 export class ServerComponent{

 }
//add in app.module.ts
 import { ServerComponent } from './server/server.component'
 declarations: [
   AppComponent,
   ServerComponent
 ],
```
* easy way is to use CLI command to create new component
* ng generate component servers or ng g c servers
* templateUrl to refer external
* template can be used for inline html code
* templateUrl or template is mandatory
* styleUrls or style (for inline style)
* selector has to be unique
  * can be made attribute by giving name inside [app-servers]
  * can be made as class by giving name as '.app-severs'

## Databinding
* Databinding = communication
* communication between typescript(business logic) code and html template(display it)
  * output Databinding
    * string interpolation: {{data}}
    * property binding: [property] = "data"
  * user events
    * event binding (event) = expression
  * Two way Databinding
    * [(ngModel)] ="data"
    
