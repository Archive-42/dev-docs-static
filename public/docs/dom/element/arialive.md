# Element.ariaLive

The `ariaLive` property of the [`Element`](../element) interface reflects the value of the `aria-live` attribute, which indicates that an element will be updated, and describes the types of updates the user agents, assistive technologies, and user can expect from the live region.

## Syntax

    var ariaLive = element.ariaLive;
    element.ariaLive = ariaLive

### Value

A [`DOMString`](../domstring) with one of the following values:

`"assertive"`  
Indicates that updates to the region have the highest priority and should be presented the user immediately.

`"off"`  
Indicates that updates to the region should not be presented to the user unless the user is currently focused on that region.

`"polite"`  
Indicates that updates to the region should be presented at the next graceful opportunity, such as at the end of speaking the current sentence or when the user pauses typing.

## Examples

In this example the `aria-live` attribute on the element with an ID of `planetInfo` is set to "polite". We then update the value to "assertive".

    <div role="region" id="planetInfo" aria-live="polite">
      <h2 id="planetTitle">No planet selected</h2>
      <p id="planetDescription">Select a planet to view its description</p>
    </div>

    let el = document.getElementById('planetInfo');
    console.log(el.ariaLive); // "polite"
    el.ariaLive = "assertive";
    console.log(el.ariaLive); // assertive

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/wai-aria-1.2/#dom-ariamixin-arialive">Accessible Rich Internet Applications (WAI-ARIA) 1.2<br />
<span class="small">The definition of 'ariaLive' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`ariaLive`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLive" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/ariaLive</a>
