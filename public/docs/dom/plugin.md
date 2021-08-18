Plugin
======

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `Plugin` interface provides information about a browser plugin.

**Note**: Own properties of `Plugin` objects are no longer enumerable in the latest browser versions.

Properties
----------

 <span class="page-not-created">`Plugin.description`</span> <span class="badge inline readonly">Read only </span>   
A human readable description of the plugin.

 <span class="page-not-created">`Plugin.filename`</span> <span class="badge inline readonly">Read only </span>   
The filename of the plugin file.

 <span class="page-not-created">`Plugin.name`</span> <span class="badge inline readonly">Read only </span>   
The name of the plugin.

 <span class="page-not-created">`Plugin.version`</span> <span class="badge inline readonly">Read only </span>   
The plugin's version number string.

Methods
-------

<span class="page-not-created">`Plugin.item`</span>  
Returns the MIME type of a supported content type, given the index number into a list of supported types.

<span class="page-not-created">`Plugin.namedItem`</span>  
Returns the MIME type of a supported item.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-plugin">HTML Living Standard<br />
<span class="small">The definition of 'Plugin' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`Plugin`

1

12

1

4

15

1

1

18

4

14

1

1.0

`description`

Yes

12

1

4

Yes

10

Yes

Yes

4

Yes

10

Yes

`filename`

Yes

12

1

4

Yes

10

Yes

Yes

4

Yes

10

Yes

`item`

1

Starting with version 59, method parameters are required instead of optional.

12

1

4

15

4

1

Starting with version 59, method parameters are required instead of optional.

18

Starting with version 59, method parameters are required instead of optional.

4

14

3.2

1.0

Starting with Samsung Internet 7.0, method parameters are required instead of optional.

`length`

1

12

1

11

15

1

1

18

4

14

1

1.0

`name`

Yes

12

1

4

Yes

10

Yes

Yes

4

Yes

10

Yes

`namedItem`

1

Starting with version 59, method parameters are required instead of optional.

12

1

4

15

4

1

Starting with version 59, method parameters are required instead of optional.

18

Starting with version 59, method parameters are required instead of optional.

4

14

3.2

1.0

Starting with Samsung Internet 7.0, method parameters are required instead of optional.

`version`

No

12-79

3.6

4

No

No

No

No

4

No

No

No

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Plugin" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Plugin</a>
