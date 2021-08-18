# CSSCounterStyleRule

The `CSSCounterStyleRule` <span class="page-not-created">interface</span> represents an [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule).

## Inheritance

This interface inherits from the following parent interfaces:

## Properties

_This interface also inherits properties from its parent [`CSSRule`](cssrule)._

<span class="page-not-created">`CSSCounterStyleRule.name`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the <span class="page-not-created">`<counter-style-name>`</span> defined for the associated rule.

<span class="page-not-created">`CSSCounterStyleRule.system`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`system`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/system) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.symbols`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`symbols`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/symbols) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.additiveSymbols`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`additive-symbols`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/additive-symbols) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.negative`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`negative`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/negative) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.prefix`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`prefix`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/prefix) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.suffix`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`suffix`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/suffix) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.range`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`range`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/range) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.pad`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`pad`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/pad) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.speakAs`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`speak-as`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/speak-as) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

<span class="page-not-created">`CSSCounterStyleRule.fallback`</span>  
Is a [`DOMString`](domstring) object that contains the serialization of the [`fallback`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style/fallback) descriptor defined for the associated rule. If the descriptor was not specified in the associated rule, the attribute returns an empty string.

## Methods

_This interface doesn't implement any specific method but inherits methods from its parent [`CSSRule`](cssrule)._

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-counter-styles-3/#the-csscounterstylerule-interface">CSS Counter Styles Level 3<br />
<span class="small">The definition of 'CSSCounterStyleRule' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSCounterStyleRule`

No

No

33

No

No

No

No

No

33

No

No

No

`additiveSymbols`

No

No

33

No

No

No

No

No

33

No

No

No

`fallback`

No

No

33

No

No

No

No

No

33

No

No

No

`name`

No

No

33

No

No

No

No

No

33

No

No

No

`negative`

No

No

33

No

No

No

No

No

33

No

No

No

`pad`

No

No

33

No

No

No

No

No

33

No

No

No

`prefix`

No

No

33

No

No

No

No

No

33

No

No

No

`range`

No

No

33

No

No

No

No

No

33

No

No

No

`speakAs`

No

No

33

No

No

No

No

No

33

No

No

No

`suffix`

No

No

33

No

No

No

No

No

33

No

No

No

`symbols`

No

No

33

No

No

No

No

No

33

No

No

No

`system`

No

No

33

No

No

No

No

No

33

No

No

No

## See also

- [`@counter-style`](https://developer.mozilla.org/en-US/docs/Web/CSS/@counter-style)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSCounterStyleRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSCounterStyleRule</a>
