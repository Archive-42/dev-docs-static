# prefers-reduced-motion

The `prefers-reduced-motion` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](../media_queries/using_media_queries#media_features) is used to detect if the user has requested that the system minimize the amount of non-essential motion it uses.

**Important:** An embedded example at the bottom of this page has a scaling movement that may be problematic for some readers. Readers with vestibular motion disorders may wish to enable the reduce motion feature on their device before viewing the animation.

## Syntax

`no-preference`  
Indicates that the user has made no preference known to the system.

`reduce`  
Indicates that user has notified the system that they prefer an interface that removes or replaces the types of motion-based animation that trigger discomfort for those with vestibular motion disorders.

## User preferences

For Firefox, the `reduce` request is honoured if:

- In GTK/GNOME: GNOME Tweaks &gt; General tab (or Appearance, depending on version) &gt; Animations is turned off.
  - Alternatively, add `gtk-enable-animations = false` to the `[Settings]` block of [the GTK 3 configuration file](https://wiki.archlinux.org/index.php/GTK#Configuration).
- In Plasma/KDE: System Settings &gt; Workspace Behavior -&gt; General Behavior &gt; “Animation speed” is set all the way to right to “Instant”.
- In Windows 10: Settings &gt; Ease of Access &gt; Display &gt; Show animations in Windows.
- In Windows 7: Control Panel &gt; Ease of Access &gt; Make the computer easier to see &gt; Turn off all unnecessary animations (when possible).
- In macOS: System Preferences &gt; Accessibility &gt; Display &gt; Reduce motion.
- In iOS: Settings &gt; General &gt; Accessibility &gt; Reduce Motion.
- In Android 9+: Settings &gt; Accessibility &gt; Remove animations.
- In Firefox `about:config`: Add a number preference called `ui.prefersReducedMotion` and set its value to either `0` for full animation or to `1` to indicate a preference for reduced motion. Changes to this preference take effect immediately.

## Examples

This example has a scaling animation by default. If Reduce Motion is enabled in your accessibility preferences, the animation is toned down to a simple dissolve without vestibular motion triggers.

### HTML

    <div class="animation">animated box</div>

### CSS

    .animation {
      animation: pulse 1s linear infinite both;
    }

    /* Tone down the animation to avoid vestibular motion triggers like scaling or panning large objects. */
    @media (prefers-reduced-motion) {
      .animation {
        animation-name: dissolve;
      }
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/mediaqueries-5/#descdef-media-prefers-reduced-motion">Media Queries Level 5<br />
<span class="small">The definition of 'prefers-reduced-motion' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Initial definition.</td></tr></tbody></table>

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

`prefers-reduced-motion`

74

79

63

No

62

10.1

74

74

64

53

10.3

11.0

## See also

- [An Introduction to the Reduced Motion Media Query (CSS Tricks)](https://css-tricks.com/introduction-reduced-motion-media-query/)
- [Responsive Design for Motion (WebKit Blog)](https://webkit.org/blog/7551/responsive-design-for-motion/) includes vestibular motion trigger examples.

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/@media/prefers-reduced-motion</a>
