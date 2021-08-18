# scroll-snap-type

The `scroll-snap-type` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how strictly snap points are enforced on the scroll container in case there is one.

Specifying any precise animations or physics used to enforce those snap points is not covered by this property but instead left up to the user agent.

    /* Keyword values */
    scroll-snap-type: none;
    scroll-snap-type: x;
    scroll-snap-type: y;
    scroll-snap-type: block;
    scroll-snap-type: inline;
    scroll-snap-type: both;

    /* Optional mandatory | proximity*/
    scroll-snap-type: x mandatory;
    scroll-snap-type: y proximity;
    scroll-snap-type: both mandatory;

    /* etc */

    /* Global values */
    scroll-snap-type: inherit;
    scroll-snap-type: initial;
    scroll-snap-type: unset;

## Syntax

### Values

`none`  
When the visual [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) of this scroll container is scrolled, it must ignore snap points.

`x`  
The scroll container snaps to snap positions in its horizontal axis only.

`y`  
The scroll container snaps to snap positions in its vertical axis only.

`block`  
The scroll container snaps to snap positions in its block axis only.

`inline`  
The scroll container snaps to snap positions in its inline axis only.

`both`  
The scroll container snaps to snap positions in both of its axes independently (potentially snapping to different elements in each axis).

`mandatory`  
The visual viewport of this scroll container will rest on a snap point if it isn't currently scrolled. That means it snaps on that point when the scroll action finished, if possible. If content is added, moved, deleted or resized the scroll offset will be adjusted to maintain the resting on that snap point.

`proximity`  
The visual viewport of this scroll container may come to rest on a snap point if it isn't currently scrolled considering the user agent's scroll parameters. If content is added, moved, deleted or resized the scroll offset may be adjusted to maintain the resting on that snap point.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | [ x | y | block | inline | both ] [ mandatory | proximity ]?

## Examples

### Snapping in different axes

#### HTML

    <div class="holster">
    <div class="container x mandatory-scroll-snapping" dir="ltr">
      <div>X Mand. LTR</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container x proximity-scroll-snapping" dir="ltr">
      <div>X Prox. LTR</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container y mandatory-scroll-snapping" dir="ltr">
      <div>Y Mand. LTR</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container y proximity-scroll-snapping" dir="ltr">
      <div>Y Prox. LTR</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container x mandatory-scroll-snapping" dir="rtl">
      <div>X Mand. RTL</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container x proximity-scroll-snapping" dir="rtl">
      <div>X Prox. RTL</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container y mandatory-scroll-snapping" dir="rtl">
      <div>Y Mand. RTL</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container y proximity-scroll-snapping" dir="rtl">
      <div>Y Prox. RTL</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>
    </div>

#### CSS

    /* setup */
    html, body, .holster {
      height: 100%;
    }
    .holster {
      display: flex;
      align-items: center;
      justify-content: space-between;
      flex-flow: column nowrap;
      font-family: monospace;
    }

    .container {
      display: flex;
      overflow: auto;
      outline: 1px dashed lightgray;
      flex: none;
    }

    .container.x {
      width: 100%;
      height: 128px;
      flex-flow: row nowrap;
    }

    .container.y {
      width: 256px;
      height: 256px;
      flex-flow: column nowrap;
    }
    /* scroll-snap */
    .x.mandatory-scroll-snapping {
      scroll-snap-type: x mandatory;
    }

    .y.mandatory-scroll-snapping {
      scroll-snap-type: y mandatory;
    }

    .x.proximity-scroll-snapping {
      scroll-snap-type: x proximity;
    }

    .y.proximity-scroll-snapping {
      scroll-snap-type: y proximity;
    }

    .container > div {
      text-align: center;
      scroll-snap-align: center;
      flex: none;
    }

    .x.container > div {
      line-height: 128px;
      font-size: 64px;
      width: 100%;
      height: 128px;
    }

    .y.container > div {
      line-height: 256px;
      font-size: 128px;
      width: 256px;
      height: 100%;
    }
    /* appearance fixes */
    .y.container > div:first-child {
      line-height: 1.3;
      font-size: 64px;
    }
    /* coloration */
    .container > div:nth-child(even) {
      background-color: #87EA87;
    }

    .container > div:nth-child(odd) {
      background-color: #87CCEA;
    }

#### Results

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-snap-type">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-snap-type' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-snap-type`

69

12

Edge supports an earlier draft of CSS Scroll Snap without axis values.

68

39-68

An earlier draft of CSS Scroll Snap without axis values.

10

Internet Explorer supports an earlier draft of CSS Scroll Snap without axis values.

56

11

9

Older Safari versions support an earlier draft of CSS Scroll Snap without axis values.

69

69

68

39-68

An earlier draft of CSS Scroll Snap without axis values.

48

11

9

Older Safari versions support an earlier draft of CSS Scroll Snap without axis values.

10.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-type</a>
