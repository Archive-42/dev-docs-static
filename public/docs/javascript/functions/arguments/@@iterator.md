arguments\[@@iterator\]()
=========================

The initial value of the `@@iterator` property is the same function object as the initial value of the [`Array.prototype.values`](../../global_objects/array/values) property.

Syntax
------

    arguments[Symbol.iterator]()

Examples
--------

### Iteration using for...of loop

    function f() {
      // your browser must support for..of loop
      // and let-scoped variables in for loops
      for (let letter of arguments) {
        console.log(letter);
      }
    }
    f('w', 'y', 'k', 'o', 'p');

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-createunmappedargumentsobject">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-createunmappedargumentsobject</span></a></td></tr><tr class="even"><td><a href="https://tc39.es/ecma262/#sec-createmappedargumentsobject">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-createmappedargumentsobject</span></a></td></tr></tbody></table>

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

`@@iterator`

52

12

46

No

39

9

52

52

46

41

9

6.0

See also
--------

-   [`Array.prototype.values()`](../../global_objects/array/values)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/@@iterator" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/arguments/@@iterator</a>
