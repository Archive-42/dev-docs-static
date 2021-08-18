Error.prototype.toString()
==========================

The `toString()` method returns a string representing the specified [`Error`](../error) object.

Syntax
------

    toString()

### Return value

A string representing the specified [`Error`](../error) object.

Description
-----------

The [`Error`](../error) object overrides the [`Object.prototype.toString()`](../object/tostring) method inherited by all objects. Its semantics are as follows (assuming [`Object`](../object) and [`String`](../string) have their original values):

    Error.prototype.toString = function() {
      'use strict';

      var obj = Object(this);
      if (obj !== this) {
        throw new TypeError();
      }

      var name = this.name;
      name = (name === undefined) ? 'Error' : String(name);

      var msg = this.message;
      msg = (msg === undefined) ? '' : String(msg);

      if (name === '') {
        return msg;
      }
      if (msg === '') {
        return name;
      }

      return name + ': ' + msg;
    };

Examples
--------

### Using toString()

    var e1 = new Error('fatal error');
    console.log(e1.toString()); // 'Error: fatal error'

    var e2 = new Error('fatal error');
    e2.name = undefined;
    console.log(e2.toString()); // 'Error: fatal error'

    var e3 = new Error('fatal error');
    e3.name = '';
    console.log(e3.toString()); // 'fatal error'

    var e4 = new Error('fatal error');
    e4.name = '';
    e4.message = undefined;
    console.log(e4.toString()); // ''

    var e5 = new Error('fatal error');
    e5.name = 'hello';
    e5.message = undefined;
    console.log(e5.toString()); // 'hello'

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-error.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-error.prototype.tostring</span></a></td></tr></tbody></table>

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

`toString`

1

12

1

6

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

-   [`Error.prototype.toSource()`](tosource)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Error/toString</a>
