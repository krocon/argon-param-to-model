# #AskPolymer
 
##What is the best way to get (parse) url parameter values (on page load)?

###Question details

Example url:
http://localhost:63342/argon-epub-reader/epub.html?epub=demo/data/pg2701.epub
 
1. app-location / app-route with query-params="{{queryParams}}" __or__
2. window.Polymer.Settings __or__
3. &lt;argon-param-to-model/>  with ArgonParamToModelBehavior __?__

 
 
####1) app-location / app-route with query-params="{{queryParams}}"
```
<app-location route="{{route}}"></app-location>
<app-route
        route="{{route}}"
        pattern="/:page"
        data="{{data}}"
        tail="{{tail}}"
        query-params="{{queryParams}}">
…
observers:[
    'onRouteChanged(route)'
],
onRouteChanged: function(route){
    console.info('this.data', this.data);
    console.info('this.route', this.route);
    console.info('this.page', this.page);
    console.info('this.tail', this.tail);
    console.info('this.queryParams', this.queryParams); // ß params as object
},
``` 
 
####2) window.Polymer.Settings (see polymer-micro.html)
```
ready: function () {
    var epub = Polymer.Settings.epub;
    console.info('epub ', epub);
}
``` 
 
####3) &lt;argon-param-to-model/>  with ArgonParamToModelBehavior
There's a tag for everything:
``` 
<argon-param-to-model/> 
 
ready: function () {
    console.info('epub', this.epub);
}
```