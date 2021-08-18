# &lt;filter-function&gt;

The `<filter-function>` [CSS](https://developer.mozilla.org/en-US/docs/Web/CSS) [data type](css_types) represents a graphical effect that can change the appearance of an input image. It is used in the [`filter`](filter) and [`backdrop-filter`](backdrop-filter) properties.

## Syntax

The `<filter-function>` data type is specified using one of the filter functions listed below. Each function requires an argument which, if invalid, results in no filter being applied.

[`blur()`](<filter-function/blur()>)  
Blurs the image.

[`brightness()`](<filter-function/brightness()>)  
Makes the image brighter or darker.

[`contrast()`](<filter-function/contrast()>)  
Increases or decreases the image's contrast.

[`drop-shadow()`](<filter-function/drop-shadow()>)  
Applies a drop shadow behind the image.

[`grayscale()`](<filter-function/grayscale()>)  
Converts the image to grayscale.

[`hue-rotate()`](<filter-function/hue-rotate()>)  
Changes the overall hue of the image.

[`invert()`](<filter-function/invert()>)  
Inverts the colors of the image.

[`opacity()`](<filter-function/opacity()>)  
Makes the image transparent.

[`saturate()`](<filter-function/saturate()>)  
Super-saturates or desaturates the input image.

[`sepia()`](<filter-function/sepia()>)  
Converts the image to sepia.

## Examples

### Filter function comparison

This example provides a simple graphic, along with a select menu to allow you to choose between the different types of filter function, and a slider to allow you to vary the values used inside the filter function. Updating the controls updates the filter effect in real time, allowing you to investigate the effects of different filters.

#### HTML

    <div></div>
    <ul>
      <li>
        <label for="filter-select">Choose a filter function:</label>
        <select id="filter-select">
          <option selected>blur</option>
          <option>brightness</option>
          <option>contrast</option>
          <option>drop-shadow</option>
          <option>grayscale</option>
          <option>hue-rotate</option>
          <option>invert</option>
          <option>opacity</option>
          <option>saturate</option>
          <option>sepia</option>
        </select>
      </li>
      <li>
        <input type="range"><output></output>
      </li>
      <li>
        <p>Current value: <code></code></p>
      </li>
    </ul>

#### CSS

    div {
      width: 300px;
      height: 300px;
      background: url(https://media.prod.mdn.mozit.cloud/attachments/2020/07/29/17350/3b4892b7e820122ac6dd7678891d4507/firefox.png) no-repeat center;
    }

    li {
      display: flex;
      align-items: center;
      justify-content: center;
      margin-bottom: 20px;
    }

    input {
      width: 60%
    }

    output {
      width: 5%;
      text-align: center;
    }

    select {
      width: 40%;
      margin-left: 2px;
    }

#### JavaScript

    const selectElem = document.querySelector('select');
    const divElem = document.querySelector('div');
    const slider = document.querySelector('input');
    const output = document.querySelector('output');
    const curValue = document.querySelector('p code');

    selectElem.addEventListener('change', () => {
      setSlider(selectElem.value);
      setDiv(selectElem.value);
    });

    slider.addEventListener('input', () => {
      setDiv(selectElem.value);
    });

    function setSlider(filter) {
      if(filter === 'blur') {
        slider.value = 0;
        slider.min = 0;
        slider.max = 30;
        slider.step = 1;
        slider.setAttribute('data-unit', 'px');
      } else if(filter === 'brightness' || filter === 'contrast' || filter === 'saturate') {
        slider.value = 1;
        slider.min = 0;
        slider.max = 4;
        slider.step = 0.05;
        slider.setAttribute('data-unit', '');
      } else if(filter === 'drop-shadow') {
        slider.value = 0;
        slider.min = -20;
        slider.max = 40;
        slider.step = 1;
        slider.setAttribute('data-unit', 'px');
      } else if(filter === 'opacity') {
        slider.value = 1;
        slider.min = 0;
        slider.max = 1;
        slider.step = 0.01;
        slider.setAttribute('data-unit', '');
      } else if(filter === 'grayscale' || filter === 'invert' || filter === 'sepia') {
        slider.value = 0;
        slider.min = 0;
        slider.max = 1;
        slider.step = 0.01;
        slider.setAttribute('data-unit', '');
      } else if(filter === 'hue-rotate') {
        slider.value = 0;
        slider.min = 0;
        slider.max = 360;
        slider.step = 1;
        slider.setAttribute('data-unit', 'deg');
      }
    }

    function setDiv(filter) {
      if(filter === 'drop-shadow') {
        divElem.style.filter = `${selectElem.value}(${Math.round(slider.value)}${slider.getAttribute('data-unit')}${Math.round(slider.value)}${slider.getAttribute('data-unit')}${Math.round(Math.abs(slider.value/2))}${slider.getAttribute('data-unit')})`;
      } else {
        divElem.style.filter = `${selectElem.value}(${slider.value}${slider.getAttribute('data-unit')}`;
      }

      updateOutput();
      updateCurValue();
    }

    function updateOutput() {
      output.textContent = slider.value;
    }

    function updateCurValue() {
      curValue.textContent = `filter: ${divElem.style.filter}`;
    }

    setSlider(selectElem.value);
    setDiv(selectElem.value);

#### Result

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th></tr></thead><tbody><tr class="odd"><td><a href="https://drafts.fxtf.org/filter-effects/#typedef-filter-function">Filter Effects Module Level 1<br />
<span class="small">The definition of 'filter-function' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td></tr></tbody></table>

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

`filter-function`

53

18

In Chrome 18 to 19, the `saturate()` function only takes integers instead of decimal or percentage values. From Chrome 20, this bug is fixed.

12

12

35

49

No

Internet Explorer 4 to 9 implemented a non-standard `filter` property. The syntax was completely different from this one and is not documented here.

40

15

9.1

6

53

4.4

53

35

49

41

14

9.3

6

6.0

`svg`

No

No

35

No

No

No

No

No

35

No

No

No

## See also

- Properties that use this data type: [`filter`](filter) and [`backdrop-filter`](backdrop-filter)

<a href="https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/CSS/filter-function</a>
