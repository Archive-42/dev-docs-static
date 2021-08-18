Boolean() constructor
=====================

The `Boolean()` constructor is used to create [`Boolean`](../boolean) objects.

Syntax
------

    new Boolean()
    new Boolean(value)

### Parameters

 `value` <span class="badge inline optional">Optional</span>   
The initial value of the `Boolean` object.

Examples
--------

### Creating `Boolean` objects with an initial value of `false`

    var bNoParam = new Boolean();
    var bZero = new Boolean(0);
    var bNull = new Boolean(null);
    var bEmptyString = new Boolean('');
    var bfalse = new Boolean(false);

### Creating `Boolean` objects with an initial value of `true`

    var btrue = new Boolean(true);
    var btrueString = new Boolean('true');
    var bfalseString = new Boolean('false');
    var bSuLin = new Boolean('Su Lin');
    var bArrayProto = new Boolean([]);
    var bObjProto = new Boolean({});

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-boolean-constructor">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-boolean-constructor</span></a></td></tr></tbody></table>

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

`Boolean`

1

12

1

3

4

1

1

18

4

10.1

1

1.0

See also
--------

-   [Boolean](https://developer.mozilla.org/en-US/docs/Glossary/Boolean)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/Boolean" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean/Boolean</a>
