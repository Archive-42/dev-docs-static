# appearance (-moz-appearance, -webkit-appearance)

The `appearance` CSS property is used to display an element using platform-native styling, based on the operating system's theme. The `-moz-appearance` and `-webkit-appearance` properties are non-standard versions of this property, used (respectively) by Gecko (Firefox) and by WebKit-based (e.g., Safari) and Blink-based (e.g., Chrome, Opera) browsers to achieve the same thing. Note that Firefox and Edge also support `-webkit-appearance`, for compatibility reasons.

The `-moz-appearance` property was used in [XUL](https://developer.mozilla.org/en-US/docs/Mozilla/Tech/XUL/Tutorial) stylesheets to design custom widgets with platform-appropriate styling. It was also used in the [XBL](https://developer.mozilla.org/en-US/docs/XBL) implementations of the widgets that ship with the Mozilla platform. Starting with Gecko/Firefox 80, these uses were changed to `-moz-default-appearance`, which should never be used outside of internal stylesheets.

**Compatibility note**: If you wish to use this property on websites, you should test it very carefully. Although it is supported in most modern browsers, its implementation varies. In older browsers, even the keyword `none` does not have the same effect on all form elements across different browsers, and some do not support it at all. The differences are smaller in the newest browsers.

## Syntax

    /* CSS Basic User Interface Module Level 4 values */
    appearance: none;
    appearance: auto;
    appearance: menulist-button;
    appearance: textfield;

    /* "Compat-auto" values, which have the same effect as 'auto' */
    appearance: button;
    appearance: searchfield;
    appearance: textarea;
    appearance: push-button;
    appearance: slider-horizontal;
    appearance: checkbox;
    appearance: radio;
    appearance: square-button;
    appearance: menulist;
    appearance: listbox;
    appearance: meter;
    appearance: progress-bar;

    /* Partial list of available values in Gecko */
    -moz-appearance: scrollbarbutton-up;
    -moz-appearance: button-bevel;

    /* Partial list of available values in WebKit/Blink (as well as Gecko and Edge) */
    -webkit-appearance: media-mute-button;
    -webkit-appearance: caret;

### Values

#### Standard keywords

Value

Browser

Description

`none`

Firefox Chrome Safari Edge

No special styling is applied. This is the default.

`auto`

Firefox Chrome

The user agent selects the appropriate special styling based on the element. Acts as `none` on elements with no special styling.

`menulist-button`

Firefox Chrome Safari Edge

The element is styled as a button that would indicate a menulist can be opened.

`textfield`

Firefox Chrome Safari Edge

The following values are treated as equivalent to `auto`:

`button`

Firefox Chrome Safari Edge

The element is drawn like a button.

`checkbox`

Firefox Chrome Safari Edge

The element is drawn like a checkbox, including only the actual "checkbox" portion.

`listbox`

Firefox Chrome Safari Edge

`menulist`

Firefox Chrome Safari Edge

`meter`

Chrome Safari Firefox

`progress-bar`

Chrome Safari Firefox

`push-button`

Chrome Safari Edge

`radio`

Firefox Chrome Safari Edge

The element is drawn like a radio button, including only the actual "radio button" portion.

`searchfield`

Firefox Chrome Safari Edge

`slider-horizontal`

Chrome Safari Edge

`square-button`

Chrome Safari Edge

`textarea`

Firefox Chrome Safari Edge

#### Non-standard keywords

The following values are implemented only for one or both of the prefixed properties, but not on the standard `appearance` property.

<table><thead><tr class="header"><th>Value</th><th>Browser</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>attachment</code></td><td>Safari</td><td></td></tr><tr class="even"><td><code>borderless-attachment</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>button-bevel</code></td><td>Firefox Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>caps-lock-indicator</code></td><td>Safari Edge</td><td></td></tr><tr class="odd"><td><code>caret</code></td><td>Firefox Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>checkbox-container</code></td><td>Firefox</td><td>The element is drawn like a container for a checkbox, which may include a prelighting background effect under certain platforms. Normally it would contain a label and a checkbox.</td></tr><tr class="odd"><td><code>checkbox-label</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>checkmenuitem</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>color-well</code></td><td>Safari</td><td><code>input type=color</code></td></tr><tr class="even"><td><code>continuous-capacity-level-indicator</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>default-button</code></td><td>Safari Edge</td><td></td></tr><tr class="even"><td><code>discrete-capacity-level-indicator</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>inner-spin-button</code></td><td>Firefox Chrome Safari</td><td></td></tr><tr class="even"><td><code>image-controls-button</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>list-button</code></td><td>Safari</td><td>datalist</td></tr><tr class="even"><td><code>listitem</code></td><td>Firefox Chrome Safari Edge</td><td></td></tr><tr class="odd"><td><code>media-enter-fullscreen-button</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-exit-fullscreen-button</code></td><td>Chrome Safari</td><td></td></tr><tr class="odd"><td><code>media-fullscreen-volume-slider</code></td><td>Safari</td><td></td></tr><tr class="even"><td><code>media-fullscreen-volume-slider-thumb</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>media-mute-button</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>media-play-button</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="odd"><td><code>media-overlay-play-button</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-return-to-realtime-button</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>media-rewind-button</code></td><td>Safari</td><td></td></tr><tr class="even"><td><code>media-seek-back-button</code></td><td>Safari Edge</td><td></td></tr><tr class="odd"><td><code>media-seek-forward-button</code></td><td>Safari Edge</td><td></td></tr><tr class="even"><td><code>media-toggle-closed-captions-button</code></td><td>Chrome Safari</td><td></td></tr><tr class="odd"><td><code>media-slider</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>media-sliderthumb</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="odd"><td><code>media-volume-slider-container</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-volume-slider-mute-button</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>media-volume-slider</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-volume-sliderthumb</code></td><td>Chrome Safari</td><td></td></tr><tr class="odd"><td><code>media-controls-background</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-controls-dark-bar-background</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>media-controls-fullscreen-background</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-controls-light-bar-background</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>media-current-time-display</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>media-time-remaining-display</code></td><td>Chrome Safari</td><td></td></tr><tr class="odd"><td><code>menulist-text</code></td><td>Firefox Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>menulist-textfield</code></td><td>Firefox Chrome Safari Edge</td><td>The element is styled as the text field for a menulist. (Not implemented for the Windows platform)</td></tr><tr class="odd"><td><code>meterbar</code></td><td>Firefox</td><td>Use <code>meter</code> instead.</td></tr><tr class="even"><td><code>number-input</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>progress-bar-value</code></td><td>Chrome Safari</td><td></td></tr><tr class="even"><td><code>progressbar</code></td><td>Firefox</td><td>The element is styled like a progress bar. Use <code>progress-bar</code> instead</td></tr><tr class="odd"><td><code>progressbar-vertical</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>range</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>range-thumb</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>rating-level-indicator</code></td><td>Safari</td><td></td></tr><tr class="odd"><td><code>relevancy-level-indicator</code></td><td>Safari</td><td></td></tr><tr class="even"><td><code>scale-horizontal</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>scalethumbend</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>scalethumb-horizontal</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>scalethumbstart</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>scalethumbtick</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>scalethumb-vertical</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>scale-vertical</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>scrollbarthumb-horizontal</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>scrollbarthumb-vertical</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>scrollbartrack-horizontal</code></td><td>Firefox</td><td></td></tr><tr class="even"><td><code>scrollbartrack-vertical</code></td><td>Firefox</td><td></td></tr><tr class="odd"><td><code>searchfield-decoration</code></td><td>Safari Edge</td><td></td></tr><tr class="even"><td><code>searchfield-results-decoration</code></td><td>Chrome Safari Edge</td><td>(Works on Chrome 51 on Windows 7)</td></tr><tr class="odd"><td><code>searchfield-results-button</code></td><td>Safari Edge</td><td></td></tr><tr class="even"><td><code>searchfield-cancel-button</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="odd"><td><code>snapshotted-plugin-overlay</code></td><td>Safari</td><td></td></tr><tr class="even"><td><code>sheet</code></td><td>None</td><td></td></tr><tr class="odd"><td><code>slider-vertical</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>sliderthumb-horizontal</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="odd"><td><code>sliderthumb-vertical</code></td><td>Chrome Safari Edge</td><td></td></tr><tr class="even"><td><code>textfield-multiline</code></td><td>Firefox</td><td>Use <code>textarea</code> instead.</td></tr><tr class="odd"><td><code>-apple-pay-button</code></td><td>Safari</td><td><strong>iOS and macOS only</strong>. Available on the web starting in iOS 10.1 and macOS 10.12.1</td></tr></tbody></table>

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    none | auto | textfield | menulist-button | <compat-auto>where
    <compat-auto> = searchfield | textarea | push-button | slider-horizontal | checkbox | radio | square-button | menulist | listbox | meter | progress-bar | button

## Examples

### Make an element look like a menulist button

    .exampleone {
      appearance: menulist-button;
    }

See also [this JSFiddle](https://jsfiddle.net/go392m5s/) for an example showing how you might use `appearance: none` to apply custom styling to radio buttons and checkboxes.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/css-ui-4/#appearance-switching">CSS Basic User Interface Module Level 4<br />
<span class="small">The definition of 'appearance' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`appearance`

84

1

84

12

80

1

64

62

No

70

15

3

84

1

84

18

80

4

64

62

60

14

1

1.0

`auto`

83

83

80

No

69

No

83

83

80

59

No

13.0

`compat-auto`

83

1

83

12

80

1

No

69

15

3

83

1

83

18

80

4

59

14

1

1.0

`menulist-button`

83

1

83

12

80

1

See [bug 1481615](https://bugzil.la/1481615).

No

69

15

3

83

1

83

18

80

4

See [bug 1481615](https://bugzil.la/1481615).

59

14

1

1.0

`none`

1

12

54

1

Doesn't work with `<input type="checkbox">` and `<input type="radio">`.

No

15

3

1

18

54

4

Doesn't work with `<input type="checkbox">` and `<input type="radio">`.

14

3

1.0

`textfield`

83

1

83

12

80

1

No

69

15

3

83

1

83

18

80

4

59

14

1

1.0

## See also

- [Definition of `appearance` in CSS 3 Basic User Interface](https://www.w3.org/TR/2004/CR-css3-ui-20040511/#appearance) (Candidate Recommendation from 2004-05-11).
- [Dropped CSS3 features from the UI spec.4](https://wiki.csswg.org/spec/css4-ui#dropped-css3-features)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/appearance" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/appearance</a>
