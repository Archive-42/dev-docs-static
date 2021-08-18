# CSSConditionRule.conditionText

The `conditionText` property of the [`CSSConditionRule`](../cssconditionrule) interface returns or sets the text of the CSS rule.

## Syntax

    var text = CSSConditionRule.conditionText
    cssConditionRule.conditionText = text

### Value

A [`CSSOMString`](../cssomstring).

## Examples

The following example demonstrates getting and setting the value of `conditionText` on a [`CSSMediaRule`](../cssmediarule) which implements the [`CSSConditionRule`](../cssconditionrule) interface.

    @media (min-width: 500px) {
      body {
        color: blue;
      }
    }

    let myRules = document.styleSheets[0].cssRules;
    let text = myRules[0].conditionText;
    console.log(text); // "(min-width: 500px)"
    text = "(min-width: 400px)";
    console.log(text);  // "(min-width: 400px)"

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-conditional-3/#dom-cssconditionrule-conditiontext">CSS Conditional Rules Module Level 3<br />
<span class="small">The definition of 'conditionText' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

No compatibility data found for `api.CSSConditionRule.conditionText`.  
[Check for problems with this page](#on-github) or contribute missing data to [mdn/browser-compat-data](https://github.com/mdn/browser-compat-data).

## See also

- [Using dynamic styling information](../css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSConditionRule/conditionText" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSConditionRule/conditionText</a>
