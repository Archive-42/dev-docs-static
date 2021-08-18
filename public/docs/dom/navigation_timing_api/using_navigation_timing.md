# Using Navigation Timing

The Navigation Timing API lets you easily obtain detailed and highly accurate timing information to help isolate performance problems with your site's code or resources. Unlike other tools or libraries, the [Navigation Timing API](../navigation_timing_api) lets you gather information that only the browser can provide at a level of accuracy much improved over other techniques. It also offers the advantage of being able to provide timing information as perceived by the user rather than data that has no correlation to what the user experiences.

## Collecting timing information

Using the API is as simple as obtaining the [`Performance`](../performance) object using [`window.performance`](../window/performance) and looking up what you need within the object returned. For example, to measure the perceived loading time for a page:

    window.addEventListener("load", function() {
      let now = new Date().getTime();
      let loadingTime = now - performance.timing.navigationStart;

      document.querySelector(".output").innerText =
            loadingTime + " ms";
    }, false);

This code, executed when the `load` event occurs, subtracts from the current time the time at which the navigation whose timing was recorded began ([`performance.timing.navigationStart`](../performancetiming/navigationstart)), and outputs that information to the screen by inserting it into an element.

In tandem with appropriate HTML and CSS, the result is:

The values listed are for the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) in which the sample is presented above.

For a list of the available timing values you can look for in [`PerformanceTiming`](../performancetiming), see the [`PerformanceTiming`](../performancetiming) interface's [Properties](../performancetiming#properties) section.

## Determining navigation type

To put the timing information obtained from [`PerformanceTiming`](../performancetiming) into the correct perspective, you need to know more about what sort of load operation occurred. In particular, you need to know:

- Was this a load or a reload?
- Was this a navigation or a move forward or backward through history?
- How many (if any) redirects were required in order to complete the navigation?

This information is provided by the [`Performance.navigation`](../performance/navigation) property, which returns a [`PerformanceNavigation`](../performancenavigation) object that includes the needed information.

Let's add this information to the example above. The new code looks like this:

    window.addEventListener("load", function() {
      let now = new Date().getTime();
      let loadingTime = now - performance.timing.navigationStart;

      output = "Load time: " + loadingTime + " ms<br/>";
      output += "Navigation type: ";

      switch(performance.navigation.type) {
          case PerformanceNavigation.TYPE_NAVIGATE:
            output += "Navigation";
          break;
        case PerformanceNavigation.TYPE_RELOAD:
            output += "Reload";
          break;
        case PerformanceNavigation.TYPE_BACK_FORWARD:
            output += "History";
          break;
        default:
            output += "Unknown";
          break;
      }

      output += "<br/>Redirects: " +
          performance.navigation.redirectCount;
      document.querySelector(".output").innerHTML = output;
    }, false);

This amends the previous example by looking at the contents of the `performance.navigation` object. [`performance.navigation.type`](../performancenavigation/type) indicates what kind of load operation took place: a navigation, a reload, or a shift through the browser's history. We also obtain the number of redirects that were incurred during the navigation from [`performance.navigation.redirectCount`](../performancenavigation/redirectcount). This information is output to the screen just like the page load time was previously: by inserting it into the element with class `"output"`.

With this code in place, the result looks like this:

The values listed are for the [`<iframe>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe) in which the sample is presented.

## See also

- [Navigation Timing API](../navigation_timing_api)
- [`window.performance`](../window/performance)
- [`Performance`](../performance), [`PerformanceTiming`](../performancetiming), and [`PerformanceNavigation`](../performancenavigation)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API/Using_Navigation_Timing" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API/Using_Navigation_Timing</a>
