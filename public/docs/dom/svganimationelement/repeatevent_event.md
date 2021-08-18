SVGAnimationElement: repeatEvent event
======================================

The `repeatEvent` event of the [`SVGAnimationElement`](../svganimationelement) interface is fired when the element's local timeline repeats. It will be fired each time the element repeats, after the first iteration.

**Note**: Associated with the `repeatEvent` event is an integer that indicates which repeat iteration is beginning; this can be found in the `detail` property of the event object. The value is a 0-based integer, but the repeat event is not raised for the first iteration and so the observed values will be &gt;= 1. This is supported in Firefox, but not in Chrome.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../timeevent"><code>TimeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onrepeat</code></td></tr></tbody></table>

Examples
--------

### Animated circle

    <svg xmlns="http://www.w3.org/2000/svg" width="300px" height="100px">
      <title>SVG SMIL Animate with Path</title>
      <circle cx="0" cy="50" r="50" fill="blue" stroke="black" stroke-width="1">
        <animateMotion
           path="M 0 0 H 300 Z"
           dur="5s" repeatCount="indefinite" />
      </circle>
    </svg>

    <hr>

    <ul>

    </ul>

    ul {
      height: 100px;
      border: 1px solid #ddd;
      overflow-y: scroll;
      padding: 10px 30px;
    }

    let svgElem = document.querySelector('svg');
    let animateElem = document.querySelector('animateMotion');
    let list = document.querySelector('ul');

    animateElem.addEventListener('beginEvent', () => {
      let listItem = document.createElement('li');
      listItem.textContent = 'beginEvent fired';
      list.appendChild(listItem);
    })

    animateElem.addEventListener('repeatEvent', (e) => {
      let listItem = document.createElement('li');
      let msg = 'repeatEvent fired';
      if(e.detail) {
        msg += '; repeat number: ' + e.detail;
      }
      listItem.textContent = msg;
      list.appendChild(listItem);
    })

### Event handler property equivalent

Note that you can also create an event listener for the `repeat` event using the `onrepeat` event handler property:

    animateElem.onrepeat = () => {
      console.log('repeatEvent fired');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#interact-RepeatEvent">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'repeatEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`repeatEvent_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

?

?

?

Yes

See also
--------

-   [SVG animation with SMIL](https://developer.mozilla.org/en-US/docs/Web/SVG/SVG_animation_with_SMIL)
-   `beginEvent`
-   `endEvent`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement/repeatEvent_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement/repeatEvent_event</a>
