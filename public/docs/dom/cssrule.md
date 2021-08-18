# CSSRule

The `CSSRule` interface represents a single CSS rule. There are several types of rules which inherit properties from `CSSRule`.

- [`CSSStyleRule`](cssstylerule)
- [`CSSImportRule`](cssimportrule)
- [`CSSMediaRule`](cssmediarule)
- [`CSSFontFaceRule`](cssfontfacerule)
- [`CSSPageRule`](csspagerule)
- [`CSSNamespaceRule`](cssnamespacerule)
- [`CSSKeyframesRule`](csskeyframesrule)
- [`CSSKeyframeRule`](csskeyframerule)
- [`CSSCounterStyleRule`](csscounterstylerule)
- <span class="page-not-created">`CSSDocumentRule`</span>
- [`CSSSupportsRule`](csssupportsrule)
- <span class="page-not-created">`CSSFontFeatureValuesRule`</span>
- <span class="page-not-created">`CSSViewportRule`</span>

## Properties common to all CSSRule instances

The `CSSRule` interface specifies the properties common to all rules, while properties unique to specific rule types are specified in the more specialized interfaces for those rules' respective types.

[`CSSRule.cssText`](cssrule/csstext)  
Represents the textual representation of the rule, e.g. "`h1,h2 { font-size: 16pt }`" or "`@import 'url'`". To access or modify parts of the rule (e.g. the value of "font-size" in the example) use the properties on the [specialized interface for the rule's type](#type_constants).

[`CSSRule.parentRule`](cssrule/parentrule) <span class="badge inline readonly">Read only </span>  
Returns the containing rule, otherwise `null`. E.g. if this rule is a style rule inside an [`@media`](https://developer.mozilla.org/en-US/docs/Web/CSS/@media) block, the parent rule would be that [`CSSMediaRule`](cssmediarule).

[`CSSRule.parentStyleSheet`](cssrule/parentstylesheet) <span class="badge inline readonly">Read only </span>  
Returns the [`CSSStyleSheet`](cssstylesheet) object for the style sheet that contains this rule

[`CSSRule.type`](cssrule/type) <span class="badge inline readonly">Read only </span><span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>  
Returns one of the Type constants to determine which type of rule is represented.

## Examples

References to a `CSSRule` may be obtained by looking at a [`CSSStyleSheet`](cssstylesheet)'s `cssRules` list.

    let myRules = document.styleSheets[0].cssRules; // Returns a CSSRuleList
    console.log(myRules);

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#css-rules">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Obsoleted values <code>CHARSET_RULE</code> and <code>UNKNOWN_RULE</code>. Added value <code>NAMESPACE_RULE</code>. Deprecates <code>CSSRule.type</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-animations-1/#interface-cssrule">CSS Animations Level 1<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added values <code>KEYFRAMES_RULE</code> and <code>KEYFRAME_RULE</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-fonts-4/#om-fontfeaturevalues">CSS Fonts Module Level 4<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Added value <code>FONT_FEATURE_VALUES_RULE</code>.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#extensions-to-cssrule-interface">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added value <code>COUNTER_STYLE_RULE</code>.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#extensions-to-cssrule-interface">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Added value <code>SUPPORTS_RULE</code>. (<code>DOCUMENT_RULE</code> has been pushed to CSS Conditional Rules Level 4)</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSRule' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSRule`

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

`cssText`

1

12

1

9

The property normalizes rules and does not return the original verbatim rule text. For example, `border-width: 1px; border-style:solid; border-color:white;` returns `border: 1px solid white;`.

≤12.1

1

1

18

4

≤12.1

1

1.0

`parentRule`

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

`parentStyleSheet`

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

`type`

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

## See also

- [Using dynamic styling information](css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRule</a>
