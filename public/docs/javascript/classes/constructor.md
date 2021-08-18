constructor
===========

The `constructor` method is a special method of a [`class`](../statements/class) for creating and initializing an object of that class.

Syntax
------

    constructor() { ... }
    constructor(argument0) { ... }
    constructor(argument0, argument1) { ... }
    constructor(argument0, argument1, ... , argumentN) { ... }

Description
-----------

A constructor enables you to provide any custom initialization that must be done before any other methods can be called on an instantiated object.

    class Person {

      constructor(name) {
        this.name = name;
      }

      introduce() {
        console.log(`Hello, my name is ${this.name}`);
      }

    }

    const otto = new Person('Otto');

    otto.introduce();

If you don't provide your own constructor, then a default constructor will be supplied for you. If your class is a base class, the default constructor is empty:

    constructor() {}

If your class is a derived class, the default constructor calls the parent constructor, passing along any arguments that were provided:

    constructor(...args) {
      super(...args);
    }

That enables code like this to work:

    class ValidationError extends Error {

      printCustomerMessage() {
        return `Validation failed :-( (details: ${this.message})`;
      }

    }

    try {
      throw new ValidationError("Not a valid phone number");
    } catch (error) {
       if (error instanceof ValidationError) {
        console.log(error.name); // This is Error instead of ValidationError!
        console.log(error.printCustomerMessage());
      } else {
        console.log('Unknown error', error);
        throw error;
      }
    }

The `ValidationError` class doesn't need an explicit constructor, because it doesn't need to do any custom initialization. The default constructor then takes care of initializing the parent `Error` from the argument it is given.

However, if you provide your own constructor, and your class derives from some parent class, then you must explicitly call the parent class constructor using `super`. For example:

    class ValidationError extends Error {

      constructor(message) {
        super(message);  // call parent class constructor
        this.name = 'ValidationError';
        this.code = '42';
      }

      printCustomerMessage() {
         return `Validation failed :-( (details: ${this.message}, code: ${this.code})`;
      }

    }

    try {
      throw new ValidationError("Not a valid phone number");
    } catch (error) {
       if (error instanceof ValidationError) {
        console.log(error.name); // Now this is ValidationError!
        console.log(error.printCustomerMessage());
      } else {
        console.log('Unknown error', error);
        throw error;
      }
    }

There can be only one special method with the name "`constructor`" in a class. Having more than one occurrence of a `constructor` method in a class will throw a [`SyntaxError`](../global_objects/syntaxerror) error.

Examples
--------

### Using the `constructor` method

This code snippet is taken from the [classes sample](https://github.com/GoogleChrome/samples/blob/gh-pages/classes-es6/index.html) ([live demo](https://googlechrome.github.io/samples/classes-es6/index.html)).

    class Square extends Polygon {
      constructor(length) {
        // Here, it calls the parent class' constructor with lengths
        // provided for the Polygon's width and height
        super(length, length);
        // NOTE: In derived classes, `super()` must be called before you
        // can use `this`. Leaving this out will cause a ReferenceError.
        this.name = 'Square';
      }

      get area() {
        return this.height * this.width;
      }

      set area(value) {
        this.height = value**0.5;
        this.width = value**0.5;
      }
    }

### Another example

Here the prototype of `Square` class is changed—but the constructor of its base class `Polygon` is still called when a new instance of a square is created.

    class Polygon {
        constructor() {
            this.name = "Polygon";
        }
    }

    class Square extends Polygon {
        constructor() {
            super();
        }
    }

    class Rectangle {}

    Object.setPrototypeOf(Square.prototype, Rectangle.prototype);

    console.log(Object.getPrototypeOf(Square.prototype) === Polygon.prototype); //false
    console.log(Object.getPrototypeOf(Square.prototype) === Rectangle.prototype); //true

    let newInstance = new Square();
    console.log(newInstance.name); //Polygon

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th></tr></thead><tbody><tr class="odd"><td><a href="https://tc39.es/ecma262/#sec-static-semantics-constructormethod">ECMAScript Language Specification (ECMAScript)<br />
<span class="small">#sec-static-semantics-constructormethod</span></a></td></tr></tbody></table>

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

`constructor`

49

42-49

Strict mode is required.

42-49

13

45

No

36

29-36

Strict mode is required.

29-36

9

49

42-49

Strict mode is required.

49

42-49

Strict mode is required.

42-49

45

36

29-36

Strict mode is required.

29-36

9

5.0

4.0-5.0

Strict mode is required.

See also
--------

-   [`super()`](../operators/super)
-   [class declaration](../statements/class)
-   [class expression](../operators/class)
-   [`Classes`](../classes)
-   [Object.prototype.constructor](../global_objects/object/constructor)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes/constructor</a>
