Element: show event
===================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `show` event is fired when a [`contextmenu`](contextmenu_event) event was fired on/bubbled to an element that has a [`contextmenu` attribute](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contextmenu).

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><span class="page-not-created"><code>onshow</code></span></td></tr></tbody></table>

Examples
--------

    <div contextmenu="test"></div>
    <menu type="context" id="test">
      <menuitem label="alert" onclick="alert('the alert label has been clicked')" />
    </menu>

    <script>
      document.getElementById("test").addEventListener("show", function(e){
        alert("the context menu will be displayed");
      }, false);
    </script>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/webappapis.html#handler-onshow">HTML5<br />
<span class="small">The definition of 'show event' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td></tr></tbody></table>

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

`show_event`

No

No

Yes

?

?

?

No

No

Yes

?

?

No

See also
--------

-   <span class="page-not-created">`onshow`</span>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/show_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/show_event</a>
