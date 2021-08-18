# CSSPropertyRule

The `CSSPropertyRule` interface of the [CSS_Properties_and_Values_API](css_properties_and_values_api) represents a single CSS [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule.

## Properties

_Inherits properties from its ancestor [`CSSRule`](cssrule)._

[`CSSPropertyRule.inherits`](csspropertyrule/inherits) <span class="badge inline readonly">Read only </span>  
Returns the inherit flag of the custom property.

[`CSSPropertyRule.initialvalue`](csspropertyrule/initialvalue) <span class="badge inline readonly">Read only </span>  
Returns the initial value of the custom property.

[`CSSPropertyRule.name`](csspropertyrule/name) <span class="badge inline readonly">Read only </span>  
Returns the name of the custom property.

[`CSSPropertyRule.syntax`](csspropertyrule/syntax) <span class="badge inline readonly">Read only </span>  
Returns the literal syntax of the custom property.

## Methods

_No specific methods; inherits methods from its ancestor [`CSSRule`](cssrule)._

## Examples

This stylesheet contains a single [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) rule. The first [`CSSRule`](cssrule) returned will be a `CSSPropertyRule` with the properties and values as defined by the rule in CSS.

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    let myRules = document.styleSheets[0].cssRules;
    console.log(myRules[0]); //a CSSPropertyRule

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#dom-csspropertyrule">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'CSSPropertyRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSPropertyRule`

85

85

No

No

71

No

85

85

No

60

No

14.0

`inherits`

85

85

No

No

71

No

85

85

No

60

No

14.0

`initialValue`

85

85

No

No

71

No

85

85

No

60

No

14.0

`name`

85

85

No

No

71

No

85

85

No

60

No

14.0

`syntax`

85

85

No

No

71

No

85

85

No

60

No

14.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSPropertyRule</a>
