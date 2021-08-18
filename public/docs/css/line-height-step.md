# line-height-step

The `line-height-step` CSS property sets the step unit for line box heights. When the property is set, line box heights are rounded up to the closest multiple of the unit.

    /* Point values */
    line-height-step: 18pt;

## Syntax

The `line-height-step` property is specified as any one of the following:

- a `<length>`.

### Values

`<length>`  
The specified [`<length>`](length) is used in the calculation of the line box height step.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0</code></td></tr><tr class="even"><td>Applies to</td><td>block containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>absolute <a href="length"><code>&lt;length&gt;</code></a></td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    <length>

## Examples

### Setting step unit for line box height

In the following example, the height of line box in each paragraph is rounded up to the step unit. The line box in `<h1>` does not fit into one step unit and thus occupies two, but it is still centered within the two step unit.

    :root {
      font-size: 12pt;
      --my-grid: 18pt;
      line-height-step: var(--my-grid);
    }
    h1 {
      font-size: 20pt;
      margin-top: calc(2 * var(--my-grid));
    }

The result of these rules is shown below in the following screenshot:

<img src="data:image/png;base64,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" alt="How the line-height-step property affects the appearance of text." width="144" height="340" />

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-rhythm/#line-height-step">CSS Rhythmic Sizing<br />
<span class="small">The definition of 'line-height-step' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`line-height-step`

60

79

No

No

47

No

No

60

No

44

No

No

## See also

- [`font`](font)
- [`font-size`](font-size)
- [`line-height`](line-height)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/line-height-step" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/line-height-step</a>
