Window.console
==============

The `Window.console` property returns a reference to the [`Console`](../console) object, which provides methods for logging information to the browser's console. These methods are intended for debugging purposes only and should not be relied on for presenting information to end users.

Examples
--------

### Logging to console

The first example logs text to the console.

    console.log("An error occurred while loading the content");

The next example logs an object to the console, with the object's fields expandable using disclosure widgets:

    console.dir(someObject);

See [Usage](../console#usage) in [console](../console) for more thorough examples.

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://console.spec.whatwg.org/">Console API</a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

Currently there are many implementation differences among browsers, but work is being done to bring them together and make them more consistent with one another.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/console" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/console</a>
