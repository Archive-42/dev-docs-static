# NavigatorPlugins.plugins

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

Returns a [`PluginArray`](../pluginarray) object, listing the [`Plugin`](../plugin) objects describing the plugins installed in the application.

In Firefox 29 and later, enumeration of the `navigator.plugins` array may be restricted as a privacy measure. Applications that must check for the presence of a browser plugin should query `navigator.plugins` or [`navigator.mimeTypes`](mimetypes) by exact name instead of enumerating the `navigator.plugins` array and comparing every plugin's name. This privacy change does not disable any plugins; it just hides some plugin names from enumeration.

## Syntax

    var plugins = navigator.plugins;

`plugins` is [`PluginArray`](../pluginarray) object used to access [`Plugin`](../plugin) objects either by name or as a list of items.

The returned value is not a JavaScript array, but has the `length` property and supports accessing individual items using bracket notation (`plugins[2]`), as well as via `item(index)` and `namedItem("name")` methods.

## Examples

The following example function returns the version of the Shockwave Flash plugin.

    function getFlashVersion() {
      var flash = navigator.plugins.namedItem('Shockwave Flash');
      if (typeof flash != 'object') {
        // flash is not present
        return undefined;
      }
      if(flash.version){
        return flash.version;
      } else {
        //No version property (e.g. in Chrome)
        return flash.description.replace(/Shockwave Flash /,"");
      }
    }

The following example displays information about the installed plugin(s).

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

## Notes

The [`Plugin`](../plugin) object exposes a small interface for getting information about the various plugins installed in your browser. A list of plugins is also available by entering `about:plugins` in the browser's Location bar.

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/#dom-navigator-plugins">HTML Living Standard<br />
<span class="small">The definition of 'NavigatorPlugins.plugins' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>Initial definition.</td></tr></tbody></table>

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

`plugins`

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

In addition to listing each plugin as a pseudo-array by zero-indexed numeric properties, Firefox provides properties that are the plugin name directly on the [PluginArray](../pluginarray) object.

<a href="https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/plugins" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/NavigatorPlugins/plugins</a>
