Using the Performance API
=========================

A fundamental requirement of web performance is a precise and consistent definition of *time.* The [`DOMHighResTimeStamp`](../domhighrestimestamp) type (a `double`) is used by all performance interfaces to hold such time values. Additionally, there must be a way to create a *timestamp* for a specific point in time; this is done with the [`now()`](../performance/now) method.

Web performance interfaces are defined in a [suite of standards](https://www.w3.org/wiki/Web_Performance/Publications). The *base* interface for these standards is the [`Performance`](../performance) interface and its methods and properties are extended by different standards. This guide describes how to use the [`Performance`](../performance) interfaces that are defined in the [High-Resolution Time](https://w3c.github.io/hr-time/) standard. Other web performance guides (listed in the [See also](#see_also) section) describe how to use additional methods and properties of the [`Performance`](../performance) interface.

High precision timing
---------------------

*High precision timing* is achieved by using the [`DOMHighResTimeStamp`](../domhighrestimestamp) type for time values. The unit is milliseconds and should be accurate to 5 µs (microseconds). However, if the browser is unable to provide a time value accurate to 5 microseconds (because of hardware or software constraints, for example), the browser can represent the value as a time in milliseconds accurate to a millisecond.

The following code example shows the use of [`DOMHighResTimeStamp`](../domhighrestimestamp) and the [`Performance.now()`](../performance/now) method. The [`now()`](../performance/now) method returns a *timestamp* (of type [`DOMHighResTimeStamp`](../domhighrestimestamp)) that is a discrete point in time. By calling this method before and after a task, the time it takes to do the task can be measured.

    function calculate_time() {
      var startTime;
      var endTime;

      startTime = performance.now();
      do_task();
      endTime = performance.now();

      return (endTime - startTime);
    }

Serializing the `Performance` object
------------------------------------

JSON serialization of the [`Performance`](../performance) object is done via the [`toJSON()`](../performance/tojson) method. In the following example, JSON serialization for the [`Performance`](../performance), [`Performance.timing`](../performance/timing) and [`Performance.navigation`](../performance/navigation) objects is printed in the `object` element.

    function print_json() {
      var json;
      var o = document.getElementsByTagName("output")[0];

      if (window.performance.toJSON === undefined) {
        json = "window.performance.toJSON() is NOT supported";
        o.innerHTML += json + "<br>";
      } else {
        var s;
        json = window.performance.toJSON();

        // Print the performance object
        s = JSON.stringify(json);
        o.innerHTML = "<p>performance = " + s + "</p>";

        // Print the performance.timing and performance.navigation objects
        var perf = JSON.parse(s);

        var timing = perf.timing;
        o.innerHTML += "<p>peformance.timing = " + JSON.stringify(timing) + "</p>";

        var navigation = perf.navigation;
        o.innerHTML += "<p>peformance.navigation = " + JSON.stringify(navigation) + "</p>";
      }
    }

Specifications
--------------

The interfaces described in this document are defined in the `High Resolution Time` standard which has two levels:

-   [High-Resolution Time Level 2](https://w3c.github.io/hr-time/); Editors Draft; Work In Progress
-   [High-Resolution Time](https://www.w3.org/TR/hr-time/); W3C Recommendation 17 December 2012

Interoperability
----------------

As shown in the [`Performance`](../performance) interface's [Browser Compatibility](../performance#browser_compatibility) table, most of the [`Performance`](../performance) interfaces are broadly implemented by desktop browsers.

See also
--------

-   [`Performance API Overview`](../performance_api)
-   [A Primer for Web Performance Timing APIs](https://siusin.github.io/perf-timing-primer/)
-   [Graphic of Web Performance Layers](https://docs.google.com/document/d/1ZKW9N0cteHgK91SyYQONFuy2ZW6J4Oak398niTo232E/edit)
-   [CanIUse data for High-Resolution Time](https://caniuse.com/#search=high-resolution-time)
-   [Web Performance Standards Status and Roadmap](https://www.w3.org/wiki/Web_Performance/Publications)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Performance_API/Using_the_Performance_API" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Performance_API/Using_the_Performance_API</a>
