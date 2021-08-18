# Event.eventPhase

The `eventPhase` read-only property of the [`Event`](../event) interface indicates which phase of the event flow is currently being evaluated.

## Syntax

    let phase = event.eventPhase;

### Value

Returns an integer value which specifies the current evaluation phase of the event flow. Possible values are listed in [Event phase constants](#event_phase_constants).

## Constants

### Event phase constants

These values describe which phase the event flow is currently being evaluated.

<table><thead><tr class="header"><th>Constant</th><th>Value</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>Event.NONE</code></td><td><code>0</code></td><td>No event is being processed at this time.</td></tr><tr class="even"><td><code>Event.CAPTURING_PHASE</code></td><td><code>1</code></td><td>The event is being propagated through the target's ancestor objects. This process starts with the <a href="../window"><code>Window</code></a>, then <a href="../document"><code>Document</code></a>, then the <a href="../htmlhtmlelement"><code>HTMLHtmlElement</code></a>, and so on through the elements until the target's parent is reached. <a href="../eventlistener">Event listeners</a> registered for capture mode when <a href="../eventtarget/addeventlistener"><code>EventTarget.addEventListener()</code></a> was called are triggered during this phase.</td></tr><tr class="odd"><td><code>Event.AT_TARGET</code></td><td><code>2</code></td><td>The event has arrived at <a href="../eventtarget">the event's target</a>. Event listeners registered for this phase are called at this time. If <a href="bubbles"><code>Event.bubbles</code></a> is <code>false</code>, processing the event is finished after this phase is complete.</td></tr><tr class="even"><td><code>Event.BUBBLING_PHASE</code></td><td><code>3</code></td><td>The event is propagating back up through the target's ancestors in reverse order, starting with the parent, and eventually reaching the containing <a href="../window"><code>Window</code></a>. This is known as <em>bubbling</em>, and occurs only if <a href="bubbles"><code>Event.bubbles</code></a> is <code>true</code>. <a href="../eventlistener">Event listeners</a> registered for this phase are triggered during this process.</td></tr></tbody></table>

For more details, see [section 3.1, Event dispatch and DOM event flow](https://www.w3.org/TR/DOM-Level-3-Events/#event-flow), of the DOM Level 3 Events specification.

## Example

### HTML

    <h4>Event Propagation Chain</h4>
    <ul>
      <li>Click 'd1'</li>
      <li>Analyze event propagation chain</li>
      <li>Click next div and repeat the experience</li>
      <li>Change Capturing mode</li>
      <li>Repeat the experience</li>
    </ul>
    <input type="checkbox" id="chCapture" />
    <label for="chCapture">Use Capturing</label>
      <div id="d1">d1
        <div id="d2">d2
          <div id="d3">d3
            <div id="d4">d4</div>
          </div>
        </div>
      </div>
    <div id="divInfo"></div>

### CSS

    div {
      margin: 20px;
      padding: 4px;
      border: thin black solid;
    }

    #divInfo {
      margin: 18px;
      padding: 8px;
      background-color:white;
      font-size:80%;
    }

### JavaScript

    let clear = false,
        divInfo = null,
        divs = null,
        useCapture = false;

    window.onload = function () {
      divInfo = document.getElementById('divInfo')
      divs = document.getElementsByTagName('div')
      chCapture = document.getElementById('chCapture')
      chCapture.onclick = function () {
        RemoveListeners()
        AddListeners()
      }
      Clear()
      AddListeners()
    }

    function RemoveListeners() {
      for (let i = 0; i < divs.length; i++) {
        let d = divs[i]
        if (d.id != "divInfo") {
          d.removeEventListener("click", OnDivClick, true)
          d.removeEventListener("click", OnDivClick, false)
        }
      }
    }

    function AddListeners() {
      for (let i = 0; i < divs.length; i++) {
        let d = divs[i]
        if (d.id != "divInfo") {
            if (chCapture.checked) {
                d.addEventListener("click", OnDivClick, true)
            }
            else {
                d.addEventListener("click", OnDivClick, false)
                d.onmousemove = function () { clear = true }
            }
        }
      }
    }

    function OnDivClick(e) {
      if (clear) {
        Clear()
        clear = false
      }
      if (e.eventPhase == 2)
        e.currentTarget.style.backgroundColor = 'red';
        const level =
            e.eventPhase == 0 ? "none" :
            e.eventPhase == 1 ? "capturing" :
            e.eventPhase == 2 ? "target" :
            e.eventPhase == 3 ? "bubbling" : "error";
        const p = document.createElement('p')
        p.textContent = `${e.currentTarget.id}; eventPhase: ${level}`;
        divInfo.appendChild(p);
    }

    function Clear() {
      for (let i = 0; i < divs.length; i++) {
        if (divs[i].id != "divInfo") {
          divs[i].style.backgroundColor = (i & 1) ? "#f6eedb" : "#cceeff"
        }
      }
      divInfo.textContent = '';
    }

### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/#dom-event-eventphase">DOM<br />
<span class="small">The definition of 'Event.eventPhase' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/dom/#dom-event-eventphase">DOM4<br />
<span class="small">The definition of 'Event.eventPhase' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td></td></tr><tr class="odd"><td><a href="https://www.w3.org/TR/DOM-Level-2-Events/events.html#Events-Event-eventPhase">Document Object Model (DOM) Level 2 Events Specification<br />
<span class="small">The definition of 'Event.eventPhase' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td><td>Initial definition</td></tr></tbody></table>

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

`eventPhase`

45

12

Yes

9

32

Yes

45

45

Yes

32

Yes

5.0

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Event/eventPhase" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Event/eventPhase</a>
