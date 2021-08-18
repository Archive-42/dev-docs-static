&lt;body&gt;: The Document Body element
=======================================

The `<body>` represents the content of an HTML document. There can be only one `<body>` element in a document.

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories">Content categories</a></td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Using_HTML_sections_and_outlines#sectioning_roots">Sectioning root</a>.</td></tr><tr class="even"><td>Permitted content</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#flow_content">Flow content</a>.</td></tr><tr class="odd"><td>Tag omission</td><td>The start tag may be omitted if the first thing inside it is not a space character, comment, <a href="script"><code>&lt;script&gt;</code></a> element or <a href="style"><code>&lt;style&gt;</code></a> element. The end tag may be omitted if the <code>&lt;body&gt;</code> element has contents or has a start tag, and is not immediately followed by a comment.</td></tr><tr class="even"><td>Permitted parents</td><td>It must be the second element of an <a href="html"><code>&lt;html&gt;</code></a> element.</td></tr><tr class="odd"><td>Implicit ARIA role</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/Accessibility/ARIA/Roles/Document_Role">document</a></td></tr><tr class="even"><td>Permitted ARIA roles</td><td>No <code>role</code> permitted</td></tr><tr class="odd"><td>DOM interface</td><td><a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement"><code>HTMLBodyElement</code></a><ul><li>The <code>&lt;body&gt;</code> element exposes the <a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLBodyElement"><code>HTMLBodyElement</code></a> interface.</li><li>You can access the <code>&lt;body&gt;</code> element through the <a href="https://developer.mozilla.org/en-US/docs/Web/API/Document/body"><code>document.body</code></a> property.</li></ul></td></tr></tbody></table>

Attributes
----------

This element includes the [global attributes](../global_attributes).

 `alink` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Color of text for hyperlinks when selected. *This method is non-conforming, use CSS [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property in conjunction with the [`:active`](https://developer.mozilla.org/en-US/docs/Web/CSS/:active) pseudo-class instead.*

 `background` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
URI of a image to use as a background. *This method is non-conforming, use CSS [`background`](https://developer.mozilla.org/en-US/docs/Web/CSS/background) property on the element instead.*

 `bgcolor` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Background color for the document. *This method is non-conforming, use CSS [`background-color`](https://developer.mozilla.org/en-US/docs/Web/CSS/background-color) property on the element instead.*

 `bottommargin` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The margin of the bottom of the body. *This method is non-conforming, use CSS [`margin-bottom`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-bottom) property on the element instead.*

 `leftmargin` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The margin of the left of the body. *This method is non-conforming, use CSS [`margin-left`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-left) property on the element instead.*

 `link` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Color of text for unvisited hypertext links. *This method is non-conforming, use CSS [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property in conjunction with the [`:link`](https://developer.mozilla.org/en-US/docs/Web/CSS/:link) pseudo-class instead.*

`onafterprint`  
Function to call after the user has printed the document.

`onbeforeprint`  
Function to call when the user requests printing of the document.

`onbeforeunload`  
Function to call when the document is about to be unloaded.

`onblur`  
Function to call when the document loses focus.

`onerror`  
Function to call when the document fails to load properly.

`onfocus`  
Function to call when the document receives focus.

`onhashchange`  
Function to call when the fragment identifier part (starting with the hash (`'#'`) character) of the document's current address has changed.

 `onlanguagechange` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Function to call when the preferred languages changed.

`onload`  
Function to call when the document has finished loading.

`onmessage`  
Function to call when the document has received a message.

`onoffline`  
Function to call when network communication has failed.

`ononline`  
Function to call when network communication has been restored.

`onpopstate`  
Function to call when the user has navigated session history.

`onredo`  
Function to call when the user has moved forward in undo transaction history.

`onresize`  
Function to call when the document has been resized.

`onstorage`  
Function to call when the storage area has changed.

`onundo`  
Function to call when the user has moved backward in undo transaction history.

`onunload`  
Function to call when the document is going away.

 `rightmargin` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The margin of the right of the body. *This method is non-conforming, use CSS [`margin-right`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-right) property on the element instead.*

 `text` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Foreground color of text. *This method is non-conforming, use CSS [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property on the element instead.*

 `topmargin` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
The margin of the top of the body. *This method is non-conforming, use CSS [`margin-top`](https://developer.mozilla.org/en-US/docs/Web/CSS/margin-top) property on the element instead.*

 `vlink` <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Color of text for visited hypertext links. *This method is non-conforming, use CSS [`color`](https://developer.mozilla.org/en-US/docs/Web/CSS/color) property in conjunction with the [`:visited`](https://developer.mozilla.org/en-US/docs/Web/CSS/:visited) pseudo-class instead.*

Example
-------

    <html>
      <head>
        <title>Document title</title>
      </head>
      <body>
        <p>This is a paragraph</p>
      </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#the-body-element">HTML Living Standard<br />
<span class="small">The definition of '&lt;body&gt;' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Changed the list of non-conforming features.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html52/sections.html#the-body-element">HTML5<br />
<span class="small">The definition of '&lt;body&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Obsoleted the formerly deprecated attributes. Defined the behavior of the non-conforming and never standardized <code>topmargin</code>, <code>leftmargin</code>, <code>rightmargin</code> and <code>bottommargin</code>. Added the <code>on*</code> attributes.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html401/struct/global.html#h-7.5.1">HTML 4.01 Specification<br />
<span class="small">The definition of '&lt;body&gt;' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Deprecated the <code>alink</code>, <code>background</code>, <code>bgcolor</code>, <code>link</code>, <code>text</code> and <code>vlink</code> attributes.</td></tr></tbody></table>

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

`body`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`alink`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`background`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`bgcolor`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`bottommargin`

Yes

79

35

Before Firefox 35, it was supported in Quirks Mode only.

No

Yes

?

Yes

Yes

35

Before Firefox 35, it was supported in Quirks Mode only.

Yes

?

Yes

`leftmargin`

Yes

79

35

Before Firefox 35, it was supported in Quirks Mode only.

No

Yes

?

Yes

Yes

35

Before Firefox 35, it was supported in Quirks Mode only.

Yes

?

Yes

`link`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onafterprint`

1

12

1

Yes

Yes

13

Yes

18

4

Yes

13

1.0

`onbeforeprint`

1

12

1

Yes

Yes

13

Yes

18

4

Yes

13

1.0

`onbeforeunload`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onblur`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onerror`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onfocus`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onhashchange`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onlanguagechange`

?

?

32

No

?

?

?

?

32

?

?

?

`onload`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onmessage`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onoffline`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`ononline`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onpopstate`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onredo`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onresize`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onstorage`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onundo`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`onunload`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`rightmargin`

Yes

79

35

Before Firefox 35, it was supported in Quirks Mode only.

No

Yes

?

Yes

Yes

35

Before Firefox 35, it was supported in Quirks Mode only.

Yes

?

Yes

`text`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

`topmargin`

Yes

79

35

Before Firefox 35, it was supported in Quirks Mode only.

No

Yes

?

Yes

Yes

35

Before Firefox 35, it was supported in Quirks Mode only.

Yes

?

Yes

`vlink`

1

12

1

Yes

Yes

Yes

Yes

18

4

Yes

Yes

1.0

See also
--------

-   [`<html>`](html)
-   [`<head>`](head)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body</a>
