Window: load event
==================

The `load` event is fired when the whole page has loaded, including all dependent resources such as stylesheets and images. This is in contrast to [`DOMContentLoaded`](../document/domcontentloaded_event), which is fired as soon as the page DOM has been loaded, without waiting for resources to finish loading.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onload"><code>onload</code></a></td></tr></tbody></table>

Examples
--------

Log a message when the page is fully loaded:

    window.addEventListener('load', (event) => {
      console.log('page is fully loaded');
    });

The same, but using the `onload` event handler property:

    window.onload = (event) => {
      console.log('page is fully loaded');
    };

### Live example

#### HTML

    <div class="controls">
      <button id="reload" type="button">Reload</button>
    </div>

    <div class="event-log">
      <label>Event log:</label>
      <textarea readonly class="event-log-contents" rows="8" cols="30"></textarea>
    </div>

#### JS

    const log = document.querySelector('.event-log-contents');
    const reload = document.querySelector('#reload');

    reload.addEventListener('click', () => {
      log.textContent ='';
      window.setTimeout(() => {
          window.location.reload(true);
      }, 200);
    });

    window.addEventListener('load', (event) => {
        log.textContent = log.textContent + 'load\n';
    });

    document.addEventListener('readystatechange', (event) => {
        log.textContent = log.textContent + `readystate: ${document.readyState}\n`;
    });

    document.addEventListener('DOMContentLoaded', (event) => {
        log.textContent = log.textContent + `DOMContentLoaded\n`;
    });

#### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-load">UI Events<br />
<span class="small">The definition of 'load' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td></td></tr><tr class="even"><td><a href="https://html.spec.whatwg.org/multipage/#delay-the-load-event">HTML Living Standard<br />
<span class="small">The definition of 'load event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td>This links to the section in the steps that are carried out at the end of loading a document. 'load' events are fired at many elements too. And note there are many places in the specification that refer to things that can "<a href="https://html.spec.whatwg.org/multipage/parsing.html#delay-the-load-event">delays the load event</a>".</td></tr></tbody></table>

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

`load_event`

1

12

1

4

4

1.3

1

18

4

10.1

1

1.0

See also
--------

-   Related events: [`DOMContentLoaded`](domcontentloaded_event), [`readystatechange`](../document/readystatechange_event), [`beforeunload`](beforeunload_event), [`unload`](unload_event)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Window/load_event</a>
