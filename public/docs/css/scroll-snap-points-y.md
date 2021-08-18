# scroll-snap-points-y

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `scroll-snap-points-y` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property defines the vertical positioning of snap points within the content of the scroll container they are applied to.

    /* Keyword value */
    scroll-snap-points-y: none;

    /* Repeated snap points */
    scroll-snap-points-y: repeat(400px);

    /* Global values */
    scroll-snap-points-y: inherit;
    scroll-snap-points-y: initial;
    scroll-snap-points-y: unset;

## Syntax

### Values

`none`  
The scroll container does not define any snap points. Elements within the scroll container may still define snap points on behalf of the scroll container.

`repeat(<length-percentage>)`  
Defines an interval at which snap points are defined, starting from the container's relevant start edge. Only positive lengths are allowed. Percentages refer to the width of the container.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>none</code></td></tr><tr class="even"><td>Applies to</td><td>scroll containers</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td>Percentages</td><td>relative to same axis of the padding-box of the scroll container</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified, but with relative lengths converted into absolute lengths</td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | repeat( <length-percentage> )where
    <length-percentage> = <length> | <percentage>

## Examples

### Setting vertical scroll snap points

#### HTML

    <div id="container">
      <div>1</div>
      <div>2</div>
      <div>3</div>
    </div>

#### CSS

    #container {
      height: 200px;
      width: 220px;
      overflow-x: hidden;
      overflow-y: auto;
      scroll-snap-points-y: repeat(200px);
      scroll-snap-type: mandatory;
      font-size: 0;
    }

    #container > div {
      width: 200px;
      height: 200px;
      display: inline-block;
      line-height: 200px;
      text-align: center;
      font-size: 100px;
    }

    #container > div:nth-child(even) {
      background-color: #87EA87;
    }

    #container > div:nth-child(odd) {
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

`scroll-snap-points-y`

No

No

39-68

No

No

9

No

No

39-68

No

9

No

## See also

- [CSS Scroll Snap](css_scroll_snap)
- [Well-Controlled Scrolling with CSS Scroll Snap](https://developers.google.com/web/updates/2018/07/css-scroll-snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-points-y" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/scroll-snap-points-y</a>
