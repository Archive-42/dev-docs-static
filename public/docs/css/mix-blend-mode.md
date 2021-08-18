# mix-blend-mode

The `mix-blend-mode` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets how an element's content should blend with the content of the element's parent and the element's background.

## Syntax

    /* Keyword values */
    mix-blend-mode: normal;
    mix-blend-mode: multiply;
    mix-blend-mode: screen;
    mix-blend-mode: overlay;
    mix-blend-mode: darken;
    mix-blend-mode: lighten;
    mix-blend-mode: color-dodge;
    mix-blend-mode: color-burn;
    mix-blend-mode: hard-light;
    mix-blend-mode: soft-light;
    mix-blend-mode: difference;
    mix-blend-mode: exclusion;
    mix-blend-mode: hue;
    mix-blend-mode: saturation;
    mix-blend-mode: color;
    mix-blend-mode: luminosity;

    /* Global values */
    mix-blend-mode: initial;
    mix-blend-mode: inherit;
    mix-blend-mode: unset;

### Values

[`<blend-mode>`](blend-mode)  
The blending mode that should be applied.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>normal</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    <blend-mode>where
    <blend-mode> = normal | multiply | screen | overlay | darken | lighten | color-dodge | color-burn | hard-light | soft-light | difference | exclusion | hue | saturation | color | luminosity

## Examples

### Effect of different mix-blend-mode values

### Using mix-blend-mode with HTML

#### HTML

    <div class="isolate">
      <div class="circle circle-1"></div>
      <div class="circle circle-2"></div>
      <div class="circle circle-3"></div>
    </div>

#### CSS

    .circle {
      width: 80px;
      height: 80px;
      border-radius: 50%;
      mix-blend-mode: screen;
      position: absolute;
    }

    .circle-1 {
      background: red;
    }

    .circle-2 {
      background: lightgreen;
      left: 40px;
    }

    .circle-3 {
      background: blue;
      left: 20px;
      top: 40px;
    }

    .isolate {
      isolation: isolate; /* Without isolation, the background color will be taken into account */
      position: relative;
    }

#### Result

### Using mix-blend-mode with SVG

#### SVG

    <svg>
      <g class="isolate">
        <circle cx="40" cy="40" r="40" fill="red"/>
        <circle cx="80" cy="40" r="40" fill="lightgreen"/>
        <circle cx="60" cy="80" r="40" fill="blue"/>
      </g>
    </svg>

#### CSS

    circle { mix-blend-mode: screen; }
    .isolate { isolation: isolate; } /* Without isolation, the background color will be taken into account */

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/compositing-1/#mix-blend-mode">Compositing and Blending Level 1<br />
<span class="small">The definition of 'mix-blend-mode' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`mix-blend-mode`

41

79

32

No

28

8

41

41

32

28

8

4.0

`svg`

41

79

32

No

28

No

No

No

32

No

No

No

## See also

- [`<blend-mode>`](blend-mode)
- [`background-blend-mode`](background-blend-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/mix-blend-mode</a>
