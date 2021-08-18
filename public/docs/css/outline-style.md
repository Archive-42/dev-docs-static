# outline-style

The `outline-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets the style of an element's outline. An outline is a line that is drawn around an element, outside the [`border`](border).

It is often more convenient to use the shorthand property [`outline`](outline) when defining the appearance of an outline.

## Syntax

    /* Keyword values */
    outline-style: auto;
    outline-style: none;
    outline-style: dotted;
    outline-style: dashed;
    outline-style: solid;
    outline-style: double;
    outline-style: groove;
    outline-style: ridge;
    outline-style: inset;
    outline-style: outset;

    /* Global values */
    outline-style: inherit;
    outline-style: initial;
    outline-style: unset;

The `outline-style` property is specified as any one of the values listed below.

### Values

`auto`

Permits the user agent to render a custom outline style.

`none`

No outline is used. The [`outline-width`](outline-width) is `0`.

`dotted`

The outline is a series of dots.

`dashed`

The outline is a series of short line segments.

`solid`

The outline is a single line.

`double`

The outline is two single lines. The [`outline-width`](outline-width) is the sum of the two lines and the space between them.

`groove`

The outline looks as though it were carved into the page.

`ridge`

The opposite of `groove`: the outline looks as though it were extruded from the page.

`inset`

The outline makes the box look as though it were embedded in the page.

`outset`

The opposite of `inset`: the outline makes the box look as though it were coming out of the page.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | <'border-style'>

## Examples

### Setting outline style to auto

The `auto` value indicates a custom outline style — “typically a style \[that\] is either a user interface default for the platform, or perhaps a style that is richer than can be described in detail in CSS, e.g. a rounded edge outline with semi-translucent outer pixels that appears to glow.”

#### HTML

    <div>
      <p class="auto">Outline Demo</p>
    </div>

#### CSS

    .auto {
      outline-style: auto; /* same result as "outline: auto" */
    }

    /* To make the Demo clearer */
    * { outline-width: 10px; padding: 15px; }

#### Result

### Setting outline style to dashed and dotted

#### HTML

    <div>
      <div class="dotted">
        <p class="dashed">Outline Demo</p>
      </div>
    </div>

#### CSS

    .dotted {
      outline-style: dotted; /* same result as "outline: dotted" */
    }
    .dashed {
      outline-style: dashed;
    }

    /* To make the Demo clearer */
    * { outline-width: 10px; padding: 15px; }

#### Result

### Setting outline style to solid and double

#### HTML

    <div>
      <div class="solid">
        <p class="double">Outline Demo</p>
      </div>
    </div>

#### CSS

    .solid {
      outline-style: solid;
    }
    .double {
      outline-style: double;
    }

    /* To make the Demo clearer */
    * { outline-width: 10px; padding: 15px; }

#### Result

### Setting outline style to groove and ridge

#### HTML

    <div>
      <div class="groove">
        <p class="ridge">Outline Demo</p>
      </div>
    </div>

#### CSS

    .groove {
      outline-style: groove;
    }
    .ridge {
      outline-style: ridge;
    }

    /* To make the Demo clearer */
    * { outline-width: 10px; padding: 15px; }

#### Result

### Setting outline style to inset and outset

#### HTML

    <div>
      <div class="inset">
        <p class="outset">Outline Demo</p>
      </div>
    </div>

#### CSS

    .inset {
      outline-style: inset;
    }
    .outset {
      outline-style: outset;
    }

    /* To make the Demo clearer */
    * { outline-width: 10px; padding: 15px; }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#outline-style">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'outline-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Added <code>auto</code> value.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/ui.html#propdef-outline-style">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'outline-style' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`outline-style`

1

12

1.5

1-3.6

8

7

1.2

2

18

4

10.1

1

1.0

`auto`

1

79

1.5

No

15

1.2

≤37

18

4

14

1

1.0

## See also

- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-width`](outline-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/outline-style</a>
