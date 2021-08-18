HTMLOrForeignElement.dataset
============================

The `dataset` read-only property of the [`HTMLOrForeignElement`](../htmlorforeignelement) mixin provides read/write access to [custom data attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) (`data-*`) on elements. It exposes a map of strings ([`DOMStringMap`](../domstringmap)) with an entry for each `data-*` attribute.

The `dataset` property itself can be read, but not directly written. Instead, all writes must be to the individual properties within the `dataset`, which in turn represent the data attributes.

An HTML `data-*` attribute and its corresponding DOM `dataset.property` modify their shared name according to where they are read or written:

In HTML  
The attribute name begins with `data-`. It can contain only letters, numbers, dashes (`-`), periods (`.`), colons (`:`), and underscores (`_`). Any ASCII capital letters (`A` to `Z`) are ignored and converted to lowercase.

In JavaScript  
The property name of a custom data attribute is the same as the HTML attribute without the `data-` prefix, and removes single dashes (`-`) for when to capitalize the property’s “camelCased” name.

In addition to the information below, you'll find a how-to guide for using HTML data attributes in our article [*Using data attributes*.](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)

### Name conversion

 `dash-style` to `camelCase` conversion  
A custom data attribute name is transformed to a key for the [`DOMStringMap`](../domstringmap) entry by the following:

1.  Remove the prefix `data-` (including the dash);
2.  For any dash (`U+002D`) followed by an ASCII lowercase letter `a` to `z`, remove the dash and uppercase the letter;
3.  Other characters (including other dashes) are left unchanged.

 `camelCase` to `dash-style` conversion  
The opposite transformation, which maps a key to an attribute name, uses the following:

1.  **Restriction:** Before transformation, a dash *must not* be immediately followed by an ASCII lowercase letter `a` to `z`;
2.  Add the `data-` prefix;
3.  Add a dash before any ASCII uppercase letter `A` to `Z`, then lowercase the letter;
4.  Other characters are left unchanged.

For example, a `data-abc-def` attribute corresponds to `dataset.abcDef`.

### Accessing values

-   Attributes can be set and read by the camelCase name/key as an object property of the dataset: `element.dataset.keyname`
-   Attributes can also be set and read using bracket syntax: `element.dataset['keyname']`
-   The [`in` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/in) can check if a given attribute exists: `'keyname' in element.dataset`

### Setting values

-   When the attribute is set, its value is always converted to a string.
    **For example:** `element.dataset.example = null` is converted into `data-example="null"`.

-   To remove an attribute, you can use the [`delete` operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/delete): `delete element.dataset.keyname`

Syntax
------

    const dataAttrMap = element.dataset

### Value

A [`DOMStringMap`](../domstringmap).

Examples
--------

    <div id="user" data-id="1234567890" data-user="johndoe" data-date-of-birth>John Doe</div>

    const el = document.querySelector('#user');

    // el.id === 'user'
    // el.dataset.id === '1234567890'
    // el.dataset.user === 'johndoe'
    // el.dataset.dateOfBirth === ''

    // set a data attribute
    el.dataset.dateOfBirth = '1960-10-03';
    // Result: el.dataset.dateOfBirth === '1960-10-03'

    delete el.dataset.dateOfBirth;
    // Result: el.dataset.dateOfBirth === undefined

    if ('someDataAttr' in el.dataset === false) {
      el.dataset.someDataAttr = 'mydata';
      // Result: 'someDataAttr' in el.dataset === true
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/dom.html#dom-dataset">HTML Living Standard<br />
<span class="small">The definition of 'HTMLElement.dataset' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>No change from latest snapshot, <a href="https://www.w3.org/TR/html51/">HTML 5.1</a></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/html51/dom.html#dom-dataset">HTML 5.1<br />
<span class="small">The definition of 'HTMLElement.dataset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, no change from <a href="https://www.w3.org/TR/html52/">HTML5</a></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/html52/dom.html#dom-dataset">HTML5<br />
<span class="small">The definition of 'HTMLElement.dataset' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Snapshot of <a href="https://html.spec.whatwg.org/multipage/">HTML Living Standard</a>, initial definition.</td></tr></tbody></table>

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

`dataset`

8

12

6

11

11

5.1

4.4

18

6

11

5

1.0

See also
--------

-   The HTML [`data-*`](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes/data-*) class of global attributes.
-   [Using data attributes](https://developer.mozilla.org/en-US/docs/Learn/HTML/Howto/Use_data_attributes)
-   [`Element.getAttribute()`](../element/getattribute) and [`Element.setAttribute()`](../element/setattribute)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLOrForeignElement/dataset</a>
