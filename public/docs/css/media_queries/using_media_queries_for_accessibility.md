# Using Media Queries for Accessibility

**Media Queries** can also be used to help users with disabilities understand your website better.

## Reduced Motion

Blinking and flashing animation can be problematic for people with cognitive concerns such as Attention Deficit Hyperactivity Disorder (ADHD). Additionally, certain kinds of motion can be a trigger for Vestibular disorders, epilepsy, and migraine and Scotopic sensitivity.

Also, this method of switching animation off according to the user's preference can also benefit users with low battery or low-end phones or computers.

### Syntax

`no-preference`  
Indicates that the user has made no preference known to the system.

`reduce`  
Indicates that user has notified the system that they prefer an interface that minimizes the amount of movement or animation, preferably to the point where all non-essential movement is removed.

### Example

This example has an annoying animation unless you turn on Reduce Motion in your accessibility preferences.

#### HTML

    <div class="animation">animated box</div>

#### CSS

    .animation {
      -webkit-animation: vibrate 0.3s linear infinite both;
      animation: vibrate 0.3s linear infinite both;
    }

    @media (prefers-reduced-motion: reduce) {
      .animation {
        animation: none;
      }
    }

## High Contrast Mode

**Non-standard**

This feature is non-standard and is not on a standards track. Do not use it on production sites facing the Web: it will not work for every user. There may also be large incompatibilities between implementations and the behavior may change in the future.

The **-ms-high-contrast** [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [media feature](using_media_queries#media_features) is a [Microsoft extension](https://developer.mozilla.org/en-US/docs/Web/CSS/Microsoft_Extensions) that describes whether the application is being displayed in high contrast mode, and with what color variation.

This will help not only users with low vision and contrast sensitivity issues but also users that are working on a computer or phone with direct sunlight.

### Syntax

The `-ms-high-contrast` media feature is specified as one of the following values.

### Values

`active`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with any color variation.

`black-on-white`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with a black-on-white color variation.

`white-on-black`  
Indicates that the subsequent styling rules will be applied when the system is placed in high contrast mode with a white-on-black color variation.

### Example

The following declarations will match applications that are being displayed in high contrast mode with any color variation, a black-on-white color variation, and a white-on-black color variation, respectively.

    @media screen and (-ms-high-contrast: active) {
      /* All high contrast styling rules */
    }
    @media screen and (-ms-high-contrast: black-on-white) {
      div { background-image: url('image-bw.png'); }
    }
    @media screen and (-ms-high-contrast: white-on-black) {
      div { background-image: url('image-wb.png'); }
    }

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_Media_Queries_for_Accessibility" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_Media_Queries_for_Accessibility</a>
