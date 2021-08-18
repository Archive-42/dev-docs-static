TypedArray.from()
=================

The `TypedArray.from()` method creates a new [typed array](../typedarray#typedarray_objects) from an array-like or iterable object. This method is nearly the same as [`Array.from()`](../array/from).

Syntax
------

    // Arrow function
    TypedArray.from(arrayLike, (currentValue) => { ... } )
    TypedArray.from(arrayLike, (currentValue, index) => { ... } )
    TypedArray.from(arrayLike, (currentValue, index, array) => { ... } )

    // Mapping function
    TypedArray.from(arrayLike, mapFn)
    TypedArray.from(arrayLike, mapFn, thisArg)

    // Inline mapping function
    TypedArray.from(arrayLike, function mapFn(currentValue) { ... })
    TypedArray.from(arrayLike, function mapFn(currentValue, index) { ... })
    TypedArray.from(arrayLike, function mapFn(currentValue, index, array){ ... })
    TypedArray.from(arrayLike, function mapFn(currentValue, index, array) { ... }, thisArg)

Where `TypedArray` is one of:

-   [`Int8Array`](../int8array)
-   [`Uint8Array`](../uint8array)
-   [`Uint8ClampedArray`](../uint8clampedarray)
-   [`Int16Array`](../int16array)
-   [`Uint16Array`](../uint16array)
-   [`Int32Array`](../int32array)
-   [`Uint32Array`](../uint32array)
-   [`Float32Array`](../float32array)
-   [`Float64Array`](../float64array)
-   [`BigInt64Array`](../bigint64array)
-   [`BigUint64Array`](../biguint64array)

### Parameters

`arrayLike`  
An array-like or iterable object to convert to a typed array.

 `mapFn` <span class="badge inline optional">Optional</span>   
Map function to call on every element of the typed array.

 `thisArg` <span class="badge inline optional">Optional</span>   
Value to use as `this` when executing `mapFn`.

### Return value

A new [`TypedArray`](../typedarray) instance.

Description
-----------

`TypedArray.from()` lets you create typed arrays from:

-   array-like objects (objects with a `length` property and indexed elements); or
-   [iterable objects](../../iteration_protocols) (objects where you can get its elements, such as [`Map`](../map) and [`Set`](../set)).

`TypedArray.from()` has the optional parameter `mapFn`, which allows you to execute a [`map()`](../array/map) function on each element of the typed array (or subclass object) that is being created. This means that the following are equivalent:

-   `TypedArray.from(obj, mapFn, thisArg)`
-   `TypedArray.from(Array.prototype.map.call(obj, mapFn, thisArg))`.

The `length` property of the `from()` method is `1`.

### Differences from Array.from()

Some subtle distinctions between [`Array.from()`](../array/from) and `TypedArray.from()`:

-   If the `thisArg` value passed to `TypedArray.from()` is not a constructor, `TypedArray.from()` will throw a [`TypeError`](../typeerror), where `Array.from()` defaults to creating a new [`Array`](../array).
-   `TypedArray.from()` uses `[[Put]]` where `Array.from()` uses `[[DefineProperty]]`. Hence, when working with [`Proxy`](../proxy) objects, it calls [`handler.set`](../proxy/proxy/set) to create new elements rather than [`handler.defineProperty()`](../proxy/proxy/defineproperty).
-   When the `source` parameter is an iterator, the `TypedArray.from()` first collects all the values from the iterator, then creates an instance of `thisArg` using the count, then sets the values on the instance. `Array.from()` sets each value as it receives them from the iterator, then sets its `length` at the end.
-   When `Array.from()` gets an array-like which isn't an iterator, it respects holes. `TypedArray.from()` will ensure the result is dense.

Examples
--------

### From an iterable object (Set)

    const s = new Set([1, 2, 3]);
    Uint8Array.from(s);
    // Uint8Array [ 1, 2, 3 ]

### From a string

    Int16Array.from('123');
    // Int16Array [ 1, 2, 3 ]

### Use with arrow function and map

Using an arrow function as the map function to manipulate the elements

    Float32Array.from([1, 2, 3], x => x + x);
    // Float32Array [ 2, 4, 6 ]

### Generate a sequence of numbers

    Uint8Array.from({length: 5}, (v, k) => k);
    // Uint8Array [ 0, 1, 2, 3, 4 ]

Polyfill
--------

You can partially work around this by inserting the following code at the beginning of your scripts, allowing use of much of the functionality of `from()` in implementations that do not natively support it.

    if (!Int8Array.__proto__.from) {
        (function () {
            Int8Array.__proto__.from = function (obj, func, thisObj) {

                var typedArrayClass = Int8Array.__proto__;
                if(typeof this !== 'function') {
                    throw new TypeError('# is not a constructor');
                }
                if (this.__proto__ !== typedArrayClass) {
                    throw new TypeError('this is not a typed array.');
                }

                func = func || function (elem) {
                        return elem;
                    };

                if (typeof func !== 'function') {
                    throw new TypeError('specified argument is not a function');
                }

                obj = Object(obj);
                if (!obj['length']) {
                    return new this(0);
                }
                var copy_data = [];
                for(var i = 0; i < obj.length; i++) {
                    copy_data.push(obj[i]);
                }

                copy_data = copy_data.map(func, thisObj);

                var typed_array = new this(copy_data.length);
                for(var i = 0; i < typed_array.length; i++) {
                    typed_array[i] = copy_data[i];
                }
                return typed_array;
            }
        })();
    }

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="#">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-%typedarray%.from</span></a></td></tr></tbody></table>

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

`from`

45

14

38

No

No

10

No

No

38

No

10

No

See also
--------

-   [`TypedArray.of()`](of)
-   [`Array.from()`](../array/from)
-   [`Array.prototype.map()`](../array/map)

© 2005–2021 MDN contributors.  
Licensed under the Creative Commons Attribution-ShareAlike License v2.5 or later.  
<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/from" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/TypedArray/from</a>
