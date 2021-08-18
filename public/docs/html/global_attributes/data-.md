data-\*
=======

The `data-*` [global attributes](../global_attributes) form a class of attributes called **custom data attributes**, that allow proprietary information to be exchanged between the [HTML](../index) and its [DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model) representation by scripts.

All such custom data are available via the [`HTMLElement`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) interface of the element the attribute is set on. The [`HTMLElement.dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset) property gives access to them.  
The `*` may be replaced by any name following [the production rule of XML names](https://www.w3.org/TR/REC-xml/#NT-Name) with the following restrictions:

-   The name must not start with `xml` (case-insensitive).
-   The name must not contain any colon characters (`:`).
-   The name must not contain any capital letters.

Note that the [`HTMLElement.dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset) property is a [`DOMStringMap`](https://developer.mozilla.org/en-US/docs/Web/API/DOMStringMap), and the name of the custom data attribute *data-test-value* will be accessible via `HTMLElement.dataset.testValue` (or by `HTMLElement.dataset["testValue"]`) as any dash (`U+002D`) is replaced by the capitalization of the next letter, converting the name to camelcase.

### Usage

By adding `data-*` attributes, even ordinary HTML elements can become rather complex and powerful program-objects. For example, a space-ship "[sprite](https://en.wikipedia.org/wiki/Sprite_(computer_graphics))*"* in a game could be a simple [`<img>`](../element/img) element with a [`class`](class) attribute and several `data-*` attributes:

    <img class="spaceship cruiserX3" src="shipX3.png"
      data-ship-id="324" data-weapons="laserI laserII" data-shields="72%"
      data-x="414354" data-y="85160" data-z="31940"
      onclick="spaceships[this.dataset.shipId].blasted()">

For a more in-depth tutorial about using HTML data attributes, see [Using data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes).

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#attr-data-*">HTML Living Standard<br />
<span class="small">The definition of 'data-*' in that specification.</span></a></td></tr></tbody></table>

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

`data-*`

Yes

12

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

See also
--------

-   All [global attributes](../global_attributes).
-   The [`HTMLElement.dataset`](https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset) property that allows to access and modify these values.
-   [Using data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

<a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*</a>
