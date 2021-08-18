# masonry-auto-flow

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `masonry-auto-flow` CSS property modifies how items are placed when using [masonry](css_grid_layout/masonry_layout) in [CSS Grid Layout](css_grid_layout).

## Syntax

    /* Keyword values */
    masonry-auto-flow: pack;
    masonry-auto-flow: next;
    masonry-auto-flow: ordered;
    masonry-auto-flow: definite-first;
    masonry-auto-flow: next ordered;

    /* Global values */
    masonry-auto-flow: inherit;
    masonry-auto-flow: initial;
    masonry-auto-flow: unset;

This property may take one of two forms:

- A single keyword: one of `pack`, `next`, `definite-first`, or `ordered`
- Two keywords, for example `next ordered`.

### Values

`pack`  
As per the default masonry algorithm, items will be placed into the track with the most room.

`next`  
Items will be placed one after the other in the grid axis.

`definite-first`  
Display as in the default masonry algorithm, placing items with a definite place first before placing other masonry items.

`ordered`  
Ignore any items with a definite placement, and place everything according to order-modified document order.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>pack</code></td></tr><tr class="even"><td>Applies to</td><td>Grid containers with masonry layout</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    [ pack | next ] || [ definite-first | ordered ]

## Examples

### Using the next keyword

#### HTML

    <div id="grid">
      <div id="item1"></div>
      <div id="item2"></div>
      <div id="item3"></div>
      <div id="item4"></div>
      <div id="item5"></div>
    </div>
    <select id="flow">
      <option value="pack">pack</option>
      <option value="next">next</option>
    </select>

#### CSS

    #grid {
      height: 200px;
      width: 200px;
      display: grid;
      gap: 10px;
      grid-template-columns: repeat(3, 1fr);
      grid-template-rows: masonry;
      masonry-auto-flow: pack;
    }

    #item1 {
      background-color: lime;
      height: 2em
    }

    #item2 {
      background-color: yellow;
    }

    #item3 {
      background-color: blue;
      height: 3em;
    }

    #item4 {
      background-color: red;
      height: 2.5em;
    }

    #item5 {
      background-color: aqua;
      height: 4em;
    }

    const selectElem = document.querySelector('select');

    function changeMasonryFlow() {
      var grid = document.getElementById("grid");
      var direction = document.getElementById("flow");
      var masonryAutoFlow = direction.value === "pack" ? "pack" : "next";

      grid.style.masonryAutoFlow = masonryAutoFlow;
    }

    selectElem.addEventListener('change', changeMasonryFlow);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-grid-3/#propdef-masonry-auto-flow">CSS Grid Layout Module Level 3<br />
<span class="small">The definition of 'masonry-auto-flow' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`masonry-auto-flow`

No

No

No

No

No

No

No

No

No

No

No

No

The compatibility table in this page is generated from structured data. If you'd like to contribute to the data, please check out <https://github.com/mdn/browser-compat-data> and send us a pull request.

## See also

- Related CSS properties: [`align-tracks`](align-tracks), [`justify-tracks`](justify-tracks)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/masonry-auto-flow" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/masonry-auto-flow</a>
