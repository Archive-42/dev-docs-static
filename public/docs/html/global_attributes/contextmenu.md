contextmenu
===========

The [contextmenu attribute is obsolete](https://html.spec.whatwg.org/multipage/obsolete.html#attr-contextmenu) and will be removed from all browsers

The `contextmenu` [global attribute](../global_attributes) is the [**id**](id) of a [`<menu>`](../element/menu) to use as the contextual menu for this element.

A *context menu* is a menu that appears upon user interaction, such as a right-click. HTML5 now allows us to customize this menu. Here are some implementation examples, including nested menus.

Example
-------

### HTML

    <body contextmenu="share">
      <menu type="context" id="share">
        <menu label="share">
          <menuitem label="Twitter" onclick="shareViaTwitter()"></menuitem>
          <menuitem label="Facebook" onclick="shareViaFacebook()"></menuitem>
        </menu>
      </menu>
      <ol>
        <li>
          Anywhere in the example you can share the page on Twitter and
          Facebook using the Share menu from your context menu.
        </li>
        <li contextmenu="changeFont" id="fontSizing">
          On this specific list element, you can change the size of the text
          by using the "Increase/Decrease font" actions from your context menu
        </li>
        <menu type="context" id="changeFont">
          <menuitem label="Increase Font" onclick="incFont()"></menuitem>
          <menuitem label="Decrease Font" onclick="decFont()"></menuitem>
        </menu>
        <li contextmenu="ChangeImage" id="changeImage">
          On the image below, you can fire the "Change Image" action
          in your Context Menu.<br />
          <img src="https://developer.mozilla.org/media/img/promote/promobutton_mdn5.png"
              contextmenu="ChangeImage" id="promoButton" />
          <menu type="context" id="ChangeImage">
            <menuitem label="Change Image" onclick="changeImage()"></menuitem>
          </menu>
        </li>
      </ol>
    </body>

### JavaScript

    function shareViaTwitter() {
      window.open("https://twitter.com/intent/tweet?text=" +
          "Hurray! I am learning ContextMenu from MDN via Mozilla");
    }

    function shareViaFacebook() {
      window.open("https://facebook.com/sharer/sharer.php?u=" +
          "https://developer.mozilla.org/en/HTML/Element/Using_HTML_context_menus");
    }

    function incFont() {
      document.getElementById("fontSizing").style.fontSize = "larger";
    }

    function decFont() {
      document.getElementById("fontSizing").style.fontSize = "smaller";
    }

    function changeImage() {
      var index = Math.ceil(Math.random() * 39 + 1);
      document.images[0].src =
          "https://developer.mozilla.org/media/img/promote/promobutton_mdn" +
          index + ".png";
    }

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.w3.org/TR/html51/interactive-elements.html#context-menus">HTML 5.1<br />
<span class="small">The definition of 'contextmenu' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, initial definition.</td></tr></tbody></table>

Browser compatibility
---------------------

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

`contextmenu`

No

No

9

No

No

No

No

No

32-56

Support for the `contextmenu` attribute has been removed from Firefox for Android (See [bug 1424252](https://bugzil.la/1424252)).

No

No

No

\[1\] An experimental implementation was originally available via the command line option `--enable-blink-features=ContextMenu`. Until Chrome 52 and Opera 39 it was additionally available by enabling the *Experimental Web Platform features* option, but got removed from that due to a [Web compatibility issue](https://bugs.chromium.org/p/chromium/issues/detail?id=412945). In June 2017, it was removed entirely from the browsers. This is documented in [Chrome bug 87553](https://bugs.chromium.org/p/chromium/issues/detail?id=87553).

\[2\] Support for the `contextmenu` attribute has been removed from Firefox Mobile ([bug 1424252](https://bugzilla.mozilla.org/show_bug.cgi?id=1424252)).

See also
--------

-   All [global attributes](../global_attributes)
-   [`HTMLElement.contextMenu`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement/contextMenu)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contextmenu" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/contextmenu</a>
