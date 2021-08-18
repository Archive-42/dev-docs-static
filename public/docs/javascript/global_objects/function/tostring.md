Function.prototype.toString()
=============================

The `toString()` method returns a string representing the source code of the function.

Syntax
------

    toString()

### Return value

A string representing the source code of the function.

Description
-----------

The [`Function`](../function) object overrides the [`toString`](../object/tostring) method inherited from [`Object`](../object); it does not inherit [`Object.prototype.toString`](../object/tostring). For user-defined [`Function`](../function) objects, the `toString` method returns a string containing the source text segment which was used to define the function.

JavaScript calls the `toString` method automatically when a [`Function`](../function) is to be represented as a text value, e.g. when a function is concatenated with a string.

The `toString()` method will throw a [`TypeError`](../typeerror) exception ("Function.prototype.toString called on incompatible object"), if its `this` value object is not a `Function` object.

    Function.prototype.toString.call('foo'); // TypeError

If the `toString()` method is called on built-in function objects or a function created by `Function.prototype.bind`, `toString()` returns a *native function string* which looks like

    "function () {\n    [native code]\n}"

If the `toString()` method is called on a function created by the `Function` constructor, `toString()` returns the source code of a synthesized function declaration named "anonymous" using the provided parameters and function body.

It's also possible to explicitly get the string representation of a function using the `+` operator:

    function foo() { return 'bar' }
    console.log(foo + ''); // "function foo() { return 'bar' }"

Examples
--------

### Comparing actual source code and toString results

<table><colgroup><col style="width: 50%" /><col style="width: 50%" /></colgroup><thead><tr class="header"><th>Function</th><th>Function.prototype.toString result</th></tr></thead><tbody><tr class="odd"><td><pre data-language="js"><code>function f(){}</code></pre></td><td><pre data-language="js"><code>&quot;function f(){}&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>class A { a(){} }</code></pre></td><td><pre data-language="js"><code>&quot;class A { a(){} }&quot;</code></pre></td></tr><tr class="odd"><td><pre data-language="js"><code>function* g(){}</code></pre></td><td><pre data-language="js"><code>&quot;function* g(){}&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>a =&gt; a</code></pre></td><td><pre data-language="js"><code>&quot;a =&gt; a&quot;</code></pre></td></tr><tr class="odd"><td><pre data-language="js"><code>({ a(){} }.a)</code></pre></td><td><pre data-language="js"><code>&quot;a(){}&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>({ *a(){} }.a)</code></pre></td><td><pre data-language="js"><code>&quot;*a(){}&quot;</code></pre></td></tr><tr class="odd"><td><pre data-language="js"><code>({ [0](){} }[0])</code></pre></td><td><pre data-language="js"><code>&quot;[0](){}&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>Object.getOwnPropertyDescriptor({
    get a(){}
}, &quot;a&quot;).get</code></pre></td><td><pre data-language="js"><code>&quot;get a(){}&quot;</code></pre></td></tr><tr class="odd"><td><pre data-language="js"><code>Object.getOwnPropertyDescriptor({
    set a(x){}
}, &quot;a&quot;).set</code></pre></td><td><pre data-language="js"><code>&quot;set a(x){}&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>Function.prototype.toString</code></pre></td><td><pre data-language="js"><code>&quot;function toString() { [native code] }&quot;</code></pre></td></tr><tr class="odd"><td><pre data-language="js"><code>(function f(){}.bind(0))</code></pre></td><td><pre data-language="js"><code>&quot;function () { [native code] }&quot;</code></pre></td></tr><tr class="even"><td><pre data-language="js"><code>Function(&quot;a&quot;, &quot;b&quot;)</code></pre></td><td><pre data-language="js"><code>&quot;function anonymous(a\n) {\nb\n}&quot;</code></pre></td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-function.prototype.tostring">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-function.prototype.tostring</span></a></td></tr></tbody></table>

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

5

3

1

1

18

4

10.1

1

1.0

`toString_revision`

No

No

54

No

No

No

No

No

54

No

No

No

See also
--------

-   [`Object.prototype.toString()`](../object/tostring)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toString" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/toString</a>
