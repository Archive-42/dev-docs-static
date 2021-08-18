# EventTarget()

The `EventTarget()` constructor creates a new [`EventTarget`](../eventtarget) object instance.

## Syntax

    var myEventTarget = new EventTarget();

### Parameters

None.

### Return value

An instance of the [`EventTarget`](../eventtarget) object.

## Examples

    class MyEventTarget extends EventTarget {
      constructor(mySecret) {
        super();
        this._secret = mySecret;
      }

      get secret() { return this._secret; }
    };

    let myEventTarget = new MyEventTarget(5);
    let value = myEventTarget.secret;  // == 5
    myEventTarget.addEventListener("foo", function(e) {
      this._secret = e.detail;
    });

    let event = new CustomEvent("foo", { detail: 7 });
    myEventTarget.dispatchEvent(event);
    let newValue = myEventTarget.secret; // == 7

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-eventtarget-eventtarget">DOM<br />
<span class="small">The definition of 'EventTarget() constructor' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`EventTarget`

64

79

59

No

51

14

64

64

59

47

14

9.0

## See also

- [`EventTarget`](../eventtarget)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/EventTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/EventTarget/EventTarget</a>
