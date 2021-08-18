# HashChangeEvent

The `HashChangeEvent` interface represents events that fire when the fragment identifier of the URL has changed.

The fragment identifier is the part of the URL that follows (and includes) the `#` symbol.

## Properties

_This interface also inherits the properties of its parent, [`Event`](event)._

[`HashChangeEvent.newURL`](hashchangeevent/newurl) <span class="badge inline readonly">Read only </span>  
The new URL to which the window is navigating.

[`HashChangeEvent.oldURL`](hashchangeevent/oldurl) <span class="badge inline readonly">Read only </span>  
The previous URL from which the window was navigated.

## Methods

_This interface has no methods of its own, but inherits the methods of its parent, [`Event`](event)._

## Examples

### Syntax options for a hash change

You can listen for the `hashchange` event using any of the following options:

    window.onhashchange = funcRef;

**or**

    <body onhashchange="funcRef();">

**or**

    window.addEventListener("hashchange", funcRef, false);

### Basic example

    function locationHashChanged() {
      if (location.hash === '#somecoolfeature') {
        somecoolfeature();
      }
    }

    window.addEventListener('hashchange', locationHashChanged);

## Polyfill

There are several fallback scripts listed on the [Modernizr GitHub page](https://github.com/Modernizr/Modernizr/wiki/HTML5-Cross-Browser-Polyfills). Basically, those scripts check the `hash` property of [`Window.location`](window/location) at a regular interval. Here is a version that allows only one handler to be bound to the [`onhashchange`](windoweventhandlers/onhashchange) property:

    ;(function(window) {

      // Exit if the browser implements that event
      if ( "onhashchange" in window.document.body ) { return; }

      var location = window.location,
          oldURL = location.href,
          oldHash = location.hash;

      // Check the location hash on a 100ms interval
      setInterval(function() {
        var newURL = location.href,
            newHash = location.hash;

        // If the hash has changed and a handler has been bound...
        if ( newHash != oldHash && typeof window.onhashchange === "function" ) {
          // Execute the handler
          window.onhashchange({
            type: "hashchange",
            oldURL: oldURL,
            newURL: newURL
          });

          oldURL = newURL;
          oldHash = newHash;
        }
      }, 100);

    })(window);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#the-hashchangeevent-interface">HTML Living Standard<br />
<span class="small">The definition of 'HashChangeEvent' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

## Browser compatibility

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

`HashChangeEvent`

5

12

3.6

8

10.6

5

≤37

Yes

4

11

5

Yes

`newURL`

Yes

12

6

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`oldURL`

Yes

12

6

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

## Related events

- `hashchange`
- `popstate`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HashChangeEvent</a>
