# CSSStyleDeclaration.cssText

The `cssText` property of the [`CSSStyleDeclaration`](../cssstyledeclaration) interface returns or sets the text of the element's **inline** style declaration only. To be able to set a **stylesheet** rule dynamically, see [Using dynamic styling information.](../css_object_model/using_dynamic_styling_information)

Not to be confused with stylesheet style-rule [`CSSRule.cssText`](../cssrule/csstext).

## Example

    <span id="s1" style="color: red;">
      Some text
    </span>

    <script>
      var elem = document.getElementById("s1");
      alert(elem.style.cssText); // "color: red;"
    </script>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#dom-cssstyledeclaration-csstext">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleDeclaration: cssText' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr></tbody></table>

## Browser compatibility

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

`cssText`

1

12

1

5

≤12.1

1

4.4

18

4

≤12.1

1

1.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleDeclaration/cssText</a>
