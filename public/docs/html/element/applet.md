&lt;applet&gt;: The Embed Java Applet element
=============================================

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `<applet>` element was removed in [Gecko 56](https://bugzilla.mozilla.org/show_bug.cgi?id=1279218) and [Chrome 47](https://bugs.chromium.org/p/chromium/issues/detail?id=470301).

Removal is being considered in [WebKit](https://bugs.webkit.org/show_bug.cgi?id=157926) and [Edge](https://developer.microsoft.com/en-us/microsoft-edge/platform/issues/11946645/).

The obsolete **HTML Applet Element** (`<applet>`) embeds a Java applet into the document; this element has been deprecated in favor of [`<object>`](object).

Use of Java applets on the Web is deprecated; most browsers no longer support use of plug-ins, including the Java plug-in.

<table><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#phrasing_content">phrasing content</a>, <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>, interactive content, palpable content.</td></tr><tr class="even"><td>Permitted content</td><td>Zero or more <a href="param"><code>&lt;param&gt;</code></a> elements, then <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#transparent_content_model">transparent</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>None, both the starting and ending tag are mandatory.</td></tr><tr class="even"><td>Permitted parents</td><td>Any element that accepts <a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#embedded_content">embedded content</a>.</td></tr><tr class="odd"><td>DOM interface</td><td><span class="page-not-created"><code>HTMLAppletElement</code></span></td></tr></tbody></table>

Attributes
----------

`align`  
This attribute is used to position the applet on the page relative to content that might flow around it. The HTML 4.01 specification defines values of `bottom`, `left`, `middle`, `right`, and `top`, whereas Microsoft and Netscape also might support `absbottom`, `absmiddle`, `baseline`, `center`, and `texttop`.

`alt`  
This attribute causes a descriptive text alternate to be displayed on browsers that do not support Java. Page designers should also remember that content enclosed within the `<applet>` element may also be rendered as alternative text.

`archive`  
This attribute refers to an archived or compressed version of the applet and its associated class files, which might help reduce download time.

`code`  
This attribute specifies the URL of the applet's class file to be loaded and executed. Applet filenames are identified by a .class filename extension. The URL specified by code might be relative to the `codebase` attribute.

`codebase`  
This attribute gives the absolute or relative URL of the directory where applets' .class files referenced by the code attribute are stored.

`datafld`  
This attribute, supported by Internet Explorer 4 and higher, specifies the column name from the data source object that supplies the bound data. This attribute might be used to specify the various [`<param>`](param) elements passed to the Java applet.

`datasrc`  
Like `datafld`, this attribute is used for data binding under Internet Explorer 4. It indicates the id of the data source object that supplies the data that is bound to the [`<param>`](param) elements associated with the applet.

`height`  
This attribute specifies the height, in pixels, that the applet needs.

`hspace`  
This attribute specifies additional horizontal space, in pixels, to be reserved on either side of the applet.

`mayscript`  
In the Netscape implementation, this attribute allows access to an applet by programs in a scripting language embedded in the document.

`name`  
This attribute assigns a name to the applet so that it can be identified by other resources; particularly scripts.

`object`  
This attribute specifies the URL of a serialized representation of an applet.

`src`  
As defined for Internet Explorer 4 and higher, this attribute specifies a URL for an associated file for the applet. The meaning and use is unclear and not part of the HTML standard.

`vspace`  
This attribute specifies additional vertical space, in pixels, to be reserved above and below the applet.

`width`  
This attribute specifies in pixels the width that the applet needs.

Example
-------

### HTML

    <applet code="game.class" align="left" archive="game.zip" height="250" width="350">
      <param name="difficulty" value="easy">
      <b>Sorry, you need Java to play this game.</b>
    </applet>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html52/obsolete.html#the-applet-element">HTML 5.2<br />
<span class="small">The definition of '&lt;applet&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/obsolete.html#the-applet-element">HTML 5.1<br />
<span class="small">The definition of '&lt;applet&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/obsolete.html#the-applet-element">HTML5<br />
<span class="small">The definition of '&lt;applet&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Made obsolete</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html401/struct/objects.html#h-13.4">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;applet&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecated in favor of <a href="object"><code>&lt;object&gt;</code></a></td></tr></tbody></table>

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

`applet`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

Removal in Safari is [under consideration](https://webkit.org/b/157926).

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`align`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`alt`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`archive`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`code`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`codebase`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`datafld`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`datasrc`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`height`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`hspace`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`mayscript`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`name`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`object`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`src`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`vspace`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

`width`

Yes-47

12-79

Yes-56

Yes

Yes-34

Yes

No

Yes-47

Yes-56

Yes-34

No

Yes-5.0

Notes
-----

The W3C specification does not encourage the use of `<applet>` and prefers the use of the [`<object>`](object) element. Under the strict definition of HTML 4.01, this element is deprecated and entirely obsolete in HTML5.

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/applet</a>
