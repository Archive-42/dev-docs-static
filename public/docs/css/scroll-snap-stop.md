# scroll-snap-stop

The `scroll-snap-stop` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines whether the scroll container is allowed to "pass over" possible snap positions.

    /* Keyword values */
    scroll-snap-stop: normal;
    scroll-snap-stop: always;

    /* Global values */
    scroll-snap-type: inherit;
    scroll-snap-type: initial;
    scroll-snap-type: unset;

## Syntax

### Values

`normal`  
When the visual [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) of this element's scroll container is scrolled, it may "pass over" possible snap positions.

`always`  
The scroll container must not "pass over" a possible snap position; and must snap to the first of this elements' snap positions.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    normal | always

## Examples

### Snapping in different axes

This example is duplicated from [`scroll-snap-type`](scroll-snap-type) with minor variances.

#### CSS

    /* setup */
    :root, body {
      height: 100%;
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
    /* definite scroll snap */
    .mandatory-scroll-snapping > div {
      scroll-snap-stop: always;
    }
    .proximity-scroll-snapping > div {
      scroll-snap-stop: normal;
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
      height: 256px;
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

#### HTML

    <div class="container x mandatory-scroll-snapping" dir="ltr">
      <div>X Mand. LTR </div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container x proximity-scroll-snapping" dir="ltr">
      <div>X Proximity LTR</div>
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
      <div>X Mandatory RTL</div>
      <div>2</div>
      <div>3</div>
      <div>4</div>
      <div>5</div>
    </div>

    <div class="container x proximity-scroll-snapping" dir="rtl">
      <div>X Proximity RTL</div>
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

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-scroll-snap-1/#propdef-scroll-snap-stop">CSS Scroll Snap Module Level 1<br />
<span class="small">The definition of 'scroll-snap-stop' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`scroll-snap-stop`

75

79

No

No

62

No

75

75

No

No

No

11.0

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-stop</a>
