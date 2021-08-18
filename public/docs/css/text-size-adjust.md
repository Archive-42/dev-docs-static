# text-size-adjust

**Experimental**

**This is an [experimental technology](https://developer.mozilla.org/en-US/docs/MDN/Guidelines/Conventions_definitions#experimental)**  
Check the [Browser compatibility table](#browser_compatibility) carefully before using this in production.

The `text-size-adjust` [CSS](https://developer.mozilla.org/en-US/docs/Web/API/CSS) property controls the text inflation algorithm used on some smartphones and tablets. Other browsers will ignore this property.

    /* Keyword values */
    text-size-adjust: none;
    text-size-adjust: auto;

    /* <percentage> value */
    text-size-adjust: 80%;

    /* Global values */
    text-size-adjust: inherit;
    text-size-adjust: initial;
    text-size-adjust: unset;

Because many websites have not been developed with small devices in mind, mobile browsers differ from desktop browsers in the way they render web pages. Instead of laying out pages at the width of the device screen, they lay them out using a [viewport](https://developer.mozilla.org/en-US/docs/Glossary/Viewport) that is much wider, usually 800 or 1000 pixels. To map the extra-wide layout back to the original device size, they either show only part of the whole render or scale the viewport down to fit.

Since text that has been scaled down to fit a mobile screen may be very small, many mobile browsers apply a text inflation algorithm to enlarge the text to make it more readable. When an element containing text uses 100% of the screen's width, the algorithm increases its text size, but without modifying the layout. The `text-size-adjust` property allows web authors to disable or modify this behavior, as web pages designed with small screens in mind do not need it.

## Syntax

The `text-size-adjust` property is specified as `none`, `auto`, or a `<percentage>`.

### Values

`none`  
Disables the browser's inflation algorithm.

`auto`  
Enables the browser's inflation algorithm. This value is used to cancel a `none` value previously set with CSS.

`<percentage>`  
Enables the browser's inflation algorithm, specifying a percentage value with which to increase the font size.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code> for smartphone browsers supporting inflation, <code>none</code> in other cases (and then not modifiable).</td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td>Percentages</td><td>yes, refer to the corresponding size of the text font</td></tr><tr class="odd"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="even"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | auto | <percentage>

## Examples

### Basic disabling usage

As hinted at above, on a properly designed responsive site the `text-size-adjust` behavior is not needed, so developers can elect to turn it off by specifying a value of none:

    p {
      -webkit-text-size-adjust: none;
      text-size-adjust: none;
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-size-adjust/#adjustment-control">CSS Mobile Text Size Adjustment Module Level 1<br />
<span class="small">The definition of 'text-size-adjust' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`text-size-adjust`

54

No

Instead of ignoring the `-webkit-text-size-adjust` property, a bug prevents desktop Chrome users from zooming in or out. The bug was fixed after Chrome 26.

79

12-79

No

No

41

No

No

Instead of ignoring the `-webkit-text-size-adjust` property, a bug prevents desktop Safari users from zooming in or out. The bug was fixed after Safari 5.

54

54

49

14

44

41

1

6.0

`percentages`

54

12

No

No

41

No

54

54

No

41

No

6.0

## See also

- [Apple's documentation](https://developer.apple.com/library/ios/documentation/AppleApplications/Reference/SafariWebContent/AdjustingtheTextSize/AdjustingtheTextSize.html#//apple_ref/doc/uid/TP40006510-SW16)
- [Gecko's behavior description](https://dbaron.org/log/20111126-font-inflation), by L. David Baron
- [Microsoft's documentation](<https://msdn.microsoft.com/library/windows/apps/ff462082(v=vs.105).aspx#BKMK_AdjustingTextSizewithCustomCSS>)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/text-size-adjust</a>
