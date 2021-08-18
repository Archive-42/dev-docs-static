# var()

The `var()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) can be used to insert the value of a [custom property](--*) (sometimes called a "CSS variable") instead of any part of a value of another property.

The `var()` function cannot be used in property names, selectors or anything else besides property values. (Doing so usually produces invalid syntax, or else a value whose meaning has no connection to the variable.)

## Syntax

The first argument to the function is the name of the custom property to be substituted. An optional second argument to the function serves as a fallback value. If the custom property referenced by the first argument is invalid, the function uses the second value.

    var( <custom-property-name> , <declaration-value>? )

**Note:** The syntax of the fallback, like that of custom properties, allows commas. For example, `var(--foo, red, blue)` defines a fallback of `red, blue`; that is, anything between the first comma and the end of the function is considered a fallback value.

### Values

`<custom-property-name>`  
A custom property’s name represented by an identifier that starts with two dashes. Custom properties are solely for use by authors and users; CSS will never give them a meaning beyond what is presented here.

`<declaration-value>`  
The custom property's fallback value, which is used in case the custom property is invalid in the used context. This value may contain any character except some characters with special meaning like newlines, unmatched closing brackets, i.e. `)`, `]`, or `}`, top-level semicolons, or exclamation marks.

## Examples

### Using a custom property set on :root

    :root {
      --main-bg-color: pink;
    }

    body {
      background-color: var(--main-bg-color);
    }

### Custom properties with fallbacks for use when the property has not been set

    /* Fallback */
    /* In the component’s style: */
    .component .header {
      color: var(--header-color, blue); /* header-color isn’t set, and so remains blue, the fallback value */
    }

    .component .text {
      color: var(--text-color, black);
    }

    /* In the larger application’s style: */
    .component {
      --text-color: #080;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/css-variables-1/#using-variables">CSS Custom Properties for Cascading Variables Module Level 1<br />
<span class="small">The definition of 'var()' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`var()`

49

15

31

No

36

9.1

50

49

31

36

9.3

5.0

## See also

- [`env(…)`](<env()>) – read‑only environment variables controlled by the user‑agent.
- [Using CSS variables](using_css_custom_properties)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/var()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/var()</a>
