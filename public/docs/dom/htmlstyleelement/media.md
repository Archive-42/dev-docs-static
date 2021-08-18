HTMLStyleElement.media
======================

The `HTMLStyleElement.media` property specifies the intended destination medium for style information.

Syntax
------

    medium = style.media
    style.media = medium

### Parameters

-   `medium` is a string describing a single medium or a comma-separated list.

Example
-------

    <!doctype html>
    <html>
    <head>

    <link id="LinkedStyle" rel="stylesheet" href="document.css" type="text/css" media="screen" />
    <style id="InlineStyle" rel="stylesheet" type="text/css" media="screen, print">
    p { color: blue; }
    </style>
    </head>
    <body>

    <script>
    alert('LinkedStyle: ' + document.getElementById('LinkedStyle').media); // 'screen'
    alert('InlineStyle: ' + document.getElementById('InlineStyle').media); // 'screen, print'
    </script>

    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/semantics.html#attr-style-media">HTML Living Standard<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/semantics.html#attr-style-media">HTML 5.1<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/semantics.html#attr-style-media">HTML5<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-HTML/html.html#ID-16428977">Document Object Model (DOM) Level 2 HTML Specification<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/REC-DOM-Level-1/level-one-html.html#ID-16428977">Document Object Model (DOM) Level 1 Specification<br />
<span class="small">The definition of 'HTMLStyleElement' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`media`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLStyleElement/media</a>
