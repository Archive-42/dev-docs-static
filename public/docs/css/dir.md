# :dir()

The `:dir()` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [pseudo-class](pseudo-classes) matches elements based on the directionality of the text contained in them.

    /* Selects any element with right-to-left text */
    :dir(rtl) {
      background-color: red;
    }

The `:dir()` pseudo-class uses only the _semantic_ value of the directionality, i.e., the one defined in the document itself. It doesn't account for _styling_ directionality, i.e., the directionality set by CSS properties such as [`direction`](direction).

**Note:** Be aware that the behavior of the `:dir()` pseudo-class is not equivalent to the `[dir=…]` [attribute selectors](attribute_selectors). The latter match the HTML [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-dir) attribute, and ignore elements that lack it — even if they inherit a direction from their parent. (Similarly, `[dir=rtl]` and `[dir=ltr]` won't match the `auto` value.) In contrast, `:dir()` will match the value calculated by the [user agent](https://developer.mozilla.org/en-US/docs/Glossary/User_agent), even if inherited.

**Note:** In HTML, the direction is determined by the [`dir`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-dir) attribute. Other document types may have different methods.

## Syntax

The `:dir()` pseudo-class requires one parameter, representing the text directionality you want to target.

### Parameters

`ltr`  
Target left-to-right elements.

`rtl`  
Target right-to-left elements.

### Formal syntax

    :dir( [ ltr | rtl ] )

## Examples

### HTML

    <div dir="rtl">
      <span>test1</span>
      <div dir="ltr">test2
        <div dir="auto">עִבְרִית</div>
      </div>
    </div>

### CSS

    :dir(ltr) {
      background-color: yellow;
    }

    :dir(rtl) {
      background-color: powderblue;
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/scripting.html#selector-ltr">HTML Living Standard<br />
<span class="small">The definition of ':dir(ltr)' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No changes.</td></tr><tr class="even"><td><a href="https://drafts.csswg.org/selectors-4/#the-dir-pseudo">Selectors Level 4<br />
<span class="small">The definition of ':dir()' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`:dir`

No

No

49

17-53

No

No

No

No

No

49

17-53

No

No

No

## See also

- Language-related pseudo-classes: [`:lang`](:lang), [`:dir`](:dir)
- HTML [`lang`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-lang) attribute
- HTML [`translate`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#attr-translate) attribute

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/:dir" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/:dir</a>
