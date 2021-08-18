# CSS.registerProperty()

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `CSS.registerProperty()` method registers [`custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), allowing for property type checking, default values, and properties that do or do not inherit their value.

Registering a custom property allows you to tell the browser how the custom property should behave; what are allowed types, whether the custom property inherits its value, and what the default value of the custom property is.

## Syntax

    CSS.registerProperty(PropertyDefinition);

### Parameters

A `PropertyDefinition` dictionary object, which can contain the following members:

`name`  
A `DOMString` indicating the name of the property being defined.

`syntax` <span class="badge inline optional">Optional</span>  
A `DOMString` representing the expected syntax of the defined property. Defaults to `"*"`.

`inherits`  
A boolean value defining whether the defined property should be inherited (`true`), or not (`false`). Defaults to `false`.

`initialValue` <span class="badge inline optional">Optional</span>  
A `DOMString` representing the initial value of the defined property.

### Return value

`undefined`.

### Exceptions

`InvalidModificationError`  
The given `name` has already been registered.

`SyntaxError`  
The given `name` isn't a valid custom property name (starts with two dashes, e.g. `--foo`).

`TypeError`  
The required `name` and/or `inherits` dictionary members were not provided.

## Examples

The following will register a [`custom property`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), `--my-color`, using `registerProperty()`, as a color, give it a default value, and have it not inherit its value:

    window.CSS.registerProperty({
      name: '--my-color',
      syntax: '<color>',
      inherits: false,
      initialValue: '#c0ffee',
    });

In this example, the custom property `--my-color` has been registered using the syntax `<color>` . We can now use that property to transition a gradient on hover or focus. Notice that with the registered property the transition works, but that it doesn't with the unregistered property!

    .registered {
      --my-color: #c0ffee;
      background-image: linear-gradient(to right, #fff, var(--my-color));
      transition: --my-color 1s ease-in-out;
    }

    .registered:hover,
    .registered:focus {
      --my-color: #b4d455;
    }

    .unregistered {
      --unregistered: #c0ffee;
      background-image: linear-gradient(to right, #fff, var(--unregistered));
      transition: --unregistered 1s ease-in-out;
    }

    .unregistered:hover,
    .unregistered:focus {
      --unregistered: #b4d455;
    }
    button {
      font-size: 3vw;
    }

We can add these styles to some buttons:

    <button class="registered">Background Registered</button>
    <button class="unregistered">Background Not Registered</button>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.css-houdini.org/css-properties-values-api-1/#the-registerproperty-function">CSS Properties and Values API Level 1<br />
<span class="small">The definition of 'The registerProperty() function' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`RegisterProperty`

78

79

No

No

65

No

78

78

No

No

No

12.0

## See also

- [Using the CSS properties and values API](../css_properties_and_values_api/guide)
- [`CSS`](../css)
- [`CSS.supports()`](supports)
- [`CSS.escape()`](escape)
- [`CSS factory functions`](factory_functions)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS/RegisterProperty" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS/RegisterProperty</a>
