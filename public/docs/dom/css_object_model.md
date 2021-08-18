# CSS Object Model (CSSOM)

The **CSS Object Model** is a set of APIs allowing the manipulation of CSS from JavaScript. It is much like the DOM, but for the CSS rather than the HTML. It allows users to read and modify CSS style dynamically.

## Reference

- [`AnimationEvent`](animationevent)
- [`CaretPosition`](caretposition)
- [`CSS`](css)
- <span class="page-not-created">`CSSCharsetRule`</span>
- [`CSSConditionRule`](cssconditionrule)
- [`CSSCounterStyleRule`](csscounterstylerule)
- [`CSSFontFaceRule`](cssfontfacerule)
- <span class="page-not-created">`CSSFontFeatureValuesMap`</span>
- <span class="page-not-created">`CSSFontFeatureValuesRule`</span>
- [`CSSGroupingRule`](cssgroupingrule)
- [`CSSImportRule`](cssimportrule)
- [`CSSKeyframeRule`](csskeyframerule)
- [`CSSKeyframesRule`](csskeyframesrule)
- <span class="page-not-created">`CSSMarginRule`</span>
- [`CSSMediaRule`](cssmediarule)
- [`CSSNamespaceRule`](cssnamespacerule)
- [`CSSPageRule`](csspagerule)
- [`CSSRule`](cssrule)
- [`CSSRuleList`](cssrulelist)
- [`CSSStyleDeclaration`](cssstyledeclaration)
- [`CSSStyleSheet`](cssstylesheet)
- [`CSSStyleRule`](cssstylerule)
- [`CSSSupportsRule`](csssupportsrule)
- <span class="page-not-created">`CSSVariablesMap`</span>
- <span class="page-not-created">`CSSViewportRule`</span>
- [`ElementCSSInlineStyle`](elementcssinlinestyle)
- [`FontFace`](fontface)
- [`FontFaceSet`](fontfaceset)
- [`FontFaceSetLoadEvent`](fontfacesetloadevent)
- [`GeometryUtils`](geometryutils)
- <span class="page-not-created">`GetStyleUtils`</span>
- [`LinkStyle`](linkstyle)
- [`MediaList`](medialist)
- [`MediaQueryList`](mediaquerylist)
- [`MediaQueryListEvent`](mediaquerylistevent)
- [`Screen`](screen)
- [`StyleSheet`](stylesheet)
- [`StyleSheetList`](stylesheetlist)
- [`TransitionEvent`](transitionevent)

Several other interfaces are also extended by the CSSOM-related specifications: [`Document`](document), [`Window`](window), [`Element`](element), [`HTMLElement`](htmlelement), [`HTMLImageElement`](htmlimageelement), [`Range`](range), [`MouseEvent`](mouseevent), and [`SVGElement`](svgelement).

### CSS Typed Object Model <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

- [`CSSImageValue`](cssimagevalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSKeywordValue`](csskeywordvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathInvert`](cssmathinvert) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathMax`](cssmathmax) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathMin`](cssmathmin) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathNegate`](cssmathnegate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathProduct`](cssmathproduct) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathSum`](cssmathsum) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMathValue`](cssmathvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSMatrixComponent`](cssmatrixcomponent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSNumericArray`](cssnumericarray) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSNumericValue`](cssnumericvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSPerspective`](cssperspective) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSPositionValue`](csspositionvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSRotate`](cssrotate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSScale`](cssscale) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSSkew`](cssskew) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSSkewX`](cssskewx) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSSkewY`](cssskewy) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSStyleValue`](cssstylevalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSTransformComponent`](csstransformcomponent) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSTransformValue`](csstransformvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSTranslate`](csstranslate) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSUnitValue`](cssunitvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSUnparsedValue`](cssunparsedvalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`CSSVariableReferenceValue`](cssvariablereferencevalue) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`StylePropertyMap`](stylepropertymap) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`StylePropertyMapReadOnly`](stylepropertymapreadonly) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### Obsolete CSSOM interfaces <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

- [`CSSPrimitiveValue`](cssprimitivevalue) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`CSSValue`](cssvalue) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`CSSValueList`](cssvaluelist) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

## Tutorials

- [Determining the dimensions of elements](css_object_model/determining_the_dimensions_of_elements) (it needs some updating as it was made in the DHTML/Ajax era).
- [Managing screen orientation](css_object_model/managing_screen_orientation)

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-typed-om-1/">CSS Typed OM Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.css-houdini.org/css-paint-api-1/">CSS Painting API Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Extended the <a href="css"><code>CSS</code></a> interface with the <a href="css/paintworklet"><code>paintWorklet</code></a> static property.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/">CSS Object Model (CSSOM) View Module</a></td><td><span class="spec-wd">Working Draft</span></td><td>Defined the <a href="screen"><code>Screen</code></a> and <a href="mediaquerylist"><code>MediaQueryList</code></a> interfaces and the <a href="mediaquerylistevent"><code>MediaQueryListEvent</code></a> event and <a href="mediaquerylist"><code>MediaQueryList</code></a> event listener.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/cssom/">CSS Object Model (CSSOM)</a></td><td><span class="spec-wd">Working Draft</span></td><td>Extended the <a href="css"><code>CSS</code></a> interface and provides the base for the modern CSSOM specification.</td></tr><tr class="odd"><td><a href="https://w3c.github.io/screen-orientation/">Screen Orientation API</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-fonts-3/">CSS Fonts Module Level 3</a></td><td><span class="spec-rec">Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-animations-1/">CSS Animations Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-transitions/">CSS Transitions</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/css-variables-1/">CSS Custom Properties for Cascading Variables Module Level 1</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-conditional-3/">CSS Conditional Rules Module Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Defined the <a href="css"><code>CSS</code></a> interface.</td></tr><tr class="odd"><td><a href="https://drafts.csswg.org/css-device-adapt/">CSS Device Adaptation</a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://drafts.csswg.org/css-counter-styles-3/">CSS Counter Styles Level 3</a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Style/">Document Object Model (DOM) Level 2 Style Specification</a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

## See also

- [Document Object Model (DOM)](document_object_model)
- [Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Object_Model</a>
