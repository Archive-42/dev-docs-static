# touch-action

The `touch-action` CSS property sets how an element's region can be manipulated by a touchscreen user (for example, by zooming features built into the browser).

    /* Keyword values */
    touch-action: auto;
    touch-action: none;
    touch-action: pan-x;
    touch-action: pan-left;
    touch-action: pan-right;
    touch-action: pan-y;
    touch-action: pan-up;
    touch-action: pan-down;
    touch-action: pinch-zoom;
    touch-action: manipulation;

    /* Global values */
    touch-action: inherit;
    touch-action: initial;
    touch-action: unset;

By default, panning (scrolling) and pinching gestures are handled exclusively by the browser. An application using [Pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events) will receive a [`pointercancel`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointercancel_event) event when the browser starts handling a touch gesture. By explicitly specifying which gestures should be handled by the browser, an application can supply its own behavior in [`pointermove`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointermove_event) and [`pointerup`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/pointerup_event) listeners for the remaining gestures. Applications using [Touch events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events) disable the browser handling of gestures by calling [`preventDefault()`](https://developer.mozilla.org/en-US/docs/Web/API/Event/preventDefault), but should also use `touch-action` to ensure the browser knows the intent of the application before any event listeners have been invoked.

When a gesture is started, the browser intersects the `touch-action` values of the touched element and its ancestors, up to the one that implements the gesture (in other words, the first containing scrolling element). This means that in practice, `touch-action` is typically applied only to top-level elements which have some custom behavior, without needing to specify `touch-action` explicitly on any of that element's descendants.

After a gesture starts, changes to `touch-action` will not have any impact on the behavior of the current gesture.

## Syntax

The `touch-action` property may be specified as either:

- One of the keywords `auto`, `none`, `manipulation`, _or_
- One of the keywords `pan-x`, `pan-left`, `pan-right`, and/or one of the keywords `pan-y`, `pan-up`, `pan-down`, plus optionally the keyword `pinch-zoom`.

### Values

`auto`  
Enable browser handling of all panning and zooming gestures.

`none`  
Disable browser handling of all panning and zooming gestures.

`pan-x`  
Enable single-finger horizontal panning gestures. May be combined with **pan-y**, **pan-up**, **pan-down** and/or **pinch-zoom**.

`pan-y`  
Enable single-finger vertical panning gestures. May be combined with **pan-x**, **pan-left**, **pan-right** and/or **pinch-zoom**.

`manipulation`  
Enable panning and pinch zoom gestures, but disable additional non-standard gestures such as double-tap to zoom. Disabling double-tap to zoom removes the need for browsers to delay the generation of **click** events when the user taps the screen. This is an alias for "**pan-x pan-y pinch-zoom**" (which, for compatibility, is itself still valid).

`pan-left`, `pan-right`, `pan-up`, `pan-down` <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>  
Enable single-finger gestures that begin by scrolling in the given direction(s). Once scrolling has started, the direction may still be reversed. Note that scrolling "up" (**pan-up**) means that the user is dragging their finger downward on the screen surface, and likewise **pan-left** means the user is dragging their finger to the right. Multiple directions may be combined except when there is a simpler representation (for example, **"pan-left pan-right**" is invalid since "**pan-x**" is simpler, but "**pan-left pan-down**" is valid).

`pinch-zoom`  
Enable multi-finger panning and zooming of the page. This may be combined with any of the **pan-** values.

## Accessibility concerns

A declaration of `touch-action: none;` may inhibit operating a browser's zooming capabilities. This will prevent people experiencing low vision conditions from being able to read and understand page content.

- [MDN Understanding WCAG, Guideline 1.4 explanations](https://developer.mozilla.org/en-US/docs/Web/Accessibility/Understanding_WCAG/Perceivable#guideline_1.4_make_it_easier_for_users_to_see_and_hear_content_including_separating_foreground_from_background)
- [Understanding Success Criterion 1.4.4 | Understanding WCAG 2.0](https://www.w3.org/TR/UNDERSTANDING-WCAG20/visual-audio-contrast-scale.html)

## Formal definition

<table><tbody><tr class="odd"><td><a href="initial_value">Initial value</a></td><td><code>auto</code></td></tr><tr class="even"><td>Applies to</td><td>all elements except: non-replaced inline elements, table rows, row groups, table columns, and column groups</td></tr><tr class="odd"><td><a href="inheritance">Inherited</a></td><td>no</td></tr><tr class="even"><td><a href="computed_value">Computed value</a></td><td>as specified</td></tr><tr class="odd"><td>Animation type</td><td>discrete</td></tr></tbody></table>

## Formal syntax

    auto | none | [ [ pan-x | pan-left | pan-right ] || [ pan-y | pan-up | pan-down ] || pinch-zoom ] | manipulation

## Examples

### Disabling all gestures

The most common usage is to disable all gestures on an element (and its non-scrollable descendants) that provides its own dragging and zooming behavior – such as a map or game surface.

#### HTML

    <div id="map"></div>

#### CSS

    #map {
      height: 150vh;
      width: 70vw;
      background: linear-gradient(blue, green);
      touch-action: none;
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://compat.spec.whatwg.org/#touch-action">Compatibility Standard<br />
<span class="small">The definition of 'touch-action' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Added <code>pinch-zoom</code> property value.</td></tr><tr class="even"><td><a href="https://w3c.github.io/pointerevents/#the-touch-action-css-property">Pointer Events – Level 3<br />
<span class="small">The definition of 'touch-action' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Added <code>pan-left</code>, <code>pan-right</code>, <code>pan-up</code>, <code>pan-down</code> property values.</td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/pointerevents2/#the-touch-action-css-property">Pointer Events – Level 2<br />
<span class="small">The definition of 'touch-action' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Latest recommendation.</td></tr><tr class="even"><td><a href="https://www.w3.org/TR/pointerevents1/#the-touch-action-css-property">Pointer Events<br />
<span class="small">The definition of 'touch-action' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition.</td></tr></tbody></table>

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

`touch-action`

36

12

52

Not applicable to Firefox platforms that support neither pointer nor touch events.

29

Not applicable to Firefox platforms that support neither pointer nor touch events.

11

10

23

13

37

36

52

29

24

9.3

3.0

`axis-pan`

36

12

52

Not applicable to Firefox platforms that support neither pointer nor touch events.

29

Not applicable to Firefox platforms that support neither pointer nor touch events.

11

10

23

13

37

36

52

29

24

13

3.0

`double-tap-zoom`

No

12-79

No

11

10

No

No

No

No

No

No

No

No

`manipulation`

36

12

52

Not applicable to Firefox platforms that support neither pointer nor touch events.

29

Not applicable to Firefox platforms that support neither pointer nor touch events.

11

10

23

13

37

36

52

29

24

9.3

3.0

`none`

36

12

52

Not applicable to Firefox platforms that support neither pointer nor touch events.

29

Not applicable to Firefox platforms that support neither pointer nor touch events.

11

10

23

13

37

36

52

29

24

13

3.0

`pinch-zoom`

56

12

85

Not applicable to Firefox platforms that support neither pointer nor touch events.

11

10

43

13

56

56

85

Not applicable to Firefox platforms that support neither pointer nor touch events.

43

13

6.0

`unidirectional-pan`

55

79

No

See [bug 1285685](https://bugzil.la/1285685).

No

42

No

55

55

No

See [bug 1285685](https://bugzil.la/1285685).

42

No

6.0

## See also

- <span class="page-not-created">`pointer-events`</span>
- [`Pointer Events`](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)
- WebKit Blog [More Responsive Tapping on iOS](https://webkit.org/blog/5610/more-responsive-tapping-on-ios/)
- Google Developers Blog [Making touch scrolling fast by default](https://developers.google.com/web/updates/2017/01/scrolling-intervention)
- [Scroll Snap](css_scroll_snap)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/touch-action</a>
