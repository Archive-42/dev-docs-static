StyleSheetList
==============

The `StyleSheetList` interface represents a list of [`StyleSheet`](stylesheet).

It is an array-like object but can't be iterated over using [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array) methods. However It can be iterated over in a standard [`for`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for) loop over its indices, or converted to an [`Array`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array).

Examples
--------

### Get document styleSheet objects with for loop

    for (let i = 0; i < document.styleSheets.length; i++) {
      let styleSheet = document.styleSheets[i];
    }

### Get all CSS rules for the document using Array methods

    const allCSS = [...document.styleSheets]
      .map(styleSheet => {
        try {
          return [...styleSheet.cssRules]
            .map(rule => rule.cssText)
            .join('');
        } catch (e) {
          console.log('Access to stylesheet %s is denied. Ignoring...', styleSheet.href);
        }
      })
      .filter(Boolean)
      .join('\n');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#the-stylesheetlist-interface">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheetList' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

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

`StyleSheetList`

1

12

31

4

Yes

1

Yes

Yes

31

Yes

1

Yes

`item`

1

12

31

4

Yes

1

Yes

Yes

31

Yes

1

Yes

`length`

1

12

31

4

Yes

1

Yes

Yes

31

Yes

1

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/StyleSheetList</a>
