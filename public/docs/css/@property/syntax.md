# syntax

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `syntax` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) descriptor is required when using the [`@property`](../@property) [`at-rule`](../at-rule) and describes the allowable syntax for the property.

## Syntax

The following are all valid syntax strings:

    syntax: '<color>'; /* accepts a color */

    syntax: '<length> | <percentage>'; /* accepts lengths or percentages but not calc expressions with a combination of the two */

    syntax: 'small | medium | large'; /* accepts one of these values set as custom idents. */

    syntax: '*'; /* any valid token */

## Values

A string with a supported syntax as defined by the specification. Supported syntaxes are a subset of [CSS types](../css_types). These may be used along, or a number of types can be used in combination.

`"<length>"`  
Any valid [`<length>`](../length) values.

`"<number>"`  
Any valid [`<number>`](../number) values.

`"<percentage>"`  
Any valid [`<percentage>`](../percentage) values.

`"<length-percentage>"`  
Any valid [`<length-percentage>`](../length-percentage) values.

`"<color>"`  
Any valid [`<color>`](../color_value) values.

`"<image>"`  
Any valid [`<image>`](../image) values.

`"<url>"`  
Any valid [`url()`](<../url()>) values.

`"<integer>"`  
Any valid [`<integer>`](../integer) values.

`"<angle>"`  
Any valid [`<angle>`](../angle) values.

`"<time>"`  
Any valid [`<time>`](../time) values.

`"<resolution>"`  
Any valid [`<resolution>`](../resolution) values.

`"<transform-function>"`  
Any valid [`<transform-function>`](../transform-function) values.

`"<custom-ident>"`  
Any valid [`<custom-ident>`](../custom-ident) values.

`"<transform-list>"`  
A list of valid [`<transform-function>`](../transform-function) values.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@property"><code>@property</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>n/a (required)</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <string>

## Examples

Add type checking to `--my-color` [`custom property`](../--*), using the `<color>` syntax:

Using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`@property`](../@property) [at-rule](../at-rule):

    @property --my-color {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

Using [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) [`CSS.registerProperty`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/RegisterProperty):

    window.CSS.registerProperty({
      name: '--my-color',
      syntax: '<color>',
      inherits: false,
      initialValue: '#c0ffee',
    });

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#the-syntax-descriptor">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'syntax' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

No

## See also

- [CSS Properties and Values API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API)
- [CSS Painting API](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Painting_API)
- [CSS Typed Object Model](https://developer.mozilla.org/en-US/docs/Web/API/CSS_Typed_OM_API)
- [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@property/syntax</a>
