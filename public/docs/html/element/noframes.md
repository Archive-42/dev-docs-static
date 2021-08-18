&lt;noframes&gt;: The Frame Fallback element
============================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The obsolete HTML **No Frames** or **frame fallback** element, `<noframes>`, provides content to be presented in browsers that don't support (or have disabled support for) the [`<frame>`](frame) element. Although most commonly-used browsers support frames, there are exceptions, including certain special-use browsers including some mobile browsers, as well as text-mode browsers.

A `<noframes>` element can contain any HTML elements that are allowed within the body of an HTML document, with the exception of the [`<frameset>`](frameset) and [`<frame>`](frame) elements, since using frames when they aren't supported doesn't make sense.

`<noframes>` can be used to present a message explaining that the user's browser doesn't support frames, but ideally should be used to present an alternate form of the site that doesn't use frames but still offers the same or similar functionality.

In HTML 5 and later, `<noframes>` is obsolete and shouldn't be used, since the [`<frame>`](frame) and [`<frameset>`](frameset) elements are also obsolete. When frames are needed at all, they should be presented using the [`<iframe>`](iframe) element.

Attributes
----------

Like all other HTML elements, this element supports the [global attributes](../global_attributes). It has no other attributes available.

Example
-------

In this example, we see a frameset with two frames. In addition, `<noframes>` is used to present an explanatory message if the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent) doesn't support frames.

    <frameset cols="50%,50%">
      <frame src="https://developer.mozilla.org/en/HTML/Element/frameset" />
      <frame src="https://developer.mozilla.org/en/HTML/Element/frame" />
      <noframes><p>It seems your browser does not support frames or is
      configured to not allow them.</p></noframes>
    </frameset>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/#noframes">HTML5<br />
<span class="small">The definition of 'noframes' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/frames.html#edef-NOFRAMES">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;noframes&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr></tbody></table>

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

`noframes`

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
-   [`<frame>`](frame)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noframes" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noframes</a>
