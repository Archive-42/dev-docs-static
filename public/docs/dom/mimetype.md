MimeType
========

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `MimeType` interface provides contains information about a MIME type associated with a particular plugin. [`NavigatorPlugins.mimeTypes`](navigatorplugins/mimetypes) returns an array of this object.

Properties
----------

<span class="page-not-created">`MimeType.type`</span>  
Returns the MIME type of the associated plugin.

<span class="page-not-created">`MimeType.description`</span>  
Returns a description of the associated plugin or an empty string if there is none.

<span class="page-not-created">`MimeType.suffixes`</span>  
A string containing valid file extensions for the data displayed by the plugin, or an empty string if an extension is not valid for the particular module. For example, a browser's content decryption module may appear in the plugin list but support more file extensions than can be anticipated. It might therefore return an empty string.

<span class="page-not-created">`MimeType.enabledPlugin`</span>  
Returns an instance of [`Plugin`](plugin) containing information about the plugin itself.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#mimetype">HTML Living Standard<br />
<span class="small">The definition of 'MimeType' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`MimeType`

1

12

1

11

≤12.1

1

1

18

No

≤12.1

1-8

1.0

`description`

1

12

1

11

≤12.1

1

1

18

No

≤12.1

1-8

1.0

`enabledPlugin`

1

12

1

11

≤12.1

1

1

18

No

≤12.1

1-8

1.0

`suffixes`

1

12

1

11

≤12.1

1

1

18

No

≤12.1

1-8

1.0

`type`

1

12

1

11

≤12.1

1

1

18

No

≤12.1

1-8

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/MimeType" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/MimeType</a>
