&lt;isindex&gt;
===============

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

`<isindex>` was an obsolete HTML element that put a text field in a page for querying the document. `<isindex>` provided a single line text input for entering a query string. When sent, the server would return a list of pages matching the query. Its support depended on both the browser and the server to react to the query.

`<isindex>` is removed [HTML Standard](https://html.spec.whatwg.org/multipage/). It was deprecated in HTML 4.01. The same behavior can be achieved with an HTML form. All major browsers have now removed `<isindex>`.

Attributes
----------

Like all other HTML elements, this element accepted the [global attributes](../global_attributes).

`prompt`  
This attribute added its value as a prompt for text field.

`action`  
This attribute determined the server URL to which the query was sent.

Example
-------

    <head>
      <isindex prompt="Search Document..." action="/search">
    </head>

In past browsers, this would generate, at parse time, a DOM tree equivalent to the following HTML:

    <form action="/search">
      <hr>
      <label>
        Search Document...
        <input name="isindex">
      </label>
      <hr>
    </form>

History
-------

On June 1992, Dan Connolly would [prefer](http://1997.webhistory.org/www.lists/www-talk.1992/0080.html) a different [anchor](https://developer.mozilla.org/wiki/HTML/Elements/a) type instead of isindex.

On November 1992, [indexes as links rather than documents](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/thread.html#31) started by Dan Connolly who is pushing the idea that indexes are more links than documents. In this thread, different type of solutions are proposed. The question of forms for making queries is [mentioned](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/0039.html) in reference to Dynatext browser: "The browser displays toggle buttons, text fields etc. The user fills in the fields, clicks OK, and the query results come up in the table of contents window."

A thread about [isindex](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/thread.html#42) in November 1992, Kevin Hoadley [questioned](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/0042.html) the need for an isindex element and proposed to drop it. He proposed to have instead an [input](https://developer.mozilla.org/wiki/HTML/Elements/input) element (idea [supported](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/0053.html) by Steve Putz). Tim Berners-Lee [explains](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/0044.html) the purpose of isindex resulting in aggregated search results. Kevin [replies](https://lists.w3.org/Archives/Public/www-talk/1992NovDec/0048.html) that he doesn't like the boolean nature of isindex and would prefer a system where everything is searchable and proposes to extend the current WWW Framework with a specific httpd configuration and defined that some URIs mapping create search queries.

In 2016, after it was removed from Edge and Chrome, it was [proposed](https://github.com/whatwg/html/issues/1088) to remove `isindex` from the standard; this removal was [completed](https://github.com/whatwg/html/pull/1095) the next day, after which Safari and Firefox also removed support.

HTML Reference
--------------

-   [The HTML Standard](https://html.spec.whatwg.org/multipage/) classifies it as a [obsolete and non-conforming feature](https://html.spec.whatwg.org/multipage/obsolete.html#isindex).
-   [ISINDEX](https://www.w3.org/TR/html401/interact/forms.html#h-17.8) element deprecated in [HTML 4.01](https://www.w3.org/TR/html401/)
-   [ISINDEX](https://www.w3.org/TR/REC-html32#isindex) in [HTML 3.2](https://www.w3.org/TR/REC-html32)
-   [ISINDEX](https://www.w3.org/MarkUp/html-spec/html-spec_5.html#SEC5.2.3) in [HTML 2.0](https://www.w3.org/MarkUp/html-spec/html-spec_5.html) as well the description of the behavior in [Queries and Indexes](https://www.w3.org/MarkUp/html-spec/html-spec_7.html#SEC7.5) (HTML 2.0)
-   [ISINDEX](https://www.w3.org/MarkUp/HTMLPlus/htmlplus_51.html) in [HTML+](https://www.w3.org/MarkUp/HTMLPlus/htmlplus_1.html)

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

`isindex`

No

No

No

No

No

No

No

No

No

No

No

No

`action`

No

No

No

No

No

No

No

No

No

No

No

No

`prompt`

No

No

No

No

No

No

No

No

No

No

No

No

See also
--------

-   [`<input>`](input)
-   [`<form>`](form)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/isindex" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Element/isindex</a>
