StyleSheet.media
================

The `media` property of the [`StyleSheet`](../stylesheet) interface specifies the intended destination media for style information. It is a read-only, array-like `MediaList` object and can be removed with `deleteMedium()` and added with `appendMedium()`.

Example
-------

    <!doctype html>
    <html>
    <head>
    <link rel="stylesheet" href="document.css" type="text/css" media="screen" />
    <style rel="stylesheet" type="text/css" media="screen, print">
    body  { background-color: snow; }
    </style>
    </head>
    <body>

    <script>
    for (var iSheetIndex = 0; iSheetIndex < document.styleSheets.length; iSheetIndex++)
     {
      console.log('document.styleSheets[' + String(iSheetIndex) + '].media: ' +
       JSON.stringify(document.styleSheets[iSheetIndex].media));
      if (iSheetIndex === 0)
        document.styleSheets[iSheetIndex].media.appendMedium('handheld');
      if (iSheetIndex === 1)
        document.styleSheets[iSheetIndex].media.deleteMedium('print');
      console.log('document.styleSheets[' + String(iSheetIndex) + '].media: ' +
       JSON.stringify(document.styleSheets[iSheetIndex].media));
     }
    /*
    will log:
    document.styleSheets[0].media: {"0":"screen"}
    document.styleSheets[0].media: {"0":"screen","1":"handheld"}
    document.styleSheets[1].media: {"0":"screen","1":"print"}
    document.styleSheets[1].media: {"0":"screen"}
    */
    </script>

    </body>
    </html>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-stylesheet-media">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'StyleSheet: media' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

9

Yes

1

Yes

Yes

4

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/media" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheet/media</a>
