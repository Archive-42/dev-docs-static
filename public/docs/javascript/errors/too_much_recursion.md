InternalError: too much recursion
=================================

The JavaScript exception "too much recursion" or "Maximum call stack size exceeded" occurs when there are too many function calls, or a function is missing a base case.

Message
-------

    Error: Out of stack space (Edge)
    InternalError: too much recursion (Firefox)
    RangeError: Maximum call stack size exceeded (Chrome)

Error type
----------

[`InternalError`](../global_objects/internalerror).

What went wrong?
----------------

A function that calls itself is called a *recursive function*. Once a condition is met, the function stops calling itself. This is called a *base case*.

In some ways, recursion is analogous to a loop. Both execute the same code multiple times, and both require a condition (to avoid an infinite loop, or rather, infinite recursion in this case). When there are too many function calls, or a function is missing a base case, JavaScript will throw this error.

Examples
--------

This recursive function runs 10 times, as per the exit condition.

    function loop(x) {
      if (x >= 10) // "x >= 10" is the exit condition
        return;
      // do stuff
      loop(x + 1); // the recursive call
    }
    loop(0);

Setting this condition to an extremely high value, won't work:

    function loop(x) {
      if (x >= 1000000000000)
        return;
      // do stuff
      loop(x + 1);
    }
    loop(0);

    // InternalError: too much recursion

This recursive function is missing a base case. As there is no exit condition, the function will call itself infinitely.

    function loop(x) {
     // The base case is missing

    loop(x + 1); // Recursive call
    }

    loop(0);

    // InternalError: too much recursion

### Class error: too much recursion

    class Person{
        constructor(){}
        set name(name){
            this.name = name; // Recursive call
        }
    }

    const tony = new Person();
    tony.name = "Tonisha"; // InternalError: too much recursion

When a value is assigned to the property name (this.name = name;) JavaScript needs to set that property. When this happens, the setter function is triggered.

    set name(name){
        this.name = name; // Recursive call
    }

**Note:** In this example when the setter is triggered, it is told to do the same thing again: *to set the same property that it is meant to handle.* This causes the function to call itself, again and again, making it infinitely recursive.

This issue also appears if the same variable is used in the getter.

    get name(){
        return this.name; // Recursive call
    }

To avoid this problem, make sure that the property being assigned to inside the setter function is different from the one that initially triggered the setter.The same goes for the getter.

    class Person{
        constructor(){}
        set name(name){
            this._name = name;
        }
        get name(){
            return this._name;
        }
    }
    const tony = new Person();
    tony.name = "Tonisha";
    console.log(tony);

See also
--------

-   [Recursion](https://developer.mozilla.org/en-US/docs/Glossary/Recursion)
-   [Recursive functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions#recursion)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Too_much_recursion" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Too_much_recursion</a>
