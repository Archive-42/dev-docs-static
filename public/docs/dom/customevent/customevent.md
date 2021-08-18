# CustomEvent()

The `CustomEvent()` constructor creates a new [`CustomEvent`](../customevent).

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

     event = new CustomEvent(typeArg, customEventInit);

### Parameters

`typeArg`  
A [`DOMString`](../domstring) representing the name of the event.

`customEventInit` <span class="badge inline optional">Optional</span>  
A `CustomEventInit` dictionary, having the following fields:

- `"detail"`, optional and defaulting to `null`, of type any, that is an event-dependent value associated with the event.

The `CustomEventInit` dictionary also accepts fields from the [`EventInit`](../event/event) dictionary.

### Return value

A new `CustomEvent` object of the specified type, with any other properties configured according to the `CustomEventInit` dictionary (if one was provided).

## Example

    // add an appropriate event listener
    obj.addEventListener("cat", function(e) { process(e.detail) });

    // create and dispatch the event
    var event = new CustomEvent("cat", {
      detail: {
        hazcheeseburger: true
      }
    });
    obj.dispatchEvent(event);

Additional examples can be found at [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events).

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-customevent-customevent">DOM<br />
<span class="small">The definition of 'CustomEvent()' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CustomEvent`

15

12

11

No

11.6

6.1

≤37

18

14

12

6.1

1.0

## Polyfill

You can polyfill the `CustomEvent()` constructor functionality in Internet Explorer 9 and higher with the following code:

    (function () {

      if ( typeof window.CustomEvent === "function" ) return false;

      function CustomEvent ( event, params ) {
        params = params || { bubbles: false, cancelable: false, detail: null };
        var evt = document.createEvent( 'CustomEvent' );
        evt.initCustomEvent( event, params.bubbles, params.cancelable, params.detail );
        return evt;
       }

      window.CustomEvent = CustomEvent;
    })();

Internet Explorer &gt;= 9 adds a CustomEvent object to the window, but with correct implementations, this is a function.

## See also

- [`CustomEvent`](../customevent)
- [Creating and triggering events](https://developer.mozilla.org/en-US/docs/Web/Events/Creating_and_triggering_events)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/CustomEvent</a>
