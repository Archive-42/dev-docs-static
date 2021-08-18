WindowEventHandlers.onhashchange
================================

The `WindowEventHandlers.onhashchange` property of the [`WindowEventHandlers`](../windoweventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `hashchange` events.

The `hashchange` event fires when a window's hash changes (see [`Window.location`](../window/location) and [`HTMLHyperlinkElementUtils.hash`](../htmlanchorelement/hash)).

Syntax
------

**Using an event handler:**

    window.onhashchange = funcRef;

**Using an HTML event handler:**

    <body onhashchange="funcRef();">

**Using an event listener:**

To add an event listener, use [`addEventListener()`](../eventtarget/addeventlistener):

    window.addEventListener("hashchange", funcRef, false);

### Parameters

`funcRef`  
A reference to a function.

Examples
--------

### Using an event handler

This example uses an event handler (`window.onhashchange`) to check the new hash value whenever it changes. If it equals `#cool-feature`, the script logs a message to the console.

    function locationHashChanged() {
      if (location.hash === '#cool-feature') {
        console.log("You're visiting a cool feature!");
      }
    }

    window.onhashchange = locationHashChanged;

### Using an event listener

This example uses an event listener to log a notification whenever the hash has changed.

    function hashHandler() {
      console.log('The hash has changed!');
    }

    window.addEventListener('hashchange', hashHandler, false);

### Overriding the hash

This function sets a new hash dynamically, setting it randomly to one of two values.

    function changeHash() {
      location.hash = (Math.random() > 0.5) ? 'location1' : 'location2';
    }

The hashchange event
--------------------

The dispatched `hashchange` event has the following properties:

<table><thead><tr class="header"><th>Field</th><th>Type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>newURL</code></td><td><code>DOMString</code></td><td>The new URL to which the window is navigating.</td></tr><tr class="even"><td><code>oldURL</code></td><td><code>DOMString</code></td><td>The previous URL from which the window was navigated.</td></tr></tbody></table>

### Polyfill for event.newURL and event.oldURL

    // Let this snippet run before your hashchange event binding code
    if (!window.HashChangeEvent)(function(){
      var lastURL = document.URL;
      window.addEventListener("hashchange", function(event){
        Object.defineProperty(event, "oldURL", {enumerable:true,configurable:true,value:lastURL});
        Object.defineProperty(event, "newURL", {enumerable:true,configurable:true,value:document.URL});
        lastURL = document.URL;
      });
    }());

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#handler-window-onhashchange">HTML Living Standard<br />
<span class="small">The definition of 'onhashchange' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/#windoweventhandlers">HTML 5.1<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#windoweventhandlers">HTML5<br />
<span class="small">The definition of 'GlobalEventHandlers' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

Browser compatibility
---------------------

Desktop

Mobile

Chrome

Edge

Firefox

Internet Explorer

Opera

Safari

WebView Android

Chrome Android

Firefox for Android

Opera Android

Safari on IOS

Samsung Internet

`onhashchange`

5

12

3.6

8

10

5

≤37

18

4

10.1

5

1.0

See also
--------

-   `hashchange` event
-   [Manipulating the browser history](../history_api)
-   [`history.pushState()` and `history.replaceState()`](../window/history) methods
-   [`WindowEventHandlers.onpopstate`](onpopstate)
-   [`HTMLHyperlinkElementUtils.hash`](../htmlanchorelement/hash)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WindowEventHandlers/onhashchange</a>
