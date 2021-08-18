# scroll-snap-coordinate

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `scroll-snap-coordinate` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the x and y coordinate positions within an element that will align with its nearest ancestor scroll container's [`scroll-snap-destination`](scroll-snap-destination) for each respective axis.

    /* Keyword value */
    scroll-snap-coordinate: none;

    /* <position> values */
    scroll-snap-coordinate: 50px 50px;                   /* Single coordinate */
    scroll-snap-coordinate: 100px 100px, 100px bottom;   /* Multiple coordinates */

    /* Global values */
    scroll-snap-coordinate: inherit;
    scroll-snap-coordinate: initial;
    scroll-snap-coordinate: unset;

If the element has been transformed, the snap coordinates are likewise transformed, thus aligning the snap points with the element as it is displayed.

## Syntax

### Values

`none`  
Specifies that the element does not contribute to a snap point.

[`<position>`](position_value)  
Specifies the offset of the snap coordinates from the start edge of the element’s border box. For each pairing, the first value gives the x coordinate of the snap coordinate, the second value its y coordinate.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>refer to the element’s border box</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>a <a href="position_value#interpolation">position</a></td></tr></tbody></table>

## Formal syntax

    none | <position>#where
    <position> = [ [ left | center | right ] || [ top | center | bottom ] | [ left | center | right | <length-percentage> ] [ top | center | bottom | <length-percentage> ]? | [ [ left | right ] <length-percentage> ] && [ [ top | bottom ] <length-percentage> ] ]where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting scroll snap coordinates

#### HTML

    <div id="container">
      <div>
        <p>At coordinate (0, 0)</p>
        <div class="scrollContainer coordinate0">
          <div>1</div>
          <div>2</div>
          <div>3</div>
        </div>
      </div>

      <div>
        <p>At coordinate (25, 0)</p>
        <div class="scrollContainer coordinate25">
          <div>1</div>
          <div>2</div>
          <div>3</div>
        </div>
      </div>

      <div>
        <p>At coordinate (50, 0)</p>
        <div class="scrollContainer coordinate50">
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
      scroll-snap-type: mandatory;
      font-size: 0;
    }

    .scrollContainer > div {
      width: 100px;
      height: 100px;
      display: inline-block;
      line-height: 100px;
      text-align: center;
      font-size: 50px;
    }

    .coordinate0 > div {
      scroll-snap-coordinate: 0 0;
    }

    .coordinate25 > div {
      scroll-snap-coordinate: 25px 0;
    }

    .coordinate50 > div {
      scroll-snap-coordinate: 50px 0;
    }

    .scrollContainer > div:nth-child(even) {
      background-color: #87ea87;
    }

    .scrollContainer > div:nth-child(odd) {
      background-color: #87ccea;
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

`scroll-snap-coordinate`

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

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-coordinate" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-coordinate</a>
