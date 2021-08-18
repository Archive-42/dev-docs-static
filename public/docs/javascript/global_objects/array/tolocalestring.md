Array.prototype.toLocaleString()
================================

The `toLocaleString()` method returns a string representing the elements of the array. The elements are converted to Strings using their `toLocaleString` methods and these Strings are separated by a locale-specific String (such as a comma “,”).

Syntax
------

    toLocaleString();
    toLocaleString(locales);
    toLocaleString(locales, options);

### Parameters

 `locales` <span class="badge inline optional">Optional</span>   
A string with a BCP 47 language tag, or an array of such strings. For the general form and interpretation of the `locales` argument, see the [`Intl`](../intl) page.

 `options` <span class="badge inline optional">Optional</span>   
An object with configuration properties, for numbers see [`Number.prototype.toLocaleString()`](../number/tolocalestring), and for dates see [`Date.prototype.toLocaleString()`](../date/tolocalestring).

### Return value

A string representing the elements of the array.

Polyfill
--------

    // https://tc39.github.io/ecma402/#sup-array.prototype.tolocalestring
    if (!Array.prototype.toLocaleString) {
      Object.defineProperty(Array.prototype, 'toLocaleString', {
        value: function(locales, options) {
          // 1. Let O be ? ToObject(this value).
          if (this == null) {
            throw new TypeError('"this" is null or not defined');
          }

          var a = Object(this);

          // 2. Let len be ? ToLength(? Get(A, "length")).
          var len = a.length >>> 0;

          // 3. Let separator be the String value for the
          //    list-separator String appropriate for the
          //    host environment's current locale (this is
          //    derived in an implementation-defined way).
          // NOTE: In this case, we will use a comma
          var separator = ',';

          // 4. If len is zero, return the empty String.
          if (len === 0) {
            return '';
          }

          // 5. Let firstElement be ? Get(A, "0").
          var firstElement = a[0];
          // 6. If firstElement is undefined or null, then
          //  a.Let R be the empty String.
          // 7. Else,
          //  a. Let R be ?
          //     ToString(?
          //       Invoke(
          //        firstElement,
          //        "toLocaleString",
          //        « locales, options »
          //       )
          //     )
          var r = firstElement == null ?
            '' : firstElement.toLocaleString(locales, options);

          // 8. Let k be 1.
          var k = 1;

          // 9. Repeat, while k < len
          while (k < len) {
            // a. Let S be a String value produced by
            //   concatenating R and separator.
            var s = r + separator;

            // b. Let nextElement be ? Get(A, ToString(k)).
            var nextElement = a[k];

            // c. If nextElement is undefined or null, then
            //   i. Let R be the empty String.
            // d. Else,
            //   i. Let R be ?
            //     ToString(?
            //       Invoke(
            //        nextElement,
            //        "toLocaleString",
            //        « locales, options »
            //       )
            //     )
            r = nextElement == null ?
              '' : nextElement.toLocaleString(locales, options);

            // e. Let R be a String value produced by
            //   concatenating S and R.
            r = s + r;

            // f. Increase k by 1.
            k++;
          }

          // 10. Return R.
          return r;
        }
      });
    }

If you need to support truly obsolete JavaScript engines that don't support `Object.defineProperty`, it's best not to polyfill `Array.prototype` methods at all, as you can't make them non-enumerable.

Examples
--------

### Using locales and options

The elements of the array are converted to strings using their `toLocaleString` methods.

-   `Object`: [`Object.prototype.toLocaleString()`](../object/tolocalestring)
-   `Number`: [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   `Date`: [`Date.prototype.toLocaleString()`](../date/tolocalestring)

Always display the currency for the strings and numbers in the `prices` array:

    var prices = ['￥7', 500, 8123, 12];
    prices.toLocaleString('ja-JP', { style: 'currency', currency: 'JPY' });

    // "￥7,￥500,￥8,123,￥12"

For more examples, see also the [`Intl`](../intl), [`NumberFormat`](../intl/numberformat), and [`DateTimeFormat`](../intl/datetimeformat) pages.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-array.prototype.tolocalestring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-array.prototype.tolocalestring</span></a></td></tr><tr class="even"><td><a href="https://tc39.es/ecma402/#sup-array.prototype.tolocalestring">ECMAScript Internationalization API Specification (ECMAScript Internationalization API)<br />
<span class="small">#sup-array.prototype.tolocalestring</span></a></td></tr></tbody></table>

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

`toLocaleString`

1

12

1

5.5

4

1

≤37

18

4

10.1

1

1.0

`locales`

24

79

52

No

15

6.1

≤37

25

56

14

6.1

2.0

`options`

24

79

52

No

15

6.1

≤37

25

56

14

6.1

2.0

See also
--------

-   [`Array.prototype.toString()`](tostring)
-   [`Intl`](../intl)
-   [`Object.prototype.toLocaleString()`](../object/tolocalestring)
-   [`Number.prototype.toLocaleString()`](../number/tolocalestring)
-   [`Date.prototype.toLocaleString()`](../date/tolocalestring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toLocaleString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/toLocaleString</a>
