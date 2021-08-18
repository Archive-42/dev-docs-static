Pointer events
==============

Much of today's web content assumes the user's pointing device will be a mouse. However, since many devices support other types of pointing input devices, such as pen/stylus and touch surfaces, extensions to the existing pointing device event models are needed. *[Pointer events](#term_pointer_event)* address that need.

**Note:** Pointer events are *not available* in [Web Workers](web_workers_api).

Pointer events are DOM events that are fired for a pointing device. They are designed to create a single DOM event model to handle pointing input devices such as a mouse, pen/stylus or touch (such as one or more fingers).

The *[pointer](#term_pointer)* is a hardware-agnostic device that can target a specific set of screen coordinates. Having a single event model for pointers can simplify creating Web sites and applications and provide a good user experience regardless of the user's hardware. However, for scenarios when device-specific handling is desired, pointer events defines a [`pointerType property`](pointerevent/pointertype) to inspect the device type which produced the event.

The events needed to handle generic pointer input are analogous to [`mouse events`](mouseevent) (`mousedown`/`pointerdown`, `mousemove`/`pointermove`, etc.). Consequently, pointer event types are intentionally similar to mouse event types.

Additionally, a pointer event contains the usual properties present in mouse events (client coordinates, target element, button states, etc.) in addition to new properties for other forms of input: pressure, contact geometry, tilt, etc. In fact, the [`PointerEvent`](pointerevent) interface inherits all of the [`MouseEvent`](mouseevent) properties, thus facilitating the migration of content from mouse events to pointer events.

Terminology
-----------

active buttons state  
The condition when a *[pointer](#term_pointer)* has a non-zero value for the `buttons` property. For example, in the case of a pen, when the pen has physical contact with the digitizer, or at least one button is depressed while hovering.

active pointer  
Any *[pointer](#term_pointer)* input device that can produce events. A pointer is considered active if it can still produce further events. For example, a pen that is a down state is considered active because it can produce additional events when the pen is lifted or moved.

digitizer  
A sensing device with a surface that can detect contact. Most commonly, the sensing device is a touch-enabled screen that can sense input from an input device such as a pen, stylus, or finger. Some sensing devices can detect the close proximity of the input device, and the state is expressed as a hover following the mouse.

hit test  
The process the browser uses to determine a target element for a pointer event. Typically, this is determined by considering the pointer's location and also the visual layout of elements in a document on screen media.

pointer  
A hardware-agnostic representation of input devices that can target a specific coordinate (or set of coordinates) on a screen. Examples of *pointer* input devices are mouse, pen/stylus, and touch contacts.

pointer capture  
Pointer capture allows the events for a pointer to be retargeted to a particular element other than the normal hit test result of the pointer's location.

pointer event  
A DOM [`event`](pointerevent) fired for a *[pointer](#term_pointer)*.

Interfaces
----------

The primary interface is the [`PointerEvent`](pointerevent) interface which has a [`constructor`](pointerevent/pointerevent) plus several event types and associated global event handlers.

The standard also includes some extensions to the [`Element`](element) and [`Navigator`](navigator) interfaces.

The following sub-sections contain short descriptions of each interface and property.

### PointerEvent interface

The [`PointerEvent`](pointerevent) interface extends the [`MouseEvent`](mouseevent) interface and has the following properties. (All of the following properties are <span class="badge inline readonly">Read only </span>.)

[`pointerId`](pointerevent/pointerid)  
A unique identifier for the pointer causing the event.

[`width`](pointerevent/width)  
The width (magnitude on the X axis), in CSS pixels, of the contact geometry of the pointer.

[`height`](pointerevent/height)  
the height (magnitude on the Y axis), in CSS pixels, of the contact geometry of the pointer.

[`pressure`](pointerevent/pressure)  
the normalized pressure of the pointer input in the range of `0` to `1`, where `0` and `1` represent the minimum and maximum pressure the hardware is capable of detecting, respectively.

[`tangentialPressure`](pointerevent/tangentialpressure)  
The normalized tangential pressure of the pointer input (also known as barrel pressure or cylinder stress) in the range `-1` to `1`, where `0` is the neutral position of the control.

[`tiltX`](pointerevent/tiltx)  
The plane angle (in degrees, in the range of `-90` to `90`) between the Y–Z plane and the plane containing both the pointer (e.g. pen stylus) axis and the Y axis.

[`tiltY`](pointerevent/tilty)  
the plane angle (in degrees, in the range of `-90` to `90`) between the X–Z plane and the plane containing both the pointer (e.g. pen stylus) axis and the X axis.

[`twist`](pointerevent/twist)  
The clockwise rotation of the pointer (e.g. pen stylus) around its major axis in degrees, with a value in the range `0` to `359`.

[`pointerType`](pointerevent/pointertype)  
Indicates the device type that caused the event (mouse, pen, touch, etc.)

[`isPrimary`](pointerevent/isprimary)  
Indicates if the pointer represents the primary pointer of this pointer type.

### Event types and Global Event Handlers

Pointer events have ten event types, seven of which have similar semantics to their mouse event counterparts (`down`, `up`, `move`, `over`, `out`, `enter`, and `leave`).

Below is a short description of each event type and its associated [`Global Event Handler`](globaleventhandlers).

<table><thead><tr class="header"><th>Event</th><th>On Event Handler</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>pointerover</code></td><td><a href="globaleventhandlers/onpointerover"><code>onpointerover</code></a></td><td>Fired when a pointer is moved into an element's <a href="#term_hit_test">hit test</a> boundaries.</td></tr><tr class="even"><td><code>pointerenter</code></td><td><a href="globaleventhandlers/onpointerenter"><code>onpointerenter</code></a></td><td>Fired when a pointer is moved into the <a href="#term_hit_test">hit test</a> boundaries of an element or one of its descendants, including as a result of a pointerdown event from a device that does not support hover (see <code>pointerdown</code>).</td></tr><tr class="odd"><td><code>pointerdown</code></td><td><a href="globaleventhandlers/onpointerdown"><code>onpointerdown</code></a></td><td>Fired when a pointer becomes <em>active buttons state</em>.</td></tr><tr class="even"><td><code>pointermove</code></td><td><a href="globaleventhandlers/onpointermove"><code>onpointermove</code></a></td><td>Fired when a pointer changes coordinates. This event is also used if the change in pointer state can not be reported by other events.</td></tr><tr class="odd"><td><code>pointerup</code></td><td><a href="globaleventhandlers/onpointerup"><code>onpointerup</code></a></td><td>Fired when a pointer is no longer <em>active buttons state</em>.</td></tr><tr class="even"><td><code>pointercancel</code></td><td><a href="globaleventhandlers/onpointercancel"><code>onpointercancel</code></a></td><td>A browser fires this event if it concludes the pointer will no longer be able to generate events (for example the related device is deactivated).</td></tr><tr class="odd"><td><code>pointerout</code></td><td><a href="globaleventhandlers/onpointerout"><code>onpointerout</code></a></td><td>Fired for several reasons including: pointer is moved out of the <a href="#term_hit_test">hit test</a> boundaries of an element; firing the pointerup event for a device that does not support hover (see pointerup); after firing the <code>pointercancel</code> event (see <code>pointercancel</code>); when a pen stylus leaves the hover range detectable by the digitizer.</td></tr><tr class="even"><td><code>pointerleave</code></td><td><a href="globaleventhandlers/onpointerleave"><code>onpointerleave</code></a></td><td>Fired when a pointer is moved out of the <a href="#term_hit_test">hit test</a> boundaries of an element. For pen devices, this event is fired when the stylus leaves the hover range detectable by the digitizer.</td></tr><tr class="odd"><td><code>gotpointercapture</code></td><td><a href="globaleventhandlers/ongotpointercapture"><code>ongotpointercapture</code></a></td><td>Fired when an element receives pointer capture.</td></tr><tr class="even"><td><code>lostpointercapture</code></td><td><a href="globaleventhandlers/onlostpointercapture"><code>onlostpointercapture</code></a></td><td>Fired after pointer capture is released for a pointer.</td></tr></tbody></table>

### Element extensions

There are three extensions to the [`Element`](element) interface:

[`setPointerCapture()`](element/setpointercapture)  
Designates a specific element as the *capture target* of future pointer events.

[`releasePointerCapture()`](element/releasepointercapture)  
This method releases (stops) *pointer capture* that was previously set for a specific pointer event.

### Navigator extension

The [`Navigator.maxTouchPoints`](navigator/maxtouchpoints) property is used to determine the maximum number of simultaneous touch points that are supported at any single point in time.

Examples
--------

This section contains examples of basic usage of using the pointer events interfaces.

### Registering event handlers

This example registers a handler for every event type for the given element.

    <html>
      <script>
        function over_handler(event) { }
        function enter_handler(event) { }
        function down_handler(event) { }
        function move_handler(event) { }
        function up_handler(event) { }
        function cancel_handler(event) { }
        function out_handler(event) { }
        function leave_handler(event) { }
        function gotcapture_handler(event) { }
        function lostcapture_handler(event) { }

        function init() {
          var el=document.getElementById("target");
          // Register pointer event handlers
          el.onpointerover = over_handler;
          el.onpointerenter = enter_handler;
          el.onpointerdown = down_handler;
          el.onpointermove = move_handler;
          el.onpointerup = up_handler;
          el.onpointercancel = cancel_handler;
          el.onpointerout = out_handler;
          el.onpointerleave = leave_handler;
          el.gotpointercapture = gotcapture_handler;
          el.lostpointercapture = lostcapture_handler;
        }
      </script>
      <body onload="init();">
        <div id="target"> Touch me ... </div>
      </body>
    </html>

### Event properties

This example illustrates accessing all of a touch event's properties.

    <html>
      <script>
        var id = -1;

        function process_id(event) {
          // Process this event based on the event's identifier
        }
        function process_mouse(event) {
          // Process the mouse pointer event
        }
        function process_pen(event) {
          // Process the pen pointer event
        }
        function process_touch(event) {
          // Process the touch pointer event
        }
        function process_tilt(tiltX, tiltY) {
          // Tilt data handler
        }
        function process_pressure(pressure) {
          // Pressure handler
        }
        function process_non_primary(event) {
          // Non primary handler
        }

        function down_handler(ev) {
          // Calculate the touch point's contact area
          var area = ev.width * ev.height;

          // Compare cached id with this event's id and process accordingly
          if (id == ev.identifier) process_id(ev);

          // Call the appropriate pointer type handler
          switch (ev.pointerType) {
            case "mouse":
              process_mouse(ev);
              break;
            case "pen":
              process_pen(ev);
              break;
            case "touch":
              process_touch(ev);
              break;
            default:
              console.log("pointerType " + ev.pointerType + " is Not supported");
          }

          // Call the tilt handler
          if (ev.tiltX != 0 && ev.tiltY != 0) process_tilt(ev.tiltX, ev.tiltY);

          // Call the pressure handler
          process_pressure(ev.pressure);

          // If this event is not primary, call the non primary handler
          if (!ev.isPrimary) process_non_primary(ev);
        }

        function init() {
          var el=document.getElementById("target");
          // Register pointerdown handler
          el.onpointerdown = down_handler;
        }
      </script>
      <body onload="init();">
        <div id="target"> Touch me ... </div>
      </body>
    </html>

Determining the Primary Pointer
-------------------------------

In some scenarios there may be multiple pointers (for example a device with both a touchscreen and a mouse) or a pointer supports multiple contact points (for example a touchscreen that supports multiple finger touches). The application can use the [`isPrimary`](pointerevent/isprimary) property to identify a master pointer among the set of *active pointers* for each pointer type. If an application only wants to support a primary pointer, it can ignore all pointer events that are not primary.

For mouse there is only one pointer, so it will always be the primary pointer. For touch input, a pointer is considered primary if the user touched the screen when there were no other active touches. For pen and stylus input, a pointer is considered primary if the user's pen initially contacted the screen when there were no other active pens contacting the screen.

Determining button states
-------------------------

Some pointer devices, such as mouse and pen, support multiple buttons and the button presses can be *chorded* i.e. depressing an additional button while another button on the pointer device is already depressed.

To determine the state of button presses, pointer events uses the [`button`](mouseevent/button) and [`buttons`](mouseevent/buttons) properties of the [`MouseEvent`](mouseevent) interface (that [`PointerEvent`](pointerevent) inherits from).

The following table provides the values of `button` and `buttons` for the various device button states.

<table><thead><tr class="header"><th>Device Button State</th><th>button</th><th>buttons</th></tr></thead><tbody><tr class="odd"><td>Neither buttons nor touch/pen contact changed since last event</td><td><code>-1</code></td><td>—</td></tr><tr class="even"><td>Mouse move with no buttons pressed, Pen moved while hovering with no buttons pressed</td><td>—</td><td><code>0</code></td></tr><tr class="odd"><td>Left Mouse, Touch Contact, Pen contact</td><td><code>0</code></td><td><code>1</code></td></tr><tr class="even"><td>Middle Mouse</td><td><code>1</code></td><td><code>4</code></td></tr><tr class="odd"><td>Right Mouse, Pen barrel button</td><td><code>2</code></td><td><code>2</code></td></tr><tr class="even"><td>X1 (back) Mouse</td><td><code>3</code></td><td><code>8</code></td></tr><tr class="odd"><td>X2 (forward) Mouse</td><td><code>4</code></td><td><code>16</code></td></tr><tr class="even"><td>Pen eraser button</td><td><code>5</code></td><td><code>32</code></td></tr></tbody></table>

**Notice:** The `button` property indicates a change in the state of the button. However, as in the case of touch, when multiple events occur with one event, all of them have the same value.

Pointer capture
---------------

Pointer capture allows events for a particular [`pointer event`](pointerevent) to be re-targeted to a particular element instead of the normal [hit test](#term_hit_test) at a pointer's location. This can be used to ensure that an element continues to receive pointer events even if the pointer device's contact moves off the element (for example by scrolling).

The following example shows pointer capture being set on an element.

    <html>
    <script>
      function downHandler(ev) {
        let el = document.getElementById("target");
        // Element 'target' will receive/capture further events
        el.setPointerCapture(ev.pointerId);
      }

      function init() {
        let el = document.getElementById("target");
        el.onpointerdown = downHandler;
      }
    </script>
    <body onload="init();">
      <div id="target"> Touch me ... </div>
    </body>
    </html>

The following example shows a pointer capture being released (when a `pointercancel` event occurs. The browser does this automatically when a `pointerup` or `pointercancel` event occurs.

    <html>
      <script>
        function downHandler(ev) {
          let el = document.getElementById("target");
          // Element "target" will receive/capture further events
          el.setPointerCapture(ev.pointerId);
        }

        function cancelHandler(ev) {
          let el = document.getElementById("target");
          // Release the pointer capture
          el.releasePointerCapture(ev.pointerId);
        }

        function init() {
          let el = document.getElementById("target");
          // Register pointerdown and pointercancel handlers
          el.onpointerdown = downHandler;
          el.onpointercancel = cancelHandler;
        }
      </script>
      <body onload="init();">
        <div id="target"> Touch me ... </div>
      </body>
    </html>

touch-action CSS property
-------------------------

The [`touch-action`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action) CSS property is used to specify whether or not the browser should apply its default (*native*) touch behavior (such as zooming or panning) to a region. This property may be applied to all elements except: non-replaced inline elements, table rows, row groups, table columns, and column groups.

A value of `auto` means the browser is free to apply its default touch behavior (to the specified region) and the value of `none` disables the browser's default touch behavior for the region. The values `pan-x` and `pan-y`, mean that touches that begin on the specified region are only for horizontal and vertical scrolling, respectively. The value `manipulation` means the browser may consider touches that begin on the element are only for scrolling and zooming.

In the following example, the browser's default touch behavior is disabled for the `div` element.

    <html>
      <body>
        <div style="touch-action:none;">Can't touch this ... </div>
      </body>
    </html>

In the following example, default touch behavior is disabled for some `button` elements.

    button#tiny {
      touch-action: none;
    }

In the following example, when the `target` element is touched, it will only pan in the horizontal direction.

    #target {
      touch-action: pan-x;
    }

Compatibility with mouse events
-------------------------------

Although the pointer event interfaces enable applications to create enhanced user experiences on pointer enabled devices, the reality is the vast majority of today's web content is designed to only work with mouse input. Consequently, even if a browser supports pointer events, the browser must still process mouse events so content that assumes mouse-only input will work as is without direct modification. Ideally, a pointer enabled application does not need to explicitly handle mouse input. However, because the browser must process mouse events, there may be some compatibility issues that need to be handled. This section contains information about pointer event and mouse event interaction and the ramifications for application developers.

The browser *may map generic pointer input to mouse events for compatibility with mouse-based content*. This mapping of events is called *compatibility mouse events*. Authors can prevent the production of certain compatibility mouse events by canceling the pointerdown event but note that:

-   Mouse events can only be prevented when the pointer is down.
-   Hovering pointers (e.g. a mouse with no buttons pressed) cannot have their mouse events prevented.
-   The `mouseover`, `mouseout`, `mouseenter`, and `mouseleave` events are never prevented (even if the pointer is down).

Best practices
--------------

Here are some *best practices* to consider when using pointer events:

-   Minimize the amount of work performed in event handlers.
-   Add the event handlers to a specific target element (rather than the entire document or nodes higher up in the document tree).
-   The target element (node) should be large enough to accommodate the largest contact surface area (typically a finger touch). If the target area is too small, touching it could result in firing other events for adjacent elements.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/pointerevents/">Pointer Events – Level 3</a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added new APIs for <code>getCoalescedEvent</code> and <code>getPredictedEvents</code>, new <code>pointerrawupdate</code> event, additional <code>touch-action</code> property values <code>pan-left</code>, <code>pan-right</code>, <code>pan-up</code>, <code>pan-down</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents2/">Pointer Events – Level 2</a></td><td><span class="spec-rec">Recommendation</span></td><td>Adds <code>hasPointerCapture</code> method and clarifies more edge cases and dynamic scenarios.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents1/">Pointer Events</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Pointer_events`

55

12

59

41

11

10

See [MSDN Pointer events updates](https://msdn.microsoft.com/library/dn304886).

42

13

55

55

79

41

42

13

6.0

`PointerEvent`

55

12

59

41

11

10

See [MSDN Pointer events updates](https://msdn.microsoft.com/library/dn304886).

42

13

55

55

79

41

42

13

6.0

`getCoalescedEvents`

58

79

59

No

45

No

58

58

79

59

43

No

7.0

`height`

55

12

59

41

11

10

Returns values in screen pixels instead of CSS document pixels.

42

13

55

55

79

41

42

13

6.0

`isPrimary`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`pointerId`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`pointerType`

55

12

59

41

11

10

Returns an integer enumeration instead of a string.

42

13

55

55

79

41

42

13

6.0

`pressure`

55

12

59

41

11

10

Returns 0 instead of 0.5 on hardware that doesn't support pressure.

42

13

55

55

79

41

42

13

6.0

`tangentialPressure`

58

79

59

54

No

45

13

58

58

79

54

43

13

7.0

`tiltX`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`tiltY`

55

12

59

41

10

42

13

55

55

79

41

42

13

6.0

`twist`

58

18

59

54

No

45

13

58

58

79

54

43

13

7.0

`width`

55

12

59

41

11

10

Returns values in screen pixels instead of CSS document pixels.

42

13

55

55

79

41

42

13

6.0

Some new values have been defined for the [`css touch-action`](https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action) property as part of the [Pointer Events – Level 3](https://w3c.github.io/pointerevents/) specification but currently those new values have limited implementation support.

Demos and examples
------------------

-   [Touch/pointer tests and demos (by Patrick H. Lauke)](https://patrickhlauke.github.io/touch/)

Community
---------

-   [Pointer Events Working Group](https://github.com/w3c/pointerevents)
-   [Mail list](https://lists.w3.org/Archives/Public/public-pointer-events/)
-   [W3C \#pointerevents IRC channel](irc://irc.w3.org:6667/)

Related topics and resources
----------------------------

-   [Touch Events Standard](https://www.w3.org/TR/touch-events/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events</a>
