SyntaxError: applying the 'delete' operator to an unqualified name is deprecated
================================================================================

The JavaScript [strict mode](../strict_mode)-only exception "applying the 'delete' operator to an unqualified name is deprecated" occurs when variables are attempted to be deleted using the `delete` operator.

Message
-------

    SyntaxError: Calling delete on expression not allowed in strict mode (Edge)
    SyntaxError: applying the 'delete' operator to an unqualified name is deprecated (Firefox)
    SyntaxError: Delete of an unqualified identifier in strict mode. (Chrome)

Error type
----------

[`SyntaxError`](../global_objects/syntaxerror) in [strict mode](../strict_mode) only.

What went wrong?
----------------

Normal variables in JavaScript can't be deleted using the `delete` operator. In strict mode, an attempt to delete a variable will throw an error and is not allowed.

The `delete` operator can only delete properties on an object. Object properties are "qualified" if they are configurable.

Unlike what common belief suggests, the `delete` operator has **nothing** to do with directly freeing memory. Memory management is done indirectly via breaking references, see the [memory management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management) page and the `delete` operator page for more details.

This error only happens in [strict mode code](../strict_mode). In non-strict code, the operation just returns `false`.

Examples
--------

### Freeing the contents of a variable

Attempting to delete a plain variable, doesn't work in JavaScript and it throws an error in strict mode:

    'use strict';

    var x;

    // ...

    delete x;

    // SyntaxError: applying the 'delete' operator to an unqualified name
    // is deprecated

To free the contents of a variable, you can set it to [`null`](../global_objects/null):

    'use strict';

    var x;

    // ...

    x = null;

    // x can be garbage collected

See also
--------

-   `delete`
-   [Memory management](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Memory_Management)
-   [TypeError: property "x" is non-configurable and can't be deleted](cant_delete)

<a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Delete_in_strict_mode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Errors/Delete_in_strict_mode</a>
