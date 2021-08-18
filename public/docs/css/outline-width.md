# outline-width

The [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) `outline-width` property sets the thickness of an element's outline. An outline is a line that is drawn around an element, outside the [`border`](border).

It is often more convenient to use the shorthand property [`outline`](outline) when defining the appearance of an outline.

## Syntax

    /* Keyword values */
    outline-width: thin;
    outline-width: medium;
    outline-width: thick;

    /* <length> values */
    outline-width: 1px;
    outline-width: 0.1em;

    /* Global values */
    outline-width: inherit;

The `outline-width` property is specified as any one of the values listed below.

### Values

[`<length>`](length)  
The width of the outline specified as a `<length>`.

`thin`  
Depends on the user agent. Typically equivalent to `1px` in desktop browsers (including Firefox).

`medium`  
Depends on the user agent. Typically equivalent to `3px` in desktop browsers (including Firefox).

`thick`  
Depends on the user agent. Typically equivalent to `5px` in desktop browsers (including Firefox).

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>medium</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>an absolute length; if the keyword <code>none</code> is specified, the computed value is <code>0</code></td></tr><tr class="odd"><td>Animation type</td><td>a <a href="length#interpolation">length</a></td></tr></tbody></table>

## Formal syntax

    <line-width>where
    <line-width> = <length> | thin | medium | thick

## Examples

### Setting an element's outline width

#### HTML

    <span id="thin">thin</span>
    <span id="medium">medium</span>
    <span id="thick">thick</span>
    <span id="twopixels">2px</span>
    <span id="oneex">1ex</span>
    <span id="em">1.2em</span>

#### CSS

    span {
      outline-style: solid;
      display: inline-block;
      margin: 20px;
    }

    #thin {
      outline-width: thin;
    }

    #medium {
      outline-width: medium;
    }

    #thick {
      outline-width: thick;
    }

    #twopixels {
      outline-width: 2px;
    }

    #oneex {
      outline-width: 1ex;
    }

    #em {
      outline-width: 1.2em;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#outline-width">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'outline-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/ui.html#propdef-outline-width">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'outline-width' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`outline-width`

1

12

1.5

1-3.6

8

7

1.2

37

18

4

14

1

1.0

## See also

- [`outline`](outline)
- [`outline-color`](outline-color)
- [`outline-style`](outline-style)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/outline-width</a>
