# PluginArray

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `PluginArray` interface is used to store a list of [`Plugin`](plugin) objects describing the available [plugins](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/Plugins); it's returned by the [`navigator.plugins`](navigatorplugins/plugins) property. The `PluginArray` is not a JavaScript array, but has the `length` property and supports accessing individual items using bracket notation (`plugins[2]`), as well as via `item(index)` and `namedItem("name")` methods.

**Note**: Own properties of `PluginArray` objects are no longer enumerable in the latest browser versions.

## Properties

<span class="page-not-created">`PluginArray.length`</span><span class="badge inline readonly">Read only </span>  
The number of plugins in the array.

## Methods

<span class="page-not-created">`PluginArray.item`</span>  
Returns the [`Plugin`](plugin) at the specified index into the array.

<span class="page-not-created">`PluginArray.namedItem`</span>  
Returns the [`Plugin`](plugin) with the specified name.

<span class="page-not-created">`PluginArray.refresh`</span>  
Refreshes all plugins on the current page, optionally reloading documents.

## Examples

The following example function returns the version of the Shockwave Flash plugin.

    var pluginsLength = navigator.plugins.length;

    document.body.innerHTML = pluginsLength + " Plugin(s)<br>"
      + '<table id="pluginTable"><thead>'
      +'<tr><th>Name</th><th>Filename</th><th>description</th><th>version</th></tr>'
      +'</thead><tbody></tbody></table>';

    var table = document.getElementById('pluginTable');

    for(var i = 0; i < pluginsLength; i++) {
      let newRow = table.insertRow();
      newRow.insertCell().textContent = navigator.plugins[i].name;
      newRow.insertCell().textContent = navigator.plugins[i].filename;
      newRow.insertCell().textContent = navigator.plugins[i].description;
      newRow.insertCell().textContent = navigator.plugins[i].version?navigator.plugins[i].version:"";
    }

The following example displays information about the installed plugin(s).

    var pluginsLength = navigator.plugins.length;

    document.write(
      pluginsLength.toString() + " Plugin(s)<br>" +
      "Name | Filename | description<br>"
    );

    for(var i = 0; i < pluginsLength; i++) {
      document.write(
        navigator.plugins[i].name +
        " | " +
        navigator.plugins[i].filename +
        " | " +
        navigator.plugins[i].description +
        " | " +
        navigator.plugins[i].version +
        "<br>"
      );
    }

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#pluginarray">HTML Living Standard<br />
<span class="small">The definition of 'PluginArray' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

## Browser compatibility

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

`PluginArray`

1

12

1

4

≤12.1

1

1

18

4

≤12.1

1

1.0

`item`

1

Since Chrome 59, method parameters are required instead of optional.

12

Since Edge 79, method parameters are required instead of optional.

1

6

≤12.1

Since Opera 46, method parameters are required instead of optional.

4

1

Since WebView 59, method parameters are required instead of optional.

18

Since Chrome 59, method parameters are required instead of optional.

4

≤12.1

Since Opera Android 43, method parameters are required instead of optional.

3.2

1.0

Since Samsung Internet 7.0, method parameters are required instead of optional.

`length`

Yes

12

1

4

Yes

Yes

Yes

Yes

4

No

Yes

Yes

`namedItem`

1

Since Chrome 59, method parameters are required instead of optional.

12

Since Edge 79, method parameters are required instead of optional.

1

6

≤12.1

Since Opera 46, method parameters are required instead of optional.

4

1

Since WebView 59, method parameters are required instead of optional.

18

Since Chrome 59, method parameters are required instead of optional.

4

≤12.1

Since Opera Android 43, method parameters are required instead of optional.

3.2

1.0

Since Samsung Internet 7.0, method parameters are required instead of optional.

`refresh`

1

Since Chrome 59, method parameters are required instead of optional.

12

Since Edge 79, method parameters are required instead of optional.

1

6

≤12.1

Since Opera 46, method parameters are required instead of optional.

1

1

Since WebView 59, method parameters are required instead of optional.

18

Since Chrome 59, method parameters are required instead of optional.

4

≤12.1

Since Opera Android 43, method parameters are required instead of optional.

1

1.0

Since Samsung Internet 7.0, method parameters are required instead of optional.

In addition to listing each plugin as a pseudo-array by zero-indexed numeric properties, Firefox provides properties that are the plugin name directly on the PluginArray object.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PluginArray" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PluginArray</a>
