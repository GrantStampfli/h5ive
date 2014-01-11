h5ive
=====

A collection of thin facade APIs wrapped around HTML5 JavaScript features. The goal is to provide a simple layer of abstraction on top of the native APIs, to insulate you the developer (and more importantly, your production code!) from potential inconsistencies, bugs, and even specification changes.

Want more information about the motivations behind this project? [Nicholas Zakas](http://twitter.com/slicknet) wrote a fantastic article: [The Problem with Native JavaScript APIs](http://oreillynet.com/oreilly/javascript/radarreports/native-javascript-apis.csp), which was my inspiration for the h5ive project. Also, check out my slide-deck for [Stop Using Native HTML](https://speakerdeck.com/u/getify/p/stop-using-native-html5-v5) (video will be posted from this talk ASAP).

This is **not** a "HTML5 shim|v" for semantic tags. It is **not** a library or framework. It is **not** a polyfill for older browsers. It is **not** a replacement for Modernizr (though it *will* have basic feature tests for the APIs it wraps).

Some API sugar flavor will be included, but do not expect for this library to be as sugary as something like jQuery. You can wrap other abstraction layers easily on top of h5ive.

Testing
=======

It will be an important (read: mandated) part of the culture of this project that all code which is submitted must have some reasonable tests. 

First and foremost, each module starts with an example usage of the API (see "Contributions" below), so the eventual submitted code for that module must at a minimum actually "pass" the test of being able to run the example API we agree on.

Moreover, contributors should make a good effort to provide one or more integration tests (unit tests not necessarily required), which ideally will be automatable.

We have not yet, as a project, chosen a specific testing framework or approach, so these statements are not mandating how the tests are written, only that there must be a good faith effort to provide tests along with code. A first priority will be to write tests for the code which is already in this repository.

Contributions
=============
Contributions are obviously welcomed and encouraged. But let's be a little bit intentional about how we want this to work. Here are some suggestions for how to be most friendly in terms of contributions:

1. Pick of one the native HTML5 APIs that you have some familiarity with, perhaps from this list:

   ```
   History
   Web Workers
   Web Sockets
   Geolocation
   <audio> / <video>
   File / FileSystem
   Web DBs
   BlobBuilder
   Blob URLs
   FormData
   Device APIs
   Server-Sent Events
   appCache
   Web Intents
   registerProtocolHandler
   ```

2. This project will follow "example-driven development" practices. Make an `example-{WRAPPER_NAME}.js` file that illustrates how you think the API facade will/should be used.

 This doesn't have to show all possible variations, and it's not a "contract" etched in stone. But it should illustrate the major use-case(s).

3. Submit a pull-request with **only** your example file, and explain the API facade you are proposing. We'll discuss it in that pull request.

4. Once we feel that the API facade is in good shape, amend your pull request to include a sample implementation (named `{WRAPPER_NAME}.h5ive.js`, and we'll take it from there. **NOTE:** please also include one or more tests along with the module's implementation (see "Testing" above).


Also, **PLEASE** avoid these things:

1. Reformatting this project's code style (we'll decide on a code-style later). Leave spaces, tabs, and semi-colons in existing files alone.

2. Rewrite this project in some other language (including Coffeescript). This is a JavaScript project. We write JavaScript here. Period.

3. Convince us that we shouldn't do this, or that some Project XYZ is already doing it better, etc. We'll take any valid, good-faith suggestions from any open-source project, but the goals of this project are unique and will not be shoe-horned into any other project's goals.

4. Worry too much about stuff like if this will be AMD-compliant or whatever. We'll decide on all that stuff later. There will be a build-tool, and it'll have options for you to pick which flavor you prefer.


h5ive.js
========

This single file is what you will include in your HTML5 JavaScript projects. It will eventually be customizable with a build-tool, which will let you pick which "module format" (AMD, CommonJS, customized module, etc) you prefer, and then include only which API modules you need.

The entire API will be under the `h5` namespace. For instance, XHR2 will be exposed as `h5.xhr`.


License
=======

The code and all the documentation are released under the MIT license.

http://getify.mit-license.org/
