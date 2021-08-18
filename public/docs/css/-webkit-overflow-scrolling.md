# -webkit-overflow-scrolling

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The `-webkit-overflow-scrolling` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) property controls whether or not touch devices use momentum-based scrolling for a given element.

## Syntax

### Values

`auto`  
Use "regular" scrolling, where the content immediately ceases to scroll when you remove your finger from the touchscreen.

`touch`  
Use momentum-based scrolling, where the content continues to scroll for a while after finishing the scroll gesture and removing your finger from the touchscreen. The speed and duration of the continued scrolling is proportional to how vigorous the scroll gesture was. Also creates a new stacking context.

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>scrolling boxes</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>yes</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | touch

## Examples

### HTML

    <div class="scroll-touch">
      <p>
        This paragraph has momentum scrolling
      </p>
    </div>
    <div class="scroll-auto">
      <p>
        This paragraph does not.
      </p>
    </div>

### CSS

    div {
      width: 100%;
      overflow: auto;
    }

    p {
      width: 200%;
      background: #f5f9fa;
      border: 2px solid #eaf2f4;
      padding: 10px;
    }

    .scroll-touch {
      -webkit-overflow-scrolling: touch; /* Lets it scroll lazy */
    }

    .scroll-auto {
      -webkit-overflow-scrolling: auto; /* Stops scrolling immediately */
    }

### Results

## Specifications

Not part of any standard. Apple has [a description in the Safari CSS Reference](https://developer.apple.com/library/safari/documentation/AppleApplications/Reference/SafariCSSRef/Articles/StandardCSSProperties.html#//apple_ref/css/property/-webkit-overflow-scrolling).

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

`-webkit-overflow-scrolling`

No

No

No

No

No

No

No

No

No

No

5

No

## See also

- [CSS-Tricks article with demo](https://css-tricks.com/snippets/css/momentum-scrolling-on-ios-overflow-elements/)
- [Smashing Magazine - describing the effect of scroll bouncing and how it works on different web browsers](https://www.smashingmagazine.com/2018/08/scroll-bouncing-websites/)
- [Safari 13 Release notes](https://developer.apple.com/documentation/safari_release_notes/safari_13_release_notes): Indicates the addition of support for one-finger accelerated scrolling to all frames and `overflow:scroll` elements, eliminating the need to set `-webkit-overflow-scrolling: touch`.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-overflow-scrolling" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/-webkit-overflow-scrolling</a>
