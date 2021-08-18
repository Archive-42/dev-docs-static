HTMLDetailsElement: toggle event
================================

The `toggle` event fires when the `open`/`closed` state of a [`<details>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details) element is toggled.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../event"><code>Event</code></a></td></tr><tr class="even"><td>Event handler property</td><td>None</td></tr><tr class="odd"><td>Default Action</td><td>Toggles the <code>open</code> state of the <a href="https://developer.mozilla.org/en-US/docs/Web/HTML/Element/details"><code>&lt;details&gt;</code></a> element.</td></tr></tbody></table>

Examples
--------

This example logs chapters that are open. Chapters are removed from the log when they are closed.

### HTML

    <aside id="log">
      <b>Open chapters:</b>
      <div data-id="ch1" hidden>I</div>
      <div data-id="ch2" hidden>II</div>
      <div data-id="ch3" hidden>III</div>
    </aside>
    <section id="summaries">
      <b>Chapter summaries:</b>
      <details id="ch1">
        <summary>Chapter I</summary>
        Philosophy reproves Boethius for the foolishness of his complaints against Fortune. Her very nature is caprice.
      </details>
      <details id="ch2">
        <summary>Chapter II</summary>
        Philosophy in Fortune's name replies to Boethius' reproaches, and proves that the gifts of Fortune are hers to give and to take away.
      </details>
      <details id="ch3">
        <summary>Chapter III</summary>
        Boethius falls back upon his present sense of misery. Philosophy reminds him of the brilliancy of his former fortunes.
      </details>
    </section>

### CSS

    body {
      display: flex;
      flex-direction: row-reverse;
    }

    #log {
      flex-shrink: 0;
      padding-left: 3em;
    }

    #summaries {
      flex-grow: 1;
    }

### JavaScript

    function logItem(e) {
      const item = document.querySelector(`[data-id=${e.target.id}]`);
      item.toggleAttribute('hidden');
    }

    const chapters = document.querySelectorAll('details');
    chapters.forEach((chapter) => {
      chapter.addEventListener('toggle', logItem);
    });

### Result

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://html.spec.whatwg.org/multipage/indices.html#event-toggle">HTML Living Standard<br />
<span class="small">The definition of 'toggle event' in that specification.</span></a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

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

`toggle_event`

Yes

79

Yes

No

Yes

Yes

Yes

Yes

Yes

Yes

Yes

Yes

<a href="https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/HTMLDetailsElement/toggle_event</a>
