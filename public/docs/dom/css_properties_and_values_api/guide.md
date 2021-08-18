# Using the CSS properties and values API

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The **CSS Properties and Values API** — part of the [CSS Houdini](https://developer.mozilla.org/en-US/docs/Web/Houdini) umbrella of APIs — allows the registration of [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), allowing for property type checking, default values, and properties that do or do not inherit their value.

## Registering a custom property

Registering a custom property allows you to tell the browser how the custom property should behave; what are allowed types, whether the custom property inherits its value, and what the default value of the custom property is. There are two ways to register a property, in [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) or in [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS).

### CSS.registerProperty

The following will register a [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), `--my-prop`, using [`CSS.registerProperty`](../css/registerproperty), as a color, give it a default value, and have it not inherit its value:

    window.CSS.registerProperty({
      name: '--my-prop',
      syntax: '<color>',
      inherits: false,
      initialValue: '#c0ffee',
    });

### @property

The same registration can take place in CSS. The following will register a [`css custom properties`](https://developer.mozilla.org/en-US/docs/Web/CSS/--*), `--my-prop`, using [`@property`](https://developer.mozilla.org/en-US/docs/Web/CSS/@property) [at-rule](https://developer.mozilla.org/en-US/docs/Web/CSS/At-rule), as a color, give it a default value, and have it not inherit its value:

    @property --my-prop {
      syntax: '<color>';
      inherits: false;
      initial-value: #c0ffee;
    }

## Using registered custom properties

One of the advantages of registering a property is that the browser now knows how it should handle your custom property through things like transitions! When a property isn't registered, the browser doesn't know how to treat it, so it assumes that any value can be used and therefore can't animate it. When a property has a registered syntax, though, the browser can optimize around that syntax, including being able to animate it!

In this example, the custom property `--registered` has been registered using the syntax `<color>` and then used in a linear gradient. That property is then transitioned on hover or focus to a different color. Notice that with the registered property the transition works, but that it doesn't with the unregistered property!

    .registered {
      --registered: #c0ffee;
      background-image: linear-gradient(to right, #fff, var(--registered));
      transition: --registered 1s ease-in-out;
    }

    .registered:hover,
    .registered:focus {
      --registered: #b4d455;
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

While not functionally accurate, a good way to think about the difference between the unregistered property in the above example and the registered property is the difference between a [`<custom-ident>`](https://developer.mozilla.org/en-US/docs/Web/CSS/custom-ident) and a number when trying to animate [`height`](https://developer.mozilla.org/en-US/docs/Web/CSS/height). You cannot transition or animate from `auto` to a number because the browser doesn't know what the value of `auto` is until it's calculated. With an unregisterd property, the browser likewise doesn't know what the value _may be_ until it's calculated, and because of that, it can't set up a transition from one value to another. When registered, though, you've told the browser what type of value it should expect, and because it knows that, it can then set up the transitions properly.

## Gotchas

There are two gotchas when registering a property. The first is that, once a property is registered, there's no way to update it, and trying to re-register it with [JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript) will throw an error indicating it's already been defined.

Second, unlike standard properties, registered properties aren't validated when they're parsed. Rather, they're validated when they're computed. That means both that invalid values won't appear as invalid when inspecting the element's properties, and that including an invalid property after a valid one won't fall back to the valid property. An invalid property will, however, fall back to its registered default.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API/guide" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/CSS_Properties_and_Values_API/guide</a>
