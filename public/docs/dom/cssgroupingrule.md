# CSSGroupingRule

The `CSSGroupingRule` interface of the [`CSS Object Model`](css_object_model) represents any CSS [`at-rule`](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) that contains other rules nested within it.

Objects deriving from it:

- [`CSSConditionRule`](cssconditionrule) and its children: [`CSSMediaRule`](cssmediarule) and [`CSSSupportsRule`](csssupportsrule).
- [`CSSPageRule`](csspagerule)

## Syntax

The syntax is described using the [WebIDL](https://dev.w3.org/2006/webapi/WebIDL/) format.

    interface CSSGroupingRule : CSSRule {
        readonly attribute CSSRuleList cssRules;
        unsigned long insertRule (DOMString rule, unsigned long index);
        void deleteRule (unsigned long index);
    }

## Properties common to all CSSGroupingRule instances

The `CSSGroupingRule` derives from [`CSSRule`](cssrule) and inherits all properties of this class. It has one specific property:

[`CSSGroupingRule.cssRules`](cssgroupingrule/cssrules) <span class="badge inline readonly">Read only </span>  
Returns a [`CSSRuleList`](cssrulelist) of the CSS rules in the media rule.

## Methods

_Inherits methods from its ancestor [`CSSRule`](cssrule)._

[`CSSGroupingRule.deleteRule`](cssgroupingrule/deleterule)  
Deletes a rule from the style sheet.

[`CSSGroupingRule.insertRule`](cssgroupingrule/insertrule)  
Inserts a new style rule into the current style sheet.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom/#cssgroupingrule">CSS Object Model (CSSOM)<br />
<span class="small">The definition of 'CSSGroupingRule' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`CSSGroupingRule`

45

12

20

No

32

No

45

45

20

32

No

5.0

## See also

- [Using dynamic styling information](css_object_model/using_dynamic_styling_information)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSSGroupingRule</a>
