# Element: mouseleave event

The `mouseleave` event is fired at an [`Element`](../element) when the cursor of a pointing device (usually a mouse) is moved out of it.

<table><tbody><tr class="odd"><td>Bubbles</td><td>No</td></tr><tr class="even"><td>Cancelable</td><td>No</td></tr><tr class="odd"><td>Interface</td><td><a href="../mouseevent"><code>MouseEvent</code></a></td></tr><tr class="even"><td>Event handler property</td><td><a href="../globaleventhandlers/onmouseleave"><code>onmouseleave</code></a></td></tr></tbody></table>

`mouseleave` and `mouseout` are similar but differ in that `mouseleave` does not bubble and `mouseout` does. This means that `mouseleave` is fired when the pointer has exited the element _and_ all of its descendants, whereas `mouseout` is fired when the pointer leaves the element _or_ leaves one of the element's descendants (even if the pointer is still within the element).

<img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAcMAAADGCAMAAACZ4hvrAAAABGdBTUEAALGPC/xhBQAAAAFzUkdCAK7OHOkAAAJ/UExURf//////+h8FBAAFIfz//y0HBYjC5wAAAPH+/+zHi/b/////9u3+/wAIMER/vVYOCv/939r8/n+85sbExsXu/QAScZLH6//+8KChoAAVev/57QAOUP716P/+5/7twDkJB+z4/vzv3vXo18GIUrt/Of3nt9jo9v/51v/0z+e9e9GfY/LIiXuv2v/+65GQkun+/uT+/uvBhQAMRwAncffWn+zdzQAKPGOZzLh+Ri53urrm/d/MtvHOlwAPXUwMCpjO8P/91f/zxmcQDVWTyeX0/gA2ggtLlEOHwA4yTLDd98iTWp6bnevHhfXs5qGirEMLCW0zEMLI0siRTHxDE8+ibdDGwJyCZXkwEW4mD04xDfT6//ncrNDf7RhmrdH1/rnN4AAoeoB8gff19jp5tJeuxcvW5iYlIo6DgwVBicfl+MGEPy5PZ8jR3nddQDciCf7uyQkiO3Rycb/f9U5PUhNVlYukvIefwg4ODpVTF8anienGlruvqbZzHt3RygYtXuHm7b2lkcze7aBaIy1ursn0/YPC6YlGFSpFVuDRuwA1dZ6Hd6zF42ak1m1taVxEMNeoc6rd+anE2YqGjk+Lw+Pt97zX4/fhxU5tiHCOpINTLY273jhAOvLl0B1xtUFdfM2bWjKAvXyerK5+T+vNoOXVxytnoti8oDwtFaqyv3e14VpBEIZnQKNpLezs7NPT096wdkhIRGZhV+3zyUBypeO+hsmymlZzkBRbnyImMqNvQ2N/mMavkWySvqHU8crI1rByMp683DNUi7S0tOTd5FhYWZddGTt8u1B/sfPevjUzL25KLp6UjY13Y9+vbWBSNbKroSwLMbWnetPpz8/Xpa2TWTZ0NvcAAArrSURBVHja7ZyJVxRXFodfb16gIeyLrIIQ2QVkiQqIuEVRUdBxXzCKiBMRRSXEPYpx3+PCOO6J+27URE1MojNGk8z2B8191U0E9JyZruaEetW/75xuuquru8t36713X9fnFQIAAAAAAAAAAPhffFm3Svy97ns0hMJ8QGEin4aiIbrTdChPTMv24A0hS5d5/CWWH+3y/pO1dl3HOGm2+8FA6idKHSVvXnFu6rnvophbN3wshNGtQRGikG//N4U0zONvyYr0k981Y2GgjkMc/jFt16IzW4thNxIdyw/auwVwHVG4j8UwkwoihKX1jPYk/khy+PviwtQB/DB8Kjd7PJ/mk/iWEv5nbinLhvAjQvwSmSdip8tXRfx03tUp+xjv5N7GfWMDf4j2HiFi+ROXCMv+MrklunaMxzGM3TyLiKK4D68gOnbV1Q/b6p/Jryr86tmdJKKVZ0d3CSD5XAznUF0x98GMgvnyWQ03QNCvRGMD2qw2KpsvGvv7ifVjxU2qpxa/kClktT0R3z2wn+dXd+aJNrn7+EQ6IBIqT7m3CZFQy5uzxTS+bwnMl236XimRFr3UsQGeHd5f/mQlsn0zV4jTHCuOIsfQn95Lc9jGa7PjRXvKLgdv/XqJED+4Auhj1IuQysOlchxtchyQHai1YNjIpLv2mv53qj+yh1SOc7af4QFwlLN9nhxurw3J4yjw8/Tywxy1sJApo0QO/6ncLjIL/uXapo21B8TAu2nWbNFUvsefTorT/QOz+mtdtPGMRxEMOcEH+eFiHhVEWhL9LcB5zh1DZysdFqIimEbI3n1/H++2Y5Ww//CTL/bD1MjB+TKGIx1ynhkUvEf4F2/jnpYRFyqc7UNDgsNEelIUD7gbD4r06oLmvVci7yRF+dPy5r3WcWL40tv7qJ+z/XBF9Z7ObfJTaPliP3/acfs2DfUvni84gPmuGKZ6llEmchc76XroT0MGcxef6YqhyJBP82lInuvV8xw4efq4w+hTMcyplKetLcIdwzm2YaJmjF/OzJLGhgDuVaPkhqygiNgBw3+mkpFJZ6tiXi3mfjshLqYqJndZBh279B8+A1Jf1EQOdm+Tn5q8+VdquEfHY2Jidk/k4PFtoiuGNac8OrxBU/jo/rpAPpxA4zrzUhlDPk+eiK00StvtwlXerXi8+00cRp/KSy1FN5ZMsH0fwDGUTZBRFupsHcpPRkwr4wUHHcgvCB0UvHDwes4qW081ObaLNMeIzMhA2UunlYWmRgZYri0czLMl5xzubbLL8KNf4v7N20KmlHTGMFJLZlKWeJ6S8mi6ZgCPBPO6xpCnwhcV1UGcIMfev8K7dEtOfQz+l2fRNr4L4juxvsE+qPyymGjb1lRefIVKeGrrsHLjtdGH+yjb8og66KLf1nkiPTjoK85a7tGOFcSrhSxqsXduY9KDbbfoM3GOdlgLIjI4eHzzdw176yM9zktTZFZDI/bTR641vjuGhbTzn5x6ifRymdFs8fE1fvxTHua2amd50VwRPf2ISH5qF/GfTp4r+8HkLSncQCm/TeZ7y/QYHtcu8HZ+Va4VPq9akMxrjuhwmdu7t7keTbXLVy+NFvJ1vjmnX5KZSdESHQcY++0sCssimT5zFuOOYc4Mjt1lOWWuXDMaP9TIrE/Hsv2PHPI3jA6ZSRuPFtVSZwx5cCUes0XO0wCET2PCKOMvZB2u9ZD8vVQOq4lJPF4DtUjetXr12s8PLRNfLN0t++bmQ6vQKAAAAAAAAIA/FrhU6gOXSlk8canUJWVX3UFheK9NHx64VG7C99ZfVy6E6dUbb9Meg3ttuvDApXoTQH6HejHMjAsVjWP8DOy16cMTl6pLAJWMoWWRSG5/YDes16YPD10qJqZeVa/tpdCuw4UZ1WvTi+culRA3musV7Yc8CP74iPugMb02vehyqdxhVC+GRTxlJVpHGNRr8yol1eVS3WhepFwMawpCxU3NTTSm1+bFoslnXKqmcttLOdoY12vzYnXhKy5V7KdVR4WxvTYvsm5fcqkM7rV5g8+4VAp4bbqBSwUAAAAAAJQHHo76wMNRFt/wcMyM5x6OuFGHZjMOnns42nXHdX14yCm7mhf7mdRr04HHHk7n9f8+jGGiY+Vr61g/E3ptevDcwznU6eH0YQxPl+XJC/Wm89r0ntH6ahr1rRM1iccEWSjKXF6bXvTWNFrXp/1QnnzVDwJM5rV5lZLq8HA4jPV9edRzqmXnMZfX5lWSp56H00YtPO6bzmvzanWhmIczx3oxQBb8Mp/X5g1qeTjXZMrBXcmMXpuXZ7cyHs6GcGbqbJN6bV6hmodjYq/NZzCz1wYAAAAAAHQCl0p94FIpC1wq1dHhUgEjocOl6j3aTgo4Ud7iuUvVBa/LOJx38MwLJ8orPHepugSw6paXHodlIMmrY3CivEJPTaPfA8ibvPt259WDjTIDhhPlDfpqGrkD6HUMGS2GcKK8Tkk9dqmqOnqrXpvLU4IT5S16XKrruR290w+7xBBOlFerCz0ulRbG3oohnCjv0edSXc/1+ovXy74BJ6q36BOXqki6T3Cieo2+cqngRKkPnCgAAAAAAKDzJ4Fv63Ld1L1z/XEdbWR0cirf/HQd9o6XHy0MRCMZnfvcAz+mAtkR39EPEx0NiKESlFKD65dUy6IeTkZFdUMA2kcF/GmMpqnIS1c7dgtx7uGzPCHaXq78bQXRyxI0kDIxlO7DQ4fUHwqJxsmrjQ+kJOGSAoASMcyk4t0i+hzFzRenyfZkK5WFisSkMZgP1YlhdC3tkZmoVKmi22UHfCLEyOoGP7SPMjEMmUnU0dHxUltjJCYRyXkQMVQqhumzOteJL3huDNbsDcRQrRgmzKB+FrvdPmmTXTpxpEk5iKFa82G7JmwMkipVKdHZWhrrJ2OI9aFCeWkG0debLpyggvkcxwf2QjkjNiXZjm9BAylAvrTKhOWcazrMdj6ngghtPH1SUU6u9T8wOE2v1mgj5vC9q3/6ZpnIeZUrTaqEV7kLxBevmx9jNAUAAAAAADop/UeU6wEKDSnLB9r/vhcoNKQmssZQwkztf/CJdxQaelODCBgUV42hNOtF+eRdhYZEatDx99FOhqWzxpDYT9ndCw1Fn3goJ0jno4dRjb/XXgCG402NIcvzoGHdCw2J77SLEolJtvHOL392114ABqNLjSFRUb4zsHuhIVFIsnJMJmmFXVzRfozabQajS40hUUrjehYaSphBl0VOLbkLquU8J4LBbTS61BjiRCaqZ6Eh7oItAXOscVoZp/hP5Lx5F9cjjJiSuua5nBlxoW8VGkpzFG+r0SbFoteytBaSU2PirjGU5mixi56Fhixb6ewUufKfwLtsXIzrusZdXcgaQzelKNqz0JC4x7GTU2QqHTuKhjI0lg2jr8mCpW8VGuJwanX3ijCIKpDdBMvu9lahIR5Wbageowjp+x5rf3sUGuI/a5GJAgAAAAAA4KPAbVIfuE1KA7dJdeA2KQ7cJtWB26Q6cJvUB26T+sBtMklKCrdJeeA2mWJ1AbfJBMBtMkV2A7dJeeA2AQAAAAAAAHoCt0l94DYpDdwm1YHbpDhwm1QHbpPqwG1SH7hN6gO3ySQpKdwm5YHbZIrVBdwmEwC3yRTZDdwm5YHbBAAAAAAAeht4MeoDL0Zp4MWoDrwYxYEXozrwYlQHXoz6wItRH3gxJklJ4cUoD7wYU6wu4MWYAHgxpshu4MUoD7wYAAAAAAAAAAAAAAA85b9KdcJsVe5CHwAAAABJRU5ErkJggg==" class="default internal" width="451" height="198" />

One `mouseleave` event is sent to each element of the hierarchy when leaving them. Here four events are sent to the four elements of the hierarchy when the pointer moves from the text to an area outside of the most outer div represented here.

<img src="data:image/png;base64,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" class="default internal" width="454" height="207" />

One single `mouseout` event is sent to the deepest element of the DOM tree, then it bubbles up the hierarchy until it is canceled by a handler or reaches the root.

## Examples

The [`mouseout`](mouseout_event#examples) documentation has an example illustrating the difference between `mouseout` and `mouseleave`.

### mouseleave

The following trivial example uses the `mouseenter` event to change the border on the `<div>` when the mouse enters the space alloted to it. It then adds an item to the list with the number of the `mouseenter` or `mouseleave` event.

#### HTML

    <div id='mouseTarget'>
     <ul id="unorderedList">
      <li>No events yet!</li>
     </ul>
    </div>

#### CSS

Styling the `<div>` to make it more visible.

    #mouseTarget {
      box-sizing: border-box;
      width:15rem;
      border:1px solid #333;
    }

#### JavaScript

    var enterEventCount = 0;
    var leaveEventCount = 0;
    const mouseTarget = document.getElementById('mouseTarget');
    const unorderedList = document.getElementById('unorderedList');

    mouseTarget.addEventListener('mouseenter', e => {
      mouseTarget.style.border = '5px dotted orange';
      enterEventCount++;
      addListItem('This is mouseenter event ' + enterEventCount + '.');
    });

    mouseTarget.addEventListener('mouseleave', e => {
      mouseTarget.style.border = '1px solid #333';
      leaveEventCount++;
      addListItem('This is mouseleave event ' + leaveEventCount + '.');
    });

    function addListItem(text) {
      // Create a new text node using the supplied text
      var newTextNode = document.createTextNode(text);

      // Create a new li element
      var newListItem = document.createElement("li");

      // Add the text node to the li element
      newListItem.appendChild(newTextNode);

      // Add the newly created list item to list
      unorderedList.appendChild(newListItem);
    }

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://w3c.github.io/uievents/#event-type-mouseleave">UI Events<br />
<span class="small">The definition of 'mouseleave' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr><tr class="even"><td><a href="https://www.w3.org/TR/2014/WD-DOM-Level-3-Events-20140925/#event-type-mouseleave">Document Object Model (DOM) Level 3 Events Specification<br />
<span class="small">The definition of 'mouseleave' in that specification.</span></a></td><td><span class="spec-obsolete">Obsolete</span></td></tr></tbody></table>

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

`mouseleave_event`

30

12

10

5.5

17

6.1

≤37

30

10

18

6.1

2.0

## See also

- [Introduction to events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events)
- `mousedown`
- `mouseup`
- `mousemove`
- `click`
- `dblclick`
- `mouseover`
- `mouseout`
- `mouseenter`
- `mouseleave`
- `contextmenu`

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Element/mouseleave_event</a>
