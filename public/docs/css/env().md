# env()

The `env()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [function](css_functions) can be used to insert the value of a user agent-defined environment variable into your CSS, in a similar fashion to the [`var()`](<var()>) function and [custom properties](--*). The difference is that, as well as being user-agent defined rather than user-defined, environment variables are globally scoped to a document, whereas custom properties are scoped to the element(s) on which they are declared.

To tell the browser to use the whole available space on the screen, and so enabling us to use the `env()` variables, we need to add a new viewport meta value:

    <meta name="viewport" content="viewport-fit=cover" />

    body {
      padding:
        env(safe-area-inset-top, 20px)
        env(safe-area-inset-right, 20px)
        env(safe-area-inset-bottom, 20px)
        env(safe-area-inset-left, 20px);
    }

In addition, unlike custom properties, which cannot be used outside of declarations, the `env()` function can be used in place of any part of a property value, or any part of a descriptor (e.g. in [Media query rules](@media)). As the spec evolves, it may also be usable in other places such as selectors.

Originally provided by the iOS browser to allow developers to place their content in a safe area of the viewport, the `safe-area-inset-*` values defined in the specification can be used to help ensure content is visible even to viewers using non‑rectangular displays.

## Syntax

    /* Using the four safe area inset values with no fallback values */
    env(safe-area-inset-top);
    env(safe-area-inset-right);
    env(safe-area-inset-bottom);
    env(safe-area-inset-left);

    /* Using them with fallback values */
    env(safe-area-inset-top, 20px);
    env(safe-area-inset-right, 1em);
    env(safe-area-inset-bottom, 0.5vh);
    env(safe-area-inset-left, 1.4rem);

### Values

`safe-area-inset-top`, `safe-area-inset-right`, `safe-area-inset-bottom`, `safe-area-inset-left`  
The `safe-area-inset-*` variables are four environment variables that define a rectangle by its top, right, bottom, and left insets from the edge of the viewport, which is safe to put content into without risking it being cut off by the shape of a non‑rectangular display. For rectangular viewports, like your average laptop monitor, their value is equal to zero. For non-rectangular displays — like a round watch face — the four values set by the user agent form a rectangle such that all content inside the rectangle is visible.

**Note**: Unlike other CSS properties, user agent-defined property names are case-sensitive.

### Formal syntax

    env( <custom-ident> , <declaration-value>? )

## Examples

The below example makes use of the optional second parameter of `env()`, which allows you to provide a fallback value in case the environment variable is not available.

    <p>
      If the <code>env()</code> function is supported in your browser,
      this paragraph’s text will have 50px of padding between it and
      the left border — but not the top, right and bottom.
      This is because the accompanying CSS is the equivalent of
      <code>padding: 0 0 0 50px</code>, because, unlike other CSS
      properties, user agent property names are case-sensitive.
    </p>

    p {
      width: 300px;
      border: 2px solid red;
      padding:
        env(safe-area-inset-top, 50px)
        env(safe-area-inset-right, 50px)
        env(safe-area-inset-bottom, 50px)
        env(SAFE-AREA-INSET-LEFT, 50px);
    }

### Example values

    padding: env(safe-area-inset-bottom, 50px); /* zero for all rectangular user agents */
    padding: env(Safe-area-inset-bottom, 50px); /* 50px because UA properties are case sensitive */
    padding: env(x, 50px 20px); /* as if padding: '50px 20px' were set because x is not a valid environment variable */
    padding: env(x, 50px, 20px); /* ignored because '50px, 20px' is not a valid padding value and x is not a valid environment variable */

The syntax of the fallback, like that of custom properties, allows commas. But, if the property value doesn't support commas, the value is not valid.

**Note**: User agent properties are not reset by the [all](all) property.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-env-1/#env-function">CSS Environment Variables Module Level 1<br />
<span class="small">The definition of 'env()' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`env()`

69

79

65

No

56

11.1

11-11.1

69

69

65

48

11.3

11-11.3

10.0

## See also

- [`var(…)`](<var()>)
- [CSS Custom Properties for Cascading Variables](css_variables)
- [Custom Properties (--\*)](--*)
- [Using CSS custom properties (variables)](using_css_custom_properties)
- [`viewport-fit (@viewport)`](@viewport)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/env()" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/env()</a>
