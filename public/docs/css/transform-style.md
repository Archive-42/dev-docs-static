# transform-style

The `transform-style` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property sets whether children of an element are positioned in the 3D space or are flattened in the plane of the element.

If flattened, the element's children will not exist on their own in the 3D-space.

As this property is not inherited, it must be set for all non-leaf descendants of the element.

## Syntax

    /* Keyword values */
    transform-style: flat;
    transform-style: preserve-3d;

    /* Global values */
    transform-style: inherit;
    transform-style: initial;
    transform-style: unset;

### Values

`flat`  
Indicates that the children of the element are lying in the plane of the element itself.

`preserve-3d`  
Indicates that the children of the element should be positioned in the 3D-space.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>flat</code></td></tr><tr class="even"><td>Applies to</td><td>transformable elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr><tr class="even"><td>Creates <a href="css_positioning/understanding_z_index/the_stacking_context">stacking context</a></td><td>yes</td></tr></tbody></table>

## Formal syntax

    flat | preserve-3d

## Examples

### Transform style demonstration

In this example we have a 3D cube created using transforms. The parent container of the cube faces has `transform-style: preserve-3d` set on it by default, so it is transformed in the 3D space and you can see it as intended.

We also provide a checkbox allowing you to toggle between this, and `transform-style: flat`. In this alternative state, the cube faces are all flattened onto the plane of their parent, and you might not be able to see them at all, depending on the browser you are using.

#### HTML

    <section id="example-element">
      <div class="face front">1</div>
      <div class="face back">2</div>
      <div class="face right">3</div>
      <div class="face left">4</div>
      <div class="face top">5</div>
      <div class="face bottom">6</div>
    </section>

    <div class="checkbox">
      <label for="preserve"><code>preserve-3d</code></label>
      <input type="checkbox" id="preserve" checked>
    </div>

#### CSS

    #example-element {
      margin: 50px;
      width: 100px;
      height: 100px;
      transform-style: preserve-3d;
      transform: rotate3d(1, 1, 1, 30deg);
    }

    .face {
      display: flex;
      align-items: center;
      justify-content: center;
      width: 100%;
      height: 100%;
      position: absolute;
      backface-visibility: inherit;
      font-size: 60px;
      color: #fff;
    }

    .front {
        background: rgba(90,90,90,.7);
        transform: translateZ(50px);
    }

    .back {
        background: rgba(0,210,0,.7);
        transform: rotateY(180deg) translateZ(50px);
    }

    .right {
      background: rgba(210,0,0,.7);
      transform: rotateY(90deg) translateZ(50px);
    }

    .left {
      background: rgba(0,0,210,.7);
      transform: rotateY(-90deg) translateZ(50px);
    }

    .top {
      background: rgba(210,210,0,.7);
      transform: rotateX(90deg) translateZ(50px);
    }

    .bottom {
      background: rgba(210,0,210,.7);
      transform: rotateX(-90deg) translateZ(50px);
    }

#### JavaScript

    const cube = document.getElementById('example-element');
    const checkbox = document.getElementById('preserve');

    checkbox.addEventListener('change', () => {
      if(checkbox.checked) {
        cube.style.transformStyle = 'preserve-3d';
      } else {
        cube.style.transformStyle = 'flat';
      }
    })

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-transforms-2/#transform-style-property">CSS Transforms Level 2<br />
<span class="small">The definition of 'transform-style' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`transform-style`

36

12

12

12

16

10

49

44

No

23

15

9

4

37

3

36

18

16

10

49

44

24

14

9

2

3.0

1.0

## See also

- [Using CSS transforms](css_transforms/using_css_transforms)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/transform-style</a>
