# @property

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `@property` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`at-rule`](at-rule) is part of the [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini) umbrella of APIs, it allows developers to explicitly define their [`css custom properties`](--*), allowing for property type checking, setting default values, and define whether a property can inherit values or not.

The `@property` rule represents a custom property registration directly in a stylesheet without having to run any JS. Valid `@property` rules result in a registered custom property, as if [`CSS.registerProperty`](https://developer.mozilla.org/en-US/docs/Web/API/CSS/RegisterProperty) had been called with equivalent parameters.

## Syntax

    @property --property-name {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

A valid `@property` rule represents a custom property registration, with the property name being the serialization of the in the rule’s prelude.

`@property` rules require a **syntax** and **inherits** descriptor; if either are missing, the entire rule is invalid and must be ignored. The **initial-value** descriptor is optional only if the syntax is the universal syntax definition, otherwise the descriptor is required; if it’s missing, the entire rule is invalid and must be ignored.

Unknown descriptors are invalid and ignored, but do not invalidate the `@property` rule.

## Multiple declarations

To declare multiple custom properties at the same time, use the following syntax:

    @property --primary-color,
    @property --secondary-color,
    @property --text-color {
      syntax: '';
      inherits: true;
    }

    @property --primary-color {
      initial-value: red;
    }

    @property --secondary-color {
      initial-value: blue;
    }

    @property --text-color {
      initial-value: green;
    }

## Examples

Add type checking to `--my-color` [`custom property`](--*), as a color, a default value, and not allow it to inherit its value:

Using [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [`@property`](@property) [at-rule](at-rule):

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

## Formal syntax

    @property <custom-property-name> {
      <declaration-list>
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#at-property-rule">CSS Properties and Values API Level 1</a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`@property`

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

No

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@property" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@property</a>
