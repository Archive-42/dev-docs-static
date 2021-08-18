# scroll-snap-destination

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `scroll-snap-destination` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the position in x and y coordinates within the scroll container's visual [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) which element snap points align with.

    /* <position> value */
    scroll-snap-destination: 400px 600px;

    /* Global values */
    scroll-snap-destination: inherit;
    scroll-snap-destination: initial;
    scroll-snap-destination: unset;

## Syntax

### Values

`<position>`  
Specifies the offset of the snap destination from the start edge of the scroll container’s visual viewport. The first value gives the x coordinate of the snap destination, the second value its y coordinate.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>0px 0px</code></td></tr><tr class="even"><td>Applies to</td><td>scroll containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relative to same axis of the padding-box of the scroll container</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a <a href="position_value#interpolation">position</a></td></tr></tbody></table>

## Formal syntax

    <position>where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting scroll snap destination

#### HTML

    <div id="container">
      <div>
        <p>At coordinate (0, 0)</p>
        <div class="scrollContainer destination0">
          <div>1</div>
          <div>2</div>
          <div>3</div>
        </div>
      </div>

      <div>
        <p>At coordinate (25, 0)</p>
        <div class="scrollContainer destination25">
          <div>1</div>
          <div>2</div>
          <div>3</div>
        </div>
      </div>

      <div>
        <p>At coordinate (50, 0)</p>
        <div class="scrollContainer destination50">
          <div>1</div>
          <div>2</div>
          <div>3</div>
        </div>
      </div>
    </div>

#### CSS

    #container {
      display: flex;
    }

    #container > div:nth-child(-n+2) {
      margin-right: 20px;
    }

    .scrollContainer {
      width: 100px;
      overflow: auto;
      white-space: nowrap;
      scroll-snap-points-x: repeat(100%);
      scroll-snap-type: mandatory;
      scroll-snap-destination: 20px 0;
      font-size: 0;
    }

    .destination0 {
      scroll-snap-destination: 0 0;
    }

    .destination25 {
      scroll-snap-destination: 25px 0;
    }

    .destination50 {
      scroll-snap-destination: 50px 0;
    }

    .scrollContainer > div {
      width: 100px;
      height: 100px;
      display: inline-block;
      line-height: 100px;
      text-align: center;
      font-size: 50px;
    }

    .scrollContainer > div:nth-child(even) {
      background-color: #87EA87;
    }

    .scrollContainer > div:nth-child(odd) {
      background-color: #87CCEA;
    }

#### Result

## Specifications

Not part of any standard.

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

`scroll-snap-destination`

No

No

39-68

No

No

No

No

No

39-68

No

No

No

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-destination" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-destination</a>
