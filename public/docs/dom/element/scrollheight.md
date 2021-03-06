# Element.scrollHeight

The `Element.scrollHeight` read-only property is a measurement of the height of an element's content, including content not visible on the screen due to overflow.

The `scrollHeight` value is equal to the minimum height the element would require in order to fit all the content in the viewport without using a vertical scrollbar. The height is measured in the same way as [`clientHeight`](clientheight): it includes the element's padding, but not its border, margin or horizontal scrollbar (if present). It can also include the height of pseudo-elements such as [`::before`](https://developer.mozilla.org/en-US/docs/Web/CSS/::before) or [`::after`](https://developer.mozilla.org/en-US/docs/Web/CSS/::after). If the element's content can fit without a need for vertical scrollbar, its `scrollHeight` is equal to [`clientHeight`](clientheight)

This property will round the value to an integer. If you need a fractional value, use [`Element.getBoundingClientRect()`](getboundingclientrect).

## Syntax

    elemScrollHeight = element.scrollHeight;

### Value

An integer corresponding to the scrollHeight pixel value of the element.

## Example

padding-top

Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.

Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

padding-bottom

**Left** **Top** **Right** **Bottom** _margin-top_ _margin-bottom_ _border-top_ _border-bottom_

<img src="data:image/png;base64,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" width="511" height="413" />

## Problems and solutions

### Determine if an element has been totally scrolled

The following equivalence returns `true` if an element is at the end of its scroll, `false` if it isn't.

    element.scrollHeight - Math.abs(element.scrollTop) === element.clientHeight

When the container does not scroll, but has overflowing children, these checks determine if the container can scroll:

    window.getComputedStyle(element).overflowY === 'visible'
    window.getComputedStyle(element).overflowY !== 'hidden'

## scrollHeight Demo

Associated with the [`onscroll`](../globaleventhandlers/onscroll) event, this equivalence can be useful to determine whether a user has read a text or not (see also the [`element.scrollTop`](scrolltop) and [`element.clientHeight`](clientheight) properties). For example:

### HTML

    <form name="registration">
      <p>
        <textarea id="rules">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Vestibulum at laoreet magna.
    Aliquam erat volutpat. Praesent molestie, dolor ut eleifend aliquam, mi ligula ultrices sapien, quis cursus
    neque dui nec risus. Duis tincidunt lobortis purus eu aliquet. Quisque in dignissim magna. Aenean ac lorem at
    velit ultrices consequat. Nulla luctus nisi ut libero cursus ultrices. Pellentesque nec dignissim enim. Phasellus
    ut quam lacus, sed ultricies diam. Vestibulum convallis rutrum dolor, sit amet egestas velit scelerisque id.
    Proin non dignissim nisl. Sed mi odio, ullamcorper eget mattis id, malesuada vitae libero. Integer dolor lorem,
    mattis sed dapibus a, faucibus id metus. Duis iaculis dictum pulvinar. In nisi nibh, dapibus ac blandit at, porta
    at arcu. Pellentesque habitant morbi tristique senectus et netus et malesuada fames ac turpis egestas. Praesent
    dictum ipsum aliquet erat eleifend sit amet sollicitudin felis tempus. Aliquam congue cursus venenatis. Maecenas
    luctus pellentesque placerat. Mauris nisl odio, condimentum sed fringilla a, consectetur id ligula. Praesent sem
    sem, aliquet non faucibus vitae, iaculis nec elit. Nullam volutpat, lectus et blandit bibendum, nulla lorem congue
    turpis, ac pretium tortor sem ut nibh. Donec vel mi in ligula hendrerit sagittis. Donec faucibus viverra fermentum.
    Fusce in arcu arcu. Nullam at dignissim massa. Cras nibh est, pretium sit amet faucibus eget, sollicitudin in
    ligula. Vivamus vitae urna mauris, eget euismod nunc. Aenean semper gravida enim non feugiat. In hac habitasse
    platea dictumst. Cras eleifend nisl volutpat ante condimentum convallis. Donec varius dolor malesuada erat
    consequat congue. Donec eu lacus ut sapien venenatis tincidunt. Quisque sit amet tellus et enim bibendum varius et
    a orci. Donec aliquet volutpat scelerisque. Proin et tortor dolor. Ut aliquet, dolor a mattis sodales, odio diam
    pulvinar sem, egestas pretium magna eros vitae felis. Nam vitae magna lectus, et ornare elit. Morbi feugiat, ipsum
    ac mattis congue, quam neque mollis tortor, nec mollis nisl dolor a tortor. Maecenas varius est sit amet elit
    interdum quis placerat metus posuere. Duis malesuada justo a diam vestibulum vel aliquam nisi ornare. Integer
    laoreet nisi a odio ornare non congue turpis eleifend. Cum sociis natoque penatibus et magnis dis parturient montes,
    nascetur ridiculus mus. Cras vulputate libero sed arcu iaculis nec lobortis orci fermentum.
        </textarea>
      </p>
      <p>
        <input type="checkbox" id="agree" name="accept" />
        <label for="agree">I agree</label>
        <input type="submit" id="nextstep" value="Next" />
      </p>
    </form>

### CSS

    #notice {
      display: inline-block;
      margin-bottom: 12px;
      border-radius: 5px;
      width: 600px;
      padding: 5px;
      border: 2px #7FDF55 solid;
    }

    #rules {
      width: 600px;
      height: 130px;
      padding: 5px;
      border: #2A9F00 solid 2px;
      border-radius: 5px;
    }

### JavaScript

    function checkReading () {
      if (checkReading.read) {
        return;
      }
      checkReading.read = this.scrollHeight - Math.abs(this.scrollTop) === element.clientHeight;
      document.registration.accept.disabled = document.getElementById("nextstep").disabled = !checkReading.read;
      checkReading.noticeBox.textContent = checkReading.read ? "Thank you." : "Please, scroll and read the following text.";
    }

    onload = function () {
      var oToBeRead = document.getElementById("rules");
      checkReading.noticeBox = document.createElement("span");
      document.registration.accept.checked = false;
      checkReading.noticeBox.id = "notice";
      oToBeRead.parentNode.insertBefore(checkReading.noticeBox, oToBeRead);
      oToBeRead.parentNode.insertBefore(document.createElement("br"), oToBeRead);
      oToBeRead.onscroll = checkReading;
      checkReading.call(oToBeRead);
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.csswg.org/cssom-view/#dom-element-scrollheight">CSS Object Model (CSSOM) View Module<br />
<span class="small">The definition of 'Element.scrollHeight' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Initial definition</td></tr></tbody></table>

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

`scrollHeight`

1

12

21

3-21

In Firefox versions prior to 21, when an element's content does not generate a vertical scrollbar, then its `scrollHeight` property is equal to its `clientHeight` property. This can mean either the content is too short to require a scrollbar or that the element has a CSS style `overflow` value of `visible` (non-scrollable).

5

In Internet Explorer 5 through 7, if padding is set, the value of `scrollHeight` is equal to the sum of the top and bottom padding. This behavior was fixed in Internet Explorer 8.

8

1

1

18

21

4-21

In Firefox versions prior to 21, when an element's content does not generate a vertical scrollbar, then its `scrollHeight` property is equal to its `clientHeight` property. This can mean either the content is too short to require a scrollbar or that the element has a CSS style `overflow` value of `visible` (non-scrollable).

10.1

1

1.0

## See also

- [MSDN: Measuring Element Dimension and Location with CSSOM in Windows Internet Explorer 9](<https://docs.microsoft.com/en-us/previous-versions/hh781509(v=vs.85)>)
- [`Element.clientHeight`](clientheight)
- [`HTMLElement.offsetHeight`](../htmlelement/offsetheight)
- [Determining the dimensions of elements](../css_object_model/determining_the_dimensions_of_elements)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/scrollHeight</a>
