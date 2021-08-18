# CSSStyleSheet

The `CSSStyleSheet` interface represents a single [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) stylesheet, and lets you inspect and modify the list of rules contained in the stylesheet. It inherits properties and methods from its parent, [`StyleSheet`](stylesheet).

A stylesheet consists of a collection of [`CSSRule`](cssrule) objects representing each of the rules in the stylesheet. The rules are contained in a [`CSSRuleList`](cssrulelist), which can be obtained from the stylesheet's [`cssRules`](cssstylesheet/cssrules) property.

For example, one rule might be a [`CSSStyleRule`](cssstylerule) object containing a style such as:

    h1, h2 {
      font-size: 16pt;
    }

Another rule might be an _at-rule_ such as [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) or [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media), and so forth.

See the [Notes](#notes) section for the various ways a `CSSStyleSheet` object can be obtained.

## Properties

_Inherits properties from its parent, [`StyleSheet`](stylesheet)._

[`cssRules`](cssstylesheet/cssrules) <span class="badge inline readonly">Read only </span>  
Returns a live [`CSSRuleList`](cssrulelist) which maintains an up-to-date list of the [`CSSRule`](cssrule) objects that comprise the stylesheet.

This is normally used to access individual rules like this:

    styleSheet.cssRules[i] // where i = 0..cssRules.length-1

To add or remove items in `cssRules`, use the `CSSStyleSheet`'s [`insertRule()`](cssstylesheet/insertrule) and [`deleteRule()`](cssstylesheet/deleterule) methods.

[`ownerRule`](cssstylesheet/ownerrule) <span class="badge inline readonly">Read only </span>  
If this stylesheet is imported into the document using an [`@import`](https://developer.mozilla.org/en-US/docs/Web/CSS/@import) rule, the `ownerRule` property returns the corresponding [`CSSImportRule`](cssimportrule); otherwise, this property's value is `null`.

## Methods

_Inherits methods from its parent, [`StyleSheet`](stylesheet)._

[`deleteRule()`](cssstylesheet/deleterule)  
Deletes the rule at the specified index into the stylesheet's rule list.

[`insertRule()`](cssstylesheet/insertrule)  
Inserts a new rule at the specified position in the stylesheet, given the textual representation of the rule.

## Legacy properties

_These properties are legacy properties first introduced by Microsoft long ago; they shouldn't be used but are not likely to be removed anytime soon._

[`rules`](cssstylesheet/rules) <span class="badge inline readonly">Read only </span>  
The `rules` property is functionally identical to the standard [`cssRules`](cssstylesheet/cssrules) property; it returns a live [`CSSRuleList`](cssrulelist) which maintains an up-to-date list of all of the rules in the style sheet.

## Legacy methods

_These methods are legacy methods first introduced by Microsoft; they should not be used if they can be avoided, but are not in danger of being removed anytime soon._

[`addRule()`](cssstylesheet/addrule)  
Adds a new rule to the stylesheet given the selector to which the style applies and the style block to apply to the matching elements.

This differs from [`insertRule()`](cssstylesheet/insertrule), which takes the textual representation of the entire rule as a single string.

[`removeRule()`](cssstylesheet/removerule)  
Functionally identical to [`deleteRule()`](cssstylesheet/deleterule); removes the rule at the specified index from the stylesheet's rule list.

## Notes

In some browsers, if a stylesheet is loaded from a different domain, accessing `cssRules` results in `SecurityError`.

A stylesheet is associated with at most one [`Document`](document), which it applies to (unless [disabled](stylesheet/disabled)). A list of `CSSStyleSheet` objects for a given document can be obtained using the [`Document.styleSheets`](document/stylesheets) property. A specific style sheet can also be accessed from its _owner_ object (`Node` or `CSSImportRule`), if any.

A `CSSStyleSheet` object is created and inserted into the document's [`Document.styleSheets`](document/stylesheets) list automatically by the browser, when a stylesheet is loaded for a document. As the stylesheet list cannot be modified directly, there's no useful way to create a new `CSSStyleSheet` object manually (although [Constructable Stylesheet Objects](https://wicg.github.io/construct-stylesheets/) is coming to the web platform soon and is already supported in Blink). To create a new stylesheet, insert a [`<style>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style) or [`<link>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link) element into the document.

A (possibly incomplete) list of ways a stylesheet can be associated with a document follows:

<table><thead><tr class="header"><th>Reason for the style sheet to be associated with the document</th><th>Appears in <code>document.     styleSheets</code> list</th><th>Getting the owner element/rule given the style sheet object</th><th>The interface for the owner object</th><th>Getting the CSSStyleSheet object from the owner</th></tr></thead><tbody><tr class="odd"><td><a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style"><code>&lt;style&gt;</code></a> and <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link"><code>&lt;link&gt;</code></a> elements in the document</td><td>Yes</td><td><a href="stylesheet/ownernode"><code>.ownerNode</code></a></td><td><a href="htmllinkelement"><code>HTMLLinkElement</code></a>,<br />
<a href="htmlstyleelement"><code>HTMLStyleElement</code></a>,<br />
or <a href="svgstyleelement"><code>SVGStyleElement</code></a></td><td><span class="page-not-created"><code>.sheet</code></span></td></tr><tr class="even"><td>CSS <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@import"><code>@import</code></a> rule in other style sheets applied to the document</td><td>Yes</td><td><a href="cssstylesheet/ownerrule"><code>.ownerRule</code></a></td><td><a href="cssimportrule"><code>CSSImportRule</code></a></td><td><a href="cssimportrule/stylesheet"><code>.styleSheet</code></a></td></tr><tr class="odd"><td><code>&lt;?xml-stylesheet ?&gt;</code> processing instruction in the (non-HTML) document</td><td>Yes</td><td><a href="stylesheet/ownernode"><code>.ownerNode</code></a></td><td><a href="processinginstruction"><code>ProcessingInstruction</code></a></td><td><span class="page-not-created"><code>.sheet</code></span></td></tr><tr class="even"><td>HTTP Link Header</td><td>Yes</td><td><em>N/A</em></td><td>N/A</td><td>N/A</td></tr><tr class="odd"><td>User agent (default) style sheets</td><td>No</td><td>N/A</td><td>N/A</td><td>N/A</td></tr></tbody></table>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#cssstylesheet">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSStyleSheet' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSStyleSheet">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSStyleSheet' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`CSSStyleSheet`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`CSSStyleSheet`

73

79

No

No

53

No

73

73

No

47

No

9.0

`addRule`

1

12

68

9

15

1

1

18

68

14

1

1.0

`cssRules`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`deleteRule`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`insertRule`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`ownerRule`

1

12

1

9

≤12.1

1

1

18

4

≤12.1

1

1.0

`removeRule`

1

12

68

9

15

3

1

18

68

14

1

1.0

`replace`

73

79

No

No

60

No

73

73

No

52

No

11.0

`replaceSync`

73

79

No

No

60

No

73

73

No

52

No

11.0

`rules`

1

12

68

9

15

1

1

18

68

14

1

1.0

## See also

- [CSS Object Model](css_object_model)
- [Using dynamic styling information](css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet</a>
