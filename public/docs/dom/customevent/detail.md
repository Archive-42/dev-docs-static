# CustomEvent.detail

The `detail` readonly property of the [`CustomEvent`](../customevent) interface returns any data passed when initializing the event.

**Note:** This feature is available in [Web Workers](../web_workers_api).

## Syntax

     let myDetail = customEventInstance.detail;

### Return value

Whatever data the event was initialized with.

## Example

    // add an appropriate event listener
    obj.addEventListener("cat", function(e) { process(e.detail) });

    // create and dispatch the event
    let event = new CustomEvent("cat", {
      detail: {
        hazcheeseburger: true
      }
    });
    obj.dispatchEvent(event);

    // Will return an object containing the hazcheeseburger property
    let myDetail = event.detail;

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-customevent-detail">DOM<br />
<span class="small">The definition of 'detail' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`detail`

15

12

11

No

11.6

6.1

≤37

Yes

14

Yes

6.1

Yes

## See also

- [`CustomEvent`](../customevent)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/detail" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CustomEvent/detail</a>
