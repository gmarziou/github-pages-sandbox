### Using the Java server and Gulp together
_We highly recommend you use this feature, as it allows to have live reloading of your client-side code._

You can use Gulp to work on the client-side JavaScript application:

`gulp`

(this will run our default Gulp task, `serve`)

This should open up your Web browser, with live reload enabled, on [http://localhost:9000](http://localhost:9000). This works thanks to [BrowserSync](http://www.browsersync.io/), and you can access its administration screen on [http://localhost:3001](http://localhost:3001).

This provides below very impressive features:

*   As soon as you modify one of your HTML/CSS/JavaScript file, your browser will refresh itself automatically
*   As soon as you add/remove a javascript file it will be added to the `index.html`, your browser will refresh itself automatically
*   When you test your application on several different browsers or devices, all your clicks/scrolls/inputs should be automatically synchronized on all screens

This Gulp task has a proxy to the REST endpoints on the Java server which we just launched (on [http://localhost:8080/api](http://localhost:8080/api)), so it should be able to do live REST requests to the Java back-end.

If you have generated your application with the Sass option, your templates should also be automatically compiled into CSS.

_Tips'n tricks_

*   In some browsers (like Chrome), your HTML/CSS/JS resources can be cached, and hence can have some trouble getting live-reloaded. To force them to be reloaded, open up the "developer console" and select "Disable cache (while DevTools is open)".
*   As the Gulp server proxies request to the Java server, all REST requests will fail if the Java server is down. So if your Gulp server shows a blank screen, the first thing to check is if the Java server is running at `http://127.0.0.1:8080`.
