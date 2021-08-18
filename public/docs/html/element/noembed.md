&lt;noembed&gt;: The Embed Fallback element
===========================================

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<noembed>` element is an obsolete, non-standard way to provide alternative, or "fallback", content for browsers that do not support the [`<embed>`](embed) element or do not support the type of [embedded content](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content) an author wishes to use. This element was deprecated in HTML 4.01 and above in favor of placing fallback content between the opening and closing tags of an [`<object>`](object) element.

While this element currently still works in many browsers, it is obsolete and should not be used. Use [`<object>`](object) instead, with fallback content between the opening and closing tags of the element.

Examples
--------

The message inside `<noembed>` tag will appear only when your browser does not support `<embed>` tag.

### Show an alternative content

    <embed type="vide/webm" src="/media/examples/flower.mp4" width="200" height="200">
      <noembed>
        <h1>Alternative content</h1>
      </noembed>
    </embed>

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

`noembed`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noembed" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noembed</a>
