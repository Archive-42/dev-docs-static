# GlobalEventHandlers.onabort

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

**Draft**

This page is not complete.

The `onabort` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is the [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) for processing `abort` events sent to the window.

While the [standard for aborting a document load](https://html.spec.whatwg.org/multipage/browsing-the-web.html#abort-a-document) is defined, [HTML issue \#3525](https://github.com/whatwg/html/issues/3525) suggests that browsers should not currently fire the `abort` event on a `Window` that would trigger `onabort` to be called.

TODO: define what "abort" is. Closing the window via window manager? Stopping the load of the page? By which means and reasons (user, network/server)? At which stages would it fire / be caught? For IE, `onabort` is only available with `<img>` tags.

## Syntax

    window.onabort = functionRef;

### Value

`functionRef` is a function name or a [function expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/function).

## Example

    window.onabort = function() {
      alert('Load aborted.');
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onabort">HTML Living Standard<br />
<span class="small">The definition of 'onabort' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`onabort`

1

12

9

9

≤12.1

1

1

18

9

≤12.1

1

1.0

This property is not available with Firefox 2 or Safari.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onabort</a>
