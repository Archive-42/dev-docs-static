HTMLScriptElement
=================

HTML [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements expose the `HTMLScriptElement` interface, which provides special properties and methods for manipulating the behavior and execution of `<script>` elements (beyond the inherited [`HTMLElement`](htmlelement) interface).

JavaScript files should be served with the `application/javascript` [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types), but browsers are lenient and block them only if the script is served with an image type (`image/*`), video type (`video/*`), audio type (`audio/*`), or `text/csv`. If the script is blocked, its element receives an `error` event; otherwise, it receives a `load` event.

Properties
----------

*Inherits properties from its parent, [`HTMLElement`](htmlelement).*

<span class="page-not-created">`HTMLScriptElement.type`</span>  
Is a [`DOMString`](domstring) representing the MIME type of the script. It reflects the [`type`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-type) attribute.

<span class="page-not-created">`HTMLScriptElement.src`</span>  
Is a [`DOMString`](domstring) representing the URL of an external script. It reflects the [`src`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-src) attribute.

 <span class="page-not-created">`HTMLScriptElement.event`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring); an obsolete way of registering event handlers on elements in an HTML document.

 <span class="page-not-created">`HTMLScriptElement.charset`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>   
Is a [`DOMString`](domstring) representing the character encoding of an external script. It reflects the [`charset`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-charset) attribute.

<span class="page-not-created">`HTMLScriptElement.async`</span>  
<span class="page-not-created">`HTMLScriptElement.defer`</span>  
The `async` and `defer` attributes are [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) attributes that control how the script should be executed. **The `defer` and `async` attributes must not be specified if the `src` attribute is absent.**

There are three possible execution modes:

1.  If the `async` attribute is present, then the script will be executed asynchronously as soon as it downloads.
2.  If the `async` attribute is absent but the `defer` attribute is present, then the script is executed when [the page has finished parsing](window/domcontentloaded_event).
3.  If neither attribute is present, then the script is fetched and executed immediately, blocking further parsing of the page.

The `defer` attribute may be specified with the `async` attribute, so legacy browsers that only support `defer` (and not `async`) fall back to the `defer` behavior instead of the default blocking behavior.

**Note:** The exact processing details for these attributes are complex, involving many different aspects of HTML, and therefore are scattered throughout the specification. [These algorithms](https://www.w3.org/html/wg/drafts/html/master/scripting-1.html#prepare-a-script) describe the core ideas, but they rely on the parsing rules for [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) [start](https://www.w3.org/html/wg/drafts/html/master/syntax.html#scriptTag) and [end](https://www.w3.org/html/wg/drafts/html/master/syntax.html#scriptEndTag) tags in HTML, [in foreign content](https://www.w3.org/html/wg/drafts/html/master/syntax.html#scriptForeignEndTag), and [in XML](https://www.w3.org/html/wg/drafts/html/master/the-xhtml-syntax.html#scriptTagXML); the rules for the [`document.write()`](document/write) method; the handling of [scripting](https://www.w3.org/html/wg/drafts/html/master/webappapis.html#scripting); and so on.

 <span class="page-not-created">`HTMLScriptElement.crossOrigin`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>   
Is a [`DOMString`](domstring) reflecting the [CORS setting](https://developer.mozilla.org/en-US/docs/Web/HTML/Attributes/crossorigin) for the script element. For scripts from other [origins](https://developer.mozilla.org/en-US/docs/Glossary/Origin), this controls if error information will be exposed.

<span class="page-not-created">`HTMLScriptElement.text`</span>  
Is a [`DOMString`](domstring) that joins and returns the contents of all [`Text` nodes](text) inside the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element (ignoring other nodes like comments) in tree order. On setting, it acts the same way as the [`textContent`](node/textcontent) IDL attribute.

**Note:** When inserted using the [`document.write()`](document/write) method, [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) elements execute (typically synchronously), but when inserted using [`innerHTML`](element/innerhtml) or [`outerHTML`](element/outerhtml), they do not execute at all.

<span class="page-not-created">`HTMLScriptElement.noModule`</span>  
Is a [`Boolean`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean) that if true, stops the script's execution in browsers that support [ES2015 modules](https://hacks.mozilla.org/2015/08/es6-in-depth-modules/) — used to run fallback scripts in older browsers that do *not* support JavaScript modules.

[`HTMLScriptElement.referrerPolicy`](htmlscriptelement/referrerpolicy)  
Is a [`DOMString`](domstring) that reflects the [`referrerpolicy`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script#attr-referrerpolicy) HTML attribute indicating which referrer to use when fetching the script, and fetches done by that script.

Methods
-------

*No specific methods; inherits methods from its parent, [`HTMLElement`](htmlelement).*

Examples
--------

### Dynamically importing scripts

Let's create a function that imports new scripts within a document creating a [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) node *immediately before* the [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) that hosts the following code (through [`document.currentScript`](document/currentscript)). These scripts will be **asynchronously** executed. For more details, see the [`defer`](#defer_property) and [`async`](#async_property) properties.

    function loadError(oError) {
      throw new URIError("The script " + oError.target.src + " didn't load correctly.");
    }

    function prefixScript(url, onloadFunction) {
      var newScript = document.createElement("script");
      newScript.onerror = loadError;
      if (onloadFunction) { newScript.onload = onloadFunction; }
      document.currentScript.parentNode.insertBefore(newScript, document.currentScript);
      newScript.src = url;
    }

This next function, instead of prepending the new scripts immediately before the [`document.currentScript`](document/currentscript) element, appends them as children of the [`<head>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head) tag.

    function loadError(oError) {
      throw new URIError("The script " + oError.target.src + " didn't load correctly.");
    }

    function affixScriptToHead(url, onloadFunction) {
      var newScript = document.createElement("script");
      newScript.onerror = loadError;
      if (onloadFunction) { newScript.onload = onloadFunction; }
      document.head.appendChild(newScript);
      newScript.src = url;
    }

Sample usage:

    affixScriptToHead("myScript1.js");
    affixScriptToHead("myScript2.js", function () { alert("The script \"myScript2.js\" has been correctly loaded."); });

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#htmlscriptelement">HTML Living Standard<br />
<span class="small">The definition of 'HTMLScriptElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/scripting-1.html#the-script-element">HTML 5.1<br />
<span class="small">The definition of 'HTMLScriptElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/scripting-1.html#the-script-element">HTML5<br />
<span class="small">The definition of 'HTMLScriptElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>The following properties are now obsolete: <code>htmlFor,</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-81598695">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLScriptElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>No change from <a href="https://www.w3.org/TR/REC-DOM-Level-1/">Document Object Model (DOM) Level 1 Specification</a>.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-81598695">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLScriptElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`HTMLScriptElement`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`async`

6

12

3.6

10

15

5.1

≤37

18

4

14

5

1.0

`charset`

1

12

1

6

≤12.1

3

1

18

4

≤12.1

1

1.0

`crossOrigin`

1

14

14

11

15

6

1

18

14

14

6

1.0

`defer`

1

12

3.5

10

In versions prior to Internet Explorer 10, it implemented `defer` by a proprietary specification. Since version 10 it conforms to the W3C specification.

≤12.1

3

1

18

4

≤12.1

1

1.0

`event`

1

12

1

5.5

15

3

1

18

4

14

1

1.0

`htmlFor`

1

12

1

5.5

15

3

1

18

4

14

1

1.0

`integrity`

45

17

43

No

32

11.1

43

45

43

32

11.3

5.0

`noModule`

61

16

60

No

48

11

61

61

60

45

11

8.0

`referrerPolicy`

70

79

65

No

57

14

70

70

65

49

14

10.0

`src`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`text`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

`type`

1

12

1

5.5

≤12.1

3

1

18

4

≤12.1

1

1.0

See also
--------

-   HTML [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) element
-   HTML [`<noscript>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/noscript) element
-   [`document.currentScript`](document/currentscript)
-   [Web Workers](web_workers_api/using_web_workers) (code snippets similar to scripts but executed in [another global context](dedicatedworkerglobalscope))
-   [Ryan Grove's &lt;script&gt; and &lt;link&gt; node event compatibility chart](https://pieisgood.org/test/script-link-events/)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLScriptElement</a>
