# initial-value

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `initial-value` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) descriptor is required when using the [`@property`](../@property) [`at-rule`](../at-rule) unless the syntax accepts any valid token stream. It sets the initial-value for the property.

The value chosen as the `initial-value` must parse correctly according to the syntax definition. Therefore, if syntax is `<color>` then the initial-value must be a valid [`color`](../color) value.

## Syntax

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

    @property --property-name {
      syntax: '<color>';
      inherits: true;
      initial-value: #c0ffee;
    }

## Values

A string with a value which is a correct value for the chosen `syntax`.

## Formal definition

<table><tbody><tr class="odd"><td>Related <a href="../at-rule">at-rule</a></td><td><a href="../@property"><code>@property</code></a></td></tr><tr class="even"><td><a href="../initial_value">Initial value</a></td><td><code>n/a (required)</code></td></tr><tr class="odd"><td><a href="../computed_value">Computed value</a></td><td>as specified</td></tr></tbody></table>

## Formal syntax

    <string>

## Examples

Add type checking to `--my-color` [`custom property`](../--*), as a color, the initial-value being a valid color:

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

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#initial-value-descriptor">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'initial-value' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`initial-value`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@property/initial-value</a>
