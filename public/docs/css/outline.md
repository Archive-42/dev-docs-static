# outline

The `outline` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [shorthand property](shorthand_properties) set all the outline properties in a single declaration.

## Constituent properties

This property is a shorthand for the following CSS properties:

- [`outline-color`](outline-color)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)

## Syntax

    /* style */
    outline: solid;

    /* color | style */
    outline: #f66 dashed;

    /* style | width */
    outline: inset thick;

    /* color | style | width */
    outline: green solid 3px;

    /* Global values */
    outline: inherit;
    outline: initial;
    outline: unset;

The `outline` property may be specified using one, two, or three of the values listed below. The order of the values does not matter.

**Note:** The outline will be invisible for many elements if its style is not defined. This is because the style defaults to `none`. A notable exception is `input` elements, which are given default styling by browsers.

### Values

`<'outline-color'>`  
Sets the color of the outline. Defaults to `currentcolor` if absent. See [`outline-color`](outline-color).

`<'outline-style'>`  
Sets the style of the outline. Defaults to `none` if absent. See [`outline-style`](outline-style).

`<'outline-width'>`  
Sets the thickness of the outline. Defaults to `medium` if absent. See [`outline-width`](outline-width).

## Description

[Borders](border) and outlines are very similar. However, outlines differ from borders in the following ways:

- Outlines never take up space, as they are drawn outside of an element's content.
- According to the spec, outlines don't have to be rectangular, although they usually are.

As with all shorthand properties, any omitted sub-values will be set to their [initial value](initial_value).

## Accessibility concerns

Assigning `outline` a value of `0` or `none` will remove the browser's default focus style. If an element can be interacted with it must have a visible focus indicator. Provide obvious focus styling if the default focus style is removed.

- [How to Design Useful and Usable Focus Indicators](https://www.deque.com/blog/give-site-focus-tips-designing-usable-focus-indicators/)
- WCAG 2.1: [Understanding Success Criterion 2.4.7: Focus Visible](https://www.w3.org/WAI/WCAG21/Understanding/focus-visible.html)

## Formal definition

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="outline-color"><code>outline-color</code></a>: <code>invert</code>, for browsers supporting it, <code>currentColor</code> for the other</li><li><a href="outline-style"><code>outline-style</code></a>: <code>none</code></li><li><a href="outline-width"><code>outline-width</code></a>: <code>medium</code></li></ul></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="outline-color"><code>outline-color</code></a>: For the keyword <code>invert</code>, the computed value is <code>invert</code>. For the color value, if the value is translucent, the computed value will be the <code>rgba()</code> corresponding one. If it isn't, it will be the <code>rgb()</code> corresponding one. The <code>transparent</code> keyword maps to <code>rgba(0,0,0,0)</code>.</li><li><a href="outline-width"><code>outline-width</code></a>: an absolute length; if the keyword <code>none</code> is specified, the computed value is <code>0</code></li><li><a href="outline-style"><code>outline-style</code></a>: as specified</li></ul></td></tr><tr class="odd"><td>Animation type</td><td>as each of the properties of the shorthand:<br />
<ul><li><a href="outline-color"><code>outline-color</code></a>: a <a href="color_value#interpolation">color</a></li><li><a href="outline-width"><code>outline-width</code></a>: a <a href="length#interpolation">length</a></li><li><a href="outline-style"><code>outline-style</code></a>: discrete</li></ul></td></tr></tbody></table>

## Formal syntax

    [ <'outline-color'> || <'outline-style'> || <'outline-width'> ]

## Examples

### Using outline to set a focus style

#### HTML

    <a href="#">This link has a special focus style.</a>

#### CSS

    a {
      border: 1px solid;
      border-radius: 3px;
      display: inline-block;
      margin: 10px;
      padding: 5px;
    }

    a:focus {
      outline: 4px dotted #e73;
      outline-offset: 4px;
      background: #ffa;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-3/#outline">CSS Basic User Interface Module Level 3<br />
<span class="small">The definition of 'outline' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>No change.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/CSS2/ui.html#propdef-outline">CSS Level 2 (Revision 1)<br />
<span class="small">The definition of 'outline' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition.</td></tr></tbody></table>

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

`outline`

1

12

1.5

Firefox includes absolutely positioned elements inside the outline (see [bug 687311](https://bugzil.la/687311)).

1-3.6

8

7

1.2

1

18

4

10.1

3.1

1.0

## See also

- [`outline-color`](outline-color)
- [`outline-style`](outline-style)
- [`outline-width`](outline-width)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/outline" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/outline</a>
