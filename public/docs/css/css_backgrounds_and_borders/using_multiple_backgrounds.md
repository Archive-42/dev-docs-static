# Using multiple backgrounds

You can apply **multiple backgrounds** to elements. These are layered atop one another with the first background you provide on top and the last background listed in the back. Only the last background can include a background color.

Specifying multiple backgrounds is easy:

    .myclass {
      background: background1, background 2, ..., backgroundN;
    }

You can do this with both the shorthand [`background`](../background) property and the individual properties thereof except for [`background-color`](../background-color). That is, the following background properties can be specified as a list, one per background: [`background`](../background), [`background-attachment`](../background-attachment), [`background-clip`](../background-clip), [`background-image`](../background-image), [`background-origin`](../background-origin), [`background-position`](../background-position), [`background-repeat`](../background-repeat), [`background-size`](../background-size).

## Example

In this example, three backgrounds are stacked: the Firefox logo, an image of bubbles, and a [linear gradient](<../linear-gradient()>):

### HTML

    <div class="multi-bg-example"></div>

### CSS

    .multi-bg-example {
      width: 100%;
      height: 400px;
      background-image: url(https://mdn.mozillademos.org/files/11305/firefox.png),
          url(https://mdn.mozillademos.org/files/11307/bubbles.png),
          linear-gradient(to right, rgba(30, 75, 115, 1), rgba(255, 255, 255, 0));
      background-repeat: no-repeat,
          no-repeat,
          no-repeat;
      background-position: bottom right,
          left,
          right;
    }

### Result

(If image does not appear in CodePen, click the 'Tidy' button in the CSS section)

As you can see here, the Firefox logo (listed first within [`background-image`](../background-image)) is on top, directly above the bubbles graphic, followed by the gradient (listed last) sitting underneath all previous 'images'. Each subsequent sub-property ([`background-repeat`](../background-repeat) and [`background-position`](../background-position)) applies to the corresponding backgrounds. So the first listed value for [`background-repeat`](../background-repeat) applies to the first (frontmost) background, and so forth.

## See also

- [Using CSS gradients](../css_images/using_css_gradients)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders/Using_multiple_backgrounds" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Backgrounds_and_Borders/Using_multiple_backgrounds</a>
