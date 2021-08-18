# margin-trim

The `margin-trim` property allows the container to trim the margins of its children where they adjoin the container’s edges.

## Syntax

`none`  
Margins are not trimmed by the container.

`in-flow`  
For in-flow boxes contained by this box, block-axis margins adjacent to the box's edges are truncated to zero.

It also truncates any margins collapsed with such a margin.

`all`  
Trims the margins of in-flow boxes and floats whose margins coincide with the container's content edge.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>Block containers and multi-column containers. It also applies to <a href="::first-letter"><code>::first-letter</code></a> and <a href="::first-line"><code>::first-line</code></a>.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | in-flow | all

## Examples

### Basic usage

Once support is implemented for this property, it will probably work like so:

When you've got a container with some inline children and you want to put a margin between each child but not have it interfere with the spacing at the end of the row, you might do something like this:

    article {
      background-color: red;
      margin: 20px;
      padding: 20px;
      display: inline-block;
    }

    article > span {
      background-color: black;
      color: white;
      text-align: center;
      padding: 10px;
      margin-right: 20px;
    }

The problem here is that you'd end up with 20px too much spacing at the right of the row, so you'd maybe do this to fix it:

    span:last-child {
      margin-right: 0;
    }

It is a pain having to write another rule to achieve this, and it is also not very flexible. Instead, `margin-trim` could fix it:

     article {
      margin-trim: in-flow;
      ...
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-box-4/#margin-trim">CSS Box Model Module Level 4<br />
<span class="small">The definition of 'margin-trim' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td></tr></tbody></table>

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

`margin-trim`

No

No

No

See [bug 1506241](https://bugzil.la/1506241).

No

No

No

No

No

No

See [bug 1506241](https://bugzil.la/1506241).

No

No

No

## See also

- [`margin`](margin)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/margin-trim" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/margin-trim</a>
