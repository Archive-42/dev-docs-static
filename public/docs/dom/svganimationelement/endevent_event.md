SVGAnimationElement: endEvent event
===================================

The `endEvent` event of the [`SVGAnimationElement`](../svganimationelement) interface is fired when at the active end of the animation is reached.

**Note**: This event is not raised at the simple end of each animation repeat. This event may be raised both in the course of normal (i.e. scheduled or interactive) timeline play, as well as in the case that the element was ended with a DOM method.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../timeevent"><code>TimeEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><code>onend</code></td></tr></tbody></table>

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

    <button>Stop animation</button>

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
    let btn = document.querySelector('button');

    animateElem.addEventListener('beginEvent', () => {
      let listItem = document.createElement('li');
      listItem.textContent = 'beginEvent fired';
      list.appendChild(listItem);
    })

    animateElem.addEventListener('endEvent', () => {
      let listItem = document.createElement('li');
      listItem.textContent = 'endEvent fired';
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

    btn.addEventListener('click', () => {
      btn.disabled = true;
      animateElem.setAttribute('repeatCount', '1');
    })

### Event handler property equivalent

Note that you can also create an event listener for the `end` event using the `onend` event handler property:

    animateElem.onend = () => {
      console.log('endEvent fired');
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://svgwg.org/svg2-draft/single-page.html#interact-EndEvent">Scalable Vector Graphics (SVG) 2<br />
<span class="small">The definition of 'endEvent' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`endEvent_event`

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
-   `repeatEvent`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement/endEvent_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/SVGAnimationElement/endEvent_event</a>
