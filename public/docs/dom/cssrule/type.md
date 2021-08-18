# CSSRule.type

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The read-only `type` property of the [`CSSRule`](../cssrule) interface is a deprecated property that returns an integer indicating which type of rule the [`CSSRule`](../cssrule) represents.

## Syntax

    var type = cssRule.type;

### Value

An integer which will be one of the type constants listed in the table below.

<table><thead><tr class="header"><th>Type</th><th style="text-align: center;">Value</th><th>Rule-specific interface</th><th>Comments and examples</th></tr></thead><tbody><tr class="odd"><td><code>CSSRule.STYLE_RULE</code></td><td style="text-align: center;"><code>1</code></td><td><a href="../cssstylerule"><code>CSSStyleRule</code></a></td><td>The most common kind of rule:<br />
<code>selector { prop1: val1; prop2: val2; }</code></td></tr><tr class="even"><td><code>CSSRule.IMPORT_RULE</code></td><td style="text-align: center;"><code>3</code></td><td><a href="../cssimportrule"><code>CSSImportRule</code></a></td><td>An <a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@import"><code>@import</code></a> rule. (Until the documentation is completed, see the interface definition in the Mozilla source code: <a href="http://mxr.mozilla.org/mozilla-central/source/dom/interfaces/css/nsIDOMCSSImportRule.idl#9">nsIDOMCSSImportRule</a>.)</td></tr><tr class="odd"><td><code>CSSRule.MEDIA_RULE</code></td><td style="text-align: center;"><code>4</code></td><td><a href="../cssmediarule"><code>CSSMediaRule</code></a></td><td></td></tr><tr class="even"><td><code>CSSRule.FONT_FACE_RULE</code></td><td style="text-align: center;"><code>5</code></td><td><a href="../cssfontfacerule"><code>CSSFontFaceRule</code></a></td><td></td></tr><tr class="odd"><td><code>CSSRule.PAGE_RULE</code></td><td style="text-align: center;"><code>6</code></td><td><a href="../csspagerule"><code>CSSPageRule</code></a></td><td></td></tr><tr class="even"><td><code>CSSRule.KEYFRAMES_RULE</code></td><td style="text-align: center;"><code>7</code></td><td><a href="../csskeyframesrule"><code>CSSKeyframesRule</code></a> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="odd"><td><code>CSSRule.KEYFRAME_RULE</code></td><td style="text-align: center;"><code>8</code></td><td><a href="../csskeyframerule"><code>CSSKeyframeRule</code></a> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="even"><td><em>Reserved for future use</em></td><td style="text-align: center;"><code>9</code></td><td></td><td>Should be used to define color profiles in the future</td></tr><tr class="odd"><td><code>CSSRule.NAMESPACE_RULE</code></td><td style="text-align: center;"><code>10</code></td><td><a href="../cssnamespacerule"><code>CSSNamespaceRule</code></a> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="even"><td><code>CSSRule.COUNTER_STYLE_RULE</code></td><td style="text-align: center;"><code>11</code></td><td><a href="../csscounterstylerule"><code>CSSCounterStyleRule</code></a> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="odd"><td><code>CSSRule.SUPPORTS_RULE</code></td><td style="text-align: center;"><code>12</code></td><td><a href="../csssupportsrule"><code>CSSSupportsRule</code></a></td><td></td></tr><tr class="even"><td><code>CSSRule.DOCUMENT_RULE</code></td><td style="text-align: center;"><code>13</code></td><td><span class="page-not-created"><code>CSSDocumentRule</code></span> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="odd"><td><code>CSSRule.FONT_FEATURE_VALUES_RULE</code></td><td style="text-align: center;"><code>14</code></td><td><span class="page-not-created"><code>CSSFontFeatureValuesRule</code></span></td><td></td></tr><tr class="even"><td><code>CSSRule.VIEWPORT_RULE</code></td><td style="text-align: center;"><code>15</code></td><td><span class="page-not-created"><code>CSSViewportRule</code></span> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="odd"><td><code>CSSRule.REGION_STYLE_RULE</code></td><td style="text-align: center;"><code>16</code></td><td><span class="page-not-created"><code>CSSRegionStyleRule</code></span> <span class="icon experimental" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This is an experimental API that should not be used in production code. </span></td><td></td></tr><tr class="even"><td><code>CSSRule.UNKNOWN_RULE</code></td><td style="text-align: center;"><code>0</code></td><td><span class="page-not-created"><code>CSSUnknownRule</code></span> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td></td></tr><tr class="odd"><td><code>CSSRule.CHARSET_RULE</code></td><td style="text-align: center;"><code>2</code></td><td><code>CSSCharsetRule</code> <span class="icon deprecated" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This deprecated API should no longer be used, but will probably still work. </span></td><td>(Removed in most browsers.)</td></tr></tbody></table>

## Examples

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0].type);

## Specifications

<table><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#concept-css-rule-type">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSRule.type' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Obsoleted values <code>CHARSET_RULE</code> and <code>UNKNOWN_RULE</code>. Added value <code>NAMESPACE_RULE</code>. Deprecates <code>CSSRule.type</code>.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/css.html#CSS-CSSRule">Document Object Model (DOM) Level 2 Style Specification<br />
<span class="small">The definition of 'CSSRule.type' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSRule/type</a>
