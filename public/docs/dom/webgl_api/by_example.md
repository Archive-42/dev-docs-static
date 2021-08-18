WebGL by example
================

Examples by topic
-----------------

-   <a href="by_example/detect_webgl" class="button minimal">Next »</a>

*WebGL by example* is a series of live samples with short explanations that showcase WebGL concepts and capabilities. The examples are sorted according to topic and level of difficulty, covering the WebGL rendering context, shader programming, textures, geometry, user interaction, and more.

The examples are sorted in order of increasing difficulty. But rather than just presenting them in a single long list, they are additionally divided into topics. Sometimes we revisit a topic several times, such as when needing to discuss it initially at a basic level, and later at intermediate and advanced levels.

Instead of trying to juggle shaders, geometry, and working with [GPU](https://developer.mozilla.org/en-US/docs/Glossary/GPU) memory, already in the first program, the examples here explore WebGL in an incremental way. We believe that it leads to a more effective learning experience and ultimately a deeper understanding of the underlying concepts.

Explanations about the examples are found in both the main text and in comments within the code. You should read all comments, because more advanced examples could not repeat comments about parts of the code that were previously explained.

### Getting to know the rendering context

[Detect WebGL](by_example/detect_webgl)  
This example demonstrates how to detect a [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) rendering context and reports the result to the user.

[Clearing with colors](by_example/clearing_with_colors)  
How to clear the rendering context with a solid color.

[Clearing by clicking](by_example/clearing_by_clicking)  
How to combine user interaction with graphics operations. Clearing the rendering context with a random color when the user clicks.

[Simple color animation](by_example/simple_color_animation)  
A very basic color animation, done by clearing the [WebGL](https://developer.mozilla.org/en-US/docs/Glossary/WebGL) drawing buffer with a different random color every second.

[Color masking](by_example/color_masking)  
Modifying random colors by applying color masking and thus limiting the range of displayed colors to specific shades.

[Basic scissoring](by_example/basic_scissoring)  
How to draw simple rectangles and squares with scissoring operations.

[Canvas size and WebGL](by_example/canvas_size_and_webgl)  
The example explores the effect of setting (or not setting) the canvas size to its element size in [CSS](https://developer.mozilla.org/en-US/docs/Glossary/CSS) pixels, as it appears in the browser window.

[Boilerplate 1](by_example/boilerplate_1)  
The example describes repeated pieces of code that will be hidden from now on, as well as defining a JavaScript utility function to make WebGL initialization easier.

[Scissor animation](by_example/scissor_animation)  
Some animation fun with scissoring and clearing operations.

[Raining rectangles](by_example/raining_rectangles)  
A simple game that demonstrates clearing with solid colors, scissoring, animation, and user interaction.

### Shader programming basics

[Hello GLSL](by_example/hello_glsl)  
A very basic shader program that draws a solid color square.

[Hello vertex attributes](by_example/hello_vertex_attributes)  
Combining shader programming and user interaction through vertex attributes.

[Textures from code](by_example/textures_from_code)  
A simple demonstration of procedural texturing with fragment shaders.

### Miscellaneous advanced examples

[Video textures](by_example/video_textures)  
This example demonstrates how to use video files as textures.

-   <a href="by_example/detect_webgl" class="button minimal">Next »</a>

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/By_example</a>
