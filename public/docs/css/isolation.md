# isolation

The `isolation` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property determines whether an element must create a new [stacking context](https://developer.mozilla.org/en-US/docs/Glossary/Stacking_context).

This property is especially helpful when used in conjunction with [`mix-blend-mode`](mix-blend-mode) and [`z-index`](z-index).

## Syntax

    /* Keyword values */
    isolation: auto;
    isolation: isolate;

    /* Global values */
    isolation: inherit;
    isolation: initial;
    isolation: unset;

The `isolation` property is specified as one of the keyword values listed below.

### Values

`auto`  
A new stacking context is created only if one of the properties applied to the element requires it.

`isolate`  
A new stacking context must be created.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>All elements. In SVG, it applies to container elements, graphics elements, and graphics referencing elements.</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | isolate

## Examples

### Forcing a new stacking context for an element

#### HTML

    <div id="b" class="a">
      <div id="d">
        <div class="a c">auto</div>
      </div>
      <div id="e">
        <div class="a c">isolate</div>
      </div>
    </div>

#### CSS

    .a {
      background-color: rgb(0,255,0);
    }
    #b {
      width: 200px;
      height: 210px;
    }
    .c {
      width: 100px;
      height: 100px;
      border: 1px solid black;
      padding: 2px;
      mix-blend-mode: difference;
    }
    #d {
      isolation: auto;
    }
    #e {
      isolation: isolate;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/compositing-1/#isolation">Compositing and Blending Level 1<br />
<span class="small">The definition of 'Isolation' in that specification.</span></a></td><td><span class="spec-cr">Candidate Recommendation</span></td><td>Initial definition</td></tr></tbody></table>

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

`isolation`

41

79

36

No

30

8

41

41

36

30

8

4.0

## See also

- [`<blend-mode>`](blend-mode)
- [`mix-blend-mode`](mix-blend-mode), [`background-blend-mode`](background-blend-mode)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/isolation" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/isolation</a>
