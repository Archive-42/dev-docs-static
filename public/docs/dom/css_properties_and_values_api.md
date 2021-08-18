# CSS Properties and Values API

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **CSS Properties and Values API** — part of the [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini) umbrella of APIs — allows developers to explicitly define their [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), allowing for property type checking, default values, and properties that do or do not inherit their value.

## Interfaces

[`CSS.registerProperty`](css/registerproperty)  
Defines how a browser should parse a [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*). Access this interface through [`CSS.registerProperty`](css/registerproperty) in [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript).

[`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property)  
Defines how a browser should parse a [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*). Access this interface through [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule) in [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS).

## Examples

The following uses [`CSS.registerProperty`](css/registerproperty) in [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) to type a [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), `--my-color`, as a color, give it a default value, and not allow it to inherit its value:

    window.CSS.registerProperty({
      name: '--my-color',
      syntax: '<color>',
      inherits: false,
      initialValue: '#c0ffee',
    });

The same registration can take place in [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) using the [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule):

    @property --my-color {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/">CSS Properties and Values API Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

## See also

- [Using the CSS properties and values API](css_properties_and_values_api/guide)
- [CSS Painting API](css_painting_api)
- [CSS Typed Object Model](css_typed_om_api)
- [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API</a>
