# Element: overflow event

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `overflow` event is fired when an element has been overflowed by its content or has been rendered for the first time in this state (only works for elements styled with overflow != visible).

It is a proprietary event specific to Gecko (Firefox).

<table><tbody><tr class="odd"><td>Bubbles</td><td>Yes</td></tr><tr class="even"><td>Cancelable</td><td>Yes</td></tr><tr class="odd"><td>Interface</td><td><a href="../uievent"><code>UIEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td>Unknown</td></tr></tbody></table>

## Examples

    <div id="wrapper">
        <div id="child"></div>
    </div>
    <br/>
    <label><input type="checkbox" id="toggle" checked/> Overflow</label>

    <style>
     #wrapper {
        width: 20px;
        height: 20px;
        background: #000;
        padding: 5px;
        overflow: hidden;
      }

      #child {
        width: 40px;
        height: 40px;
        border: 2px solid grey;
        background: #ccc;
      }
    </style>

    <script>
      var wrapper = document.getElementById("wrapper"),
          child = document.getElementById("child"),
          toggle = document.getElementById("toggle");

      wrapper.addEventListener("overflow", function( event ) {
          console.log( event );
      }, false);

      wrapper.addEventListener("underflow", function( event ) {
          console.log( event );
      }, false);

      toggle.addEventListener("change", function( event ) {
          if ( event.target.checked ) {
              child.style.width = "40px";
              child.style.height = "40px";
          } else {
              child.style.width = "10px";
              child.style.height = "10px";
          }

      }, false);
    </script>

## Specifications

Not part of any specification.

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

`overflow_event`

No

No

Yes

No

No

No

No

No

Yes

No

No

No

## See also

- Related events: [`underflow`](underflow_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/overflow_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/overflow_event</a>
