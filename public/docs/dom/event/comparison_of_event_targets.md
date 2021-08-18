# Comparison of Event Targets

### Event targets

It's easy to get confused about which target to examine when writing an event handler. This article should clarify the use of the target properties.

There are five targets to consider:

<table><colgroup><col style="width: 33%" /><col style="width: 33%" /><col style="width: 33%" /></colgroup><thead><tr class="header"><th>Property</th><th>Defined in</th><th>Purpose</th></tr></thead><tbody><tr class="odd"><td><code>event.target</code></td><td><a href="https://www.w3.org/TR/DOM-Level-2/events.html#Events-interface">DOM Event Interface</a></td><td><p>The DOM element on the lefthand side of the call that triggered this event, eg:</p><pre><code>element.dispatchEvent(event)</code></pre></td></tr><tr class="even"><td><code>event.currentTarget</code></td><td><a href="https://www.w3.org/TR/DOM-Level-2/events.html#Events-interface">DOM Event Interface</a></td><td>The <a href="https://www.w3.org/TR/DOM-Level-2/events.html#Events-EventTarget"><code>EventTarget</code></a> whose <a href="https://www.w3.org/TR/DOM-Level-2/events.html#Events-EventListener"><code>EventListeners</code></a> are currently being processed. As the event capturing and bubbling occurs, this value changes.</td></tr><tr class="odd"><td><code>event.relatedTarget</code></td><td><a href="https://www.w3.org/TR/DOM-Level-2/events.html#Events-MouseEvent">DOM MouseEvent Interface</a></td><td>Identifies a secondary target for the event.</td></tr><tr class="even"><td><code>event.explicitOriginalTarget</code></td><td><a href="https://dxr.mozilla.org/mozilla-central/source//dom/webidl/Event.webidl">Event.webidl</a></td><td><span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span> If the event was retargeted for some reason other than an anonymous boundary crossing, this will be set to the target before the retargeting occurs. For example, mouse events are retargeted to their parent node when they happen over text nodes (<a href="https://bugzilla.mozilla.org/show_bug.cgi?id=185889">bug 185889</a>), and in that case <code>.target</code> will show the parent and <code>.explicitOriginalTarget</code> will show the text node.<br />
Unlike <code>.originalTarget</code>, <code>.explicitOriginalTarget</code> will never contain anonymous content.</td></tr><tr class="odd"><td><code>event.originalTarget</code></td><td><a href="https://dxr.mozilla.org/mozilla-central/source//dom/webidl/Event.webidl">Event.webidl</a></td><td><span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span> The original target of the event, before any retargetings. See <a href="https://developer.mozilla.org/en-US/docs/XBL/XBL_1.0_Reference/Anonymous_Content#Event_Flow_and_Targeting">Anonymous Content#Event_Flow_and_Targeting</a> for details.</td></tr><tr class="even"><td>event.composedTarget</td><td><a href="https://dxr.mozilla.org/mozilla-central/source//dom/webidl/Event.webidl">Event.webidl</a></td><td><span class="icon non-standard" data-viewbox="0 0 100 100" data-xmlns="http://www.w3.org/2000/svg" data-role="img"> This API has not been standardized. </span> The original non-native target of the event before composition from Shadow DOM.</td></tr></tbody></table>

### Use of `explicitOriginalTarget` and `originalTarget`

**TODO:** Only available in a Mozilla-based browser?

**TODO:** Only suitable for extension-developers?

### Examples

    <!DOCTYPE html>
    <html>
    <head>
        <meta charset="utf-8">
        <meta http-equiv="X-UA-Compatible" content="IE=edge">
        <title>Comparison of Event Targets</title>
        <style>
            table {
                border-collapse: collapse;
                height: 150px;
                width: 100%;
            }
            td {
                border: 1px solid #ccc;
                font-weight: bold;
                padding: 5px;
                min-height: 30px;
            }
            .standard {
                background-color: #99ff99;
            }
            .non-standard {
                background-color: #902D37;
            }
        </style>
    </head>
    <body>
        <table>
        <thead>
            <tr>
                <td class="standard">Original target dispatching the event <small>event.target</small></td>
                <td class="standard">Target who's event listener is being processed <small>event.currentTarget</small></td>
                <td class="standard">Identify other element (if any) involved in the event <small>event.relatedTarget</small></td>
                <td class="non-standard">If there was a retargeting of the event for some reason <small> event.explicitOriginalTarget</small> contains the target before retargeting (never contains anonymous targets)</td>
                <td class="non-standard">If there was a retargeting of the event for some reason <small> event.originalTarget</small> contains the target before retargeting (may contain anonymous targets)</td>
            </tr>
        </thead>
        <tr>
            <td id="target"></td>
            <td id="currentTarget"></td>
            <td id="relatedTarget"></td>
            <td id="explicitOriginalTarget"></td>
            <td id="originalTarget"></td>
        </tr>
    </table>
    <p>Clicking on the text will show the difference between explicitOriginalTarget, originalTarget, and target</p>
    <script>
        function handleClicks(e) {
            document.getElementById('target').innerHTML = e.target;
            document.getElementById('currentTarget').innerHTML = e.currentTarget;
            document.getElementById('relatedTarget').innerHTML = e.relatedTarget;
            document.getElementById('explicitOriginalTarget').innerHTML = e.explicitOriginalTarget;
            document.getElementById('originalTarget').innerHTML = e.originalTarget;
        }

        function handleMouseover(e) {
            document.getElementById('target').innerHTML = e.target;
            document.getElementById('relatedTarget').innerHTML = e.relatedTarget;
        }

        document.addEventListener('click', handleClicks, false);
        document.addEventListener('mouseover', handleMouseover, false);
    </script>
    </body>
    </html>

### Use of `target` and `relatedTarget`

The `relatedTarget` property for the `mouseover` event holds the node that the mouse was previously over. For the `mouseout` event, it holds the node that the mouse moved to.

<table><thead><tr class="header"><th>Event type</th><th><a href="target">event.target</a></th><th><a href="../mouseevent/relatedtarget">event.relatedTarget</a></th></tr></thead><tbody><tr class="odd"><td><code>mouseover</code></td><td>the EventTarget which the pointing device entered</td><td>the EventTarget which the pointing device exited</td></tr><tr class="even"><td><code>mouseout</code></td><td>the EventTarget which the pointing device exited</td><td>the EventTarget which the pointing device entered</td></tr></tbody></table>

**TODO:** Also needs descriptions for `dragenter` and `dragexit` events.

#### Example

    <hbox id="outer">
      <hbox id="inner"
            onmouseover="dump('mouseover ' + event.relatedTarget.id + ' > ' + event.target.id + '\n');"
            onmouseout="dump('mouseout  ' + event.target.id + ' > ' + event.relatedTarget.id + '\n');"
            style="margin: 100px; border: 10px solid black; width: 100px; height: 100px;" />
    </hbox>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/Comparison_of_Event_Targets" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/Comparison_of_Event_Targets</a>
