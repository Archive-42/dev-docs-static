Element: mouseenter event
=========================

The `mouseenter` event is fired at an [`Element`](../element) when a pointing device (usually a mouse) is initially moved so that its hotspot is within the element at which the event was fired.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onmouseenter"><code>onmouseenter</code></a></td></tr></tbody></table>

Usage notes
-----------

Though similar to [`mouseover`](mouseover_event), `mouseenter` differs in that it doesn't [bubble](../event/bubbles) and it isn't sent to any descendants when the pointer is moved from one of its descendants' physical space to its own physical space.

<img src="data:image/png;base64,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" class="default internal" width="451" height="198" /> One `mouseenter` event is sent to each element of the hierarchy when entering them. Here 4 events are sent to the four elements of the hierarchy when the pointer reaches the text. <img src="data:image/png;base64,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" class="default internal" width="454" height="207" /> A single `mouseover` event is sent to the deepest element of the DOM tree, then it bubbles up the hierarchy until it is canceled by a handler or reaches the root.

With deep hierarchies, the number of `mouseenter` events sent can be quite huge and cause significant performance problems. In such cases, it is better to listen for `mouseover` events.

Combined with the corresponding `mouseleave` (which is fired at the element when the mouse exits its content area), the `mouseenter` event acts in a very similar way to the CSS [`:hover`](https://developer.mozilla.org/en-US/docs/Web/CSS/:hover) pseudo-class.

Examples
--------

The [`mouseover`](mouseover_event#example) documentation has an example illustrating the difference between `mouseover` and `mouseenter`.

### mouseenter

The following trivial example uses the `mouseenter` event to change the border on the `div` when the mouse enters the space alloted to it. It then adds an item to the list with the number of the `mouseenter` or `mouseleave` event.

#### HTML

    <div id='mouseTarget'>
     <ul id="unorderedList">
      <li>No events yet!</li>
     </ul>
    </div>

#### CSS

Styling the `div` to make it more visible.

    #mouseTarget {
      box-sizing: border-box;
      width:15rem;
      border:1px solid #333;
    }

#### JavaScript

    var enterEventCount = 0;
    var leaveEventCount = 0;
    const mouseTarget = document.getElementById('mouseTarget');
    const unorderedList = document.getElementById('unorderedList');

    mouseTarget.addEventListener('mouseenter', e => {
      mouseTarget.style.border = '5px dotted orange';
      enterEventCount++;
      addListItem('This is mouseenter event ' + enterEventCount + '.');
    });

    mouseTarget.addEventListener('mouseleave', e => {
      mouseTarget.style.border = '1px solid #333';
      leaveEventCount++;
      addListItem('This is mouseleave event ' + leaveEventCount + '.');
    });

    function addListItem(text) {
      // Create a new text node using the supplied text
      var newTextNode = document.createTextNode(text);

      // Create a new li element
      var newListItem = document.createElement("li");

      // Add the text node to the li element
      newListItem.appendChild(newTextNode);

      // Add the newly created list item to list
      unorderedList.appendChild(newListItem);
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mouseenter">UI Events<br />
<span class="small">The definition of 'mouseenter' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mouseenter">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mouseenter' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`mouseenter_event`

30

12

10

5.5

17

6.1

≤37

30

10

18

6.1

2.0

See also
--------

-   [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
-   [`mousedown`](mousedown_event)
-   [`mouseup`](mouseup_event)
-   [`mousemove`](mousemove_event)
-   [`click`](click_event)
-   [`dblclick`](dblclick_event)
-   [`mouseover`](mouseover_event)
-   [`mouseout`](mouseout_event)
-   [`mouseenter`](mouseenter_event)
-   [`mouseleave`](mouseleave_event)
-   [`contextmenu`](contextmenu_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseenter_event</a>
