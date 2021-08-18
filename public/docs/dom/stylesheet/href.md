Stylesheet.href
===============

The `href` property of the [`StyleSheet`](../stylesheet) interface returns the location of the style sheet.

Syntax
------

    uri = stylesheet.href

### Parameters

-   `uri` is a string containing the stylesheet's URI.

Example
-------

     // on a local machine:
     <html>
      <head>
       <link rel="StyleSheet" href="example.css" type="text/css" />
       <script>
        function sref() {
         alert(document.styleSheets[0].href);
        }
       </script>
      </head>
      <body>
       <div class="thunder">Thunder</div>
       <button onclick="sref()">ss</button>
      </body>
     </html>
    // returns "file:////C:/Windows/Desktop/example.css

Notes
-----

If the style sheet is a linked style sheet, the value of its attribute is its location. For inline style sheets, the value of this attribute is `NULL`.

This property is read-only in Firefox, Opera, Google Chrome, and Safari, and it is read/write in Internet Explorer.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-stylesheet-href">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet: href' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`href`

1

12

1

9

Yes

1

Yes

Yes

4

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/href" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/href</a>
