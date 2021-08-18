# GlobalEventHandlers.onload

The `onload` property of the [`GlobalEventHandlers`](../globaleventhandlers) mixin is an [`EventHandler`](https://developer.mozilla.org/en-US/docs/Web/Events/Event_handlers) that processes `load` events on a [`Window`](../window), [`XMLHttpRequest`](../xmlhttprequest), [`<img>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img) element, etc.

The `load` event fires when a given resource has loaded.

## Syntax

    target.onload = functionRef;

### Value

`functionRef` is the handler function to be called when the window’s `load` event fires.

## Examples

    window.onload = function() {
      init();
      doSomethingElse();
    };

    <!doctype html>
    <html>
      <head>
        <title>onload test</title>
        // ES5
        <script>
          function load() {
            console.log("load event detected!");
          }
          window.onload = load;
        </script>
        // ES2015
        <script>
          const load = () => {
            console.log("load event detected!");
          }
          window.onload = load;
        </script>
      </head>
      <body>
        <p>The load event fires when the document has finished loading!</p>
      </body>
    </html>

## Notes

The `load` event fires at the end of the document loading process. At this point, all of the objects in the document are in the DOM, and all the images, scripts, links and sub-frames have finished loading.

There are also [DOM Events](https://developer.mozilla.org/en-US/docs/Web/Events) like `DOMContentLoaded` and `DOMFrameContentLoaded` (which can be handled using [`EventTarget.addEventListener()`](../eventtarget/addeventlistener)) which are fired after the DOM for the page has been constructed, but do not wait for other resources to finish loading.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/webappapis.html#handler-onload">HTML Living Standard<br />
<span class="small">The definition of 'onload' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition</td></tr></tbody></table>

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

`onload`

1

12

1

9

9

3

1

18

4

10.1

1

1.0

## See also

- `load` event
- `DOMContentLoaded` event in [Listening to events: Simple DOM events](https://developer.mozilla.org/en-US/docs/Listening_to_events_in_Firefox_extensions#Simple_DOM_events)
- IIFE [Immediately-invoked function expression](https://en.wikipedia.org/wiki/Immediately-invoked_function_expression)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/GlobalEventHandlers/onload</a>
