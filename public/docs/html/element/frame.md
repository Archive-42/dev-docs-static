&lt;frame&gt;
=============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`<frame>` is an HTML element which defines a particular area in which another HTML document can be displayed. A frame should be used within a [`<frameset>`](frameset).

Using the `<frame>` element is not encouraged because of certain disadvantages such as performance problems and lack of accessibility for users with screen readers. Instead of the `<frame>` element, [`<iframe>`](iframe) may be preferred.

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes).

`src`  
This attribute specifies the document that will be displayed by the frame.

`name`  
This attribute is used for labeling frames. Without labeling, every link will open in the frame that it’s in – the closest parent frame. See the [`target`](a#attr-target) attribute for more information.

`noresize`  
This attribute prevents resizing of frames by users.

`scrolling`  
This attribute defines the existence of a scrollbar. If this attribute is not used, the browser adds a scrollbar when necessary. There are two choices: "yes" for forcing a scrollbar even when it is not necessary and "no" for forcing no scrollbar even when it *is* necessary.

`marginheight`  
This attribute defines the height of the margin between frames.

`marginwidth`  
This attribute defines the width of the margin between frames.

`frameborder`  
This attribute allows you to specify a frame’s border.

Example
-------

    <frameset cols="50%,50%">
      <frame src="https://developer.mozilla.org/en/HTML/Element/iframe" />
      <frame src="https://developer.mozilla.org/en/HTML/Element/frame" />
    </frameset>

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

`frame`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`frameborder`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`marginheight`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`marginwidth`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`name`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`noresize`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`scrolling`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

`src`

Yes

12

Yes

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

-   [`<frameset>`](frameset)
-   [`<iframe>`](iframe)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/frame</a>
