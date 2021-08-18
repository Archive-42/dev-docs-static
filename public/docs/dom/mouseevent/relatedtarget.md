MouseEvent.relatedTarget
========================

The `MouseEvent.relatedTarget` read-only property is the secondary target for the mouse event, if there is one. That is:

<table><thead><tr class="header"><th>Event name</th><th><code>target</code></th><th><code>relatedTarget</code></th></tr></thead><tbody><tr class="odd"><td><code>mouseenter</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td></tr><tr class="even"><td><code>mouseleave</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td></tr><tr class="odd"><td><code>mouseout</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td></tr><tr class="even"><td><code>mouseover</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td></tr><tr class="odd"><td><code>dragenter</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td></tr><tr class="even"><td><code>dragleave</code></td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device exited from</td><td>The <a href="../eventtarget"><code>EventTarget</code></a> the pointing device entered to</td></tr></tbody></table>

For events with no secondary target, `relatedTarget` returns `null`.

[`FocusEvent.relatedTarget`](../focusevent/relatedtarget) is a similar property for focus events.

Syntax
------

    var target = instanceOfMouseEvent.relatedTarget

### Return value

An [`EventTarget`](../eventtarget) object or `null`.

Example
-------

Try moving your mouse cursor into and out of the red and blue boxes.

### HTML

    <body id="body">
      <div id="outer">
        <div id="red"></div>
        <div id="blue"></div>
      </div>
      <p id="log"></p>
    </body>

### CSS

    #outer {
      width: 250px;
      height: 125px;
      display: flex;
    }

    #red {
      flex-grow: 1;
      background: red;
    }

    #blue {
      flex-grow: 1;
      background: blue;
    }

    #log {
      max-height: 120px;
      overflow-y: scroll;
    }

### JavaScript

    const mouseoutLog = document.getElementById('log'),
          red = document.getElementById('red'),
          blue = document.getElementById('blue');

    red.addEventListener('mouseover', overListener);
    red.addEventListener('mouseout', outListener);
    blue.addEventListener('mouseover', overListener);
    blue.addEventListener('mouseout', outListener);

    function outListener(event) {
      let related = event.relatedTarget ? event.relatedTarget.id : "unknown";

      mouseoutLog.innerText = `\nfrom ${event.target.id} into ${related}${mouseoutLog.innerText}`;
    }

    function overListener(event) {
      let related = event.relatedTarget ? event.relatedTarget.id : "unknown";

      log.innerText = `\ninto ${event.target.id} from ${related}${mouseoutLog.innerText}`;
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#dom-mouseevent-relatedtarget">UI Events<br />
<span class="small">The definition of 'MouseEvent.relatedTarget' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#widl-MouseEvent-relatedTarget">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'MouseEvent.relatedTarget' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html">Document Object Model (DOM) Level 2 Events Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-MouseEvent">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'MouseEvent.altkey' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`relatedTarget`

Yes

12

48

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   [`MouseEvent`](../mouseevent)
-   [Comparison of Event Targets](../event/comparison_of_event_targets)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/relatedTarget" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MouseEvent/relatedTarget</a>
