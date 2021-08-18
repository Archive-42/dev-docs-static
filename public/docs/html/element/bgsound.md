&lt;bgsound&gt;: The Background Sound element
=============================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The Internet Explorer only **HTML Background Sound element** (`<bgsound>`) sets up a sound file to play in the background while the page is used; use [`<audio>`](audio) instead.

**Do not use this!** In order to embed audio in a Web page, you should be using the [`<audio>`](audio) element.

Attributes
----------

`balance`  
This attribute defines a number between -10,000 and +10,000 that determines how the volume will be divided between the speakers.

`loop`  
This attribute indicates the number of times a sound is to be played and either has a numeric value or the keyword infinite.

`src`  
This attribute specifies the URL of the sound file to be played, which must be one of the following types: .wav, .au, or .mid.

`volume`  
This attribute defines a number between -10,000 and 0 that determines the loudness of a page's background sound.

Example
-------

    <bgsound src="sound1.mid">

    <bgsound src="sound2.au" loop="infinite">

Usage notes
-----------

Historically, the [`<embed>`](embed) element could be used with audio player plug-ins to play audio in the background in most browsers. However, even this is no longer appropriate, and you should use `<audio>` instead, since it's more capable, more compatible, and doesn't require plug-ins.

You can write `<bgsound>` as a self-closing tag (`<bgsound />`); however, since this element is non-standard, doing so will still not validate.

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

`bgsound`

No

No

No

Up to Firefox 22, even if not supporting this element, Firefox was associating it with `HTMLSpanElement`. This was fixed then and now the associated element is an `HTMLUnknownElement` as required by the specification.

Yes

No

No

No

No

No

Up to Firefox 22, even if not supporting this element, Firefox was associating it with `HTMLSpanElement`. This was fixed then and now the associated element is an `HTMLUnknownElement` as required by the specification.

No

No

No

See also
--------

-   The [`<audio>`](audio), which is the standard element to embed audio in a document.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bgsound" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/bgsound</a>
