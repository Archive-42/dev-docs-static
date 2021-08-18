# Element.ariaBusy

The `ariaBusy` property of the [`Element`](../element) interface reflects the value of the `aria-busy` attribute, which indicates whether an element is being modified, as assistive technologies may want to wait until the modifications are complete before exposing them to the user.

## Syntax

    var ariaBusy = element.ariaBusy;
    element.ariaBusy = ariaBusy

### Value

A [`DOMString`](../domstring) with one of the following values:

`"true"`  
There are no expected updates for the element.

`"false"`  
The element is being updated.

## Examples

In this example the `aria-busy` attribute on the element with an ID of `clock` is set to "false". Using `ariaBusy` we update the value to "true".

    <div id="clock" role="timer" aria-live="polite" aria-atomic="true" aria-busy="false"></div>

    let el = document.getElementById('clock');
    console.log(el.ariaBusy); // false
    el.ariaBusy = "true"
    console.log(el.ariaBusy); // true

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-ariabusy">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaBusy' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaBusy`

81

81

No

No

68

12.1

81

81

No

58

12.2

13.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaBusy" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaBusy</a>
