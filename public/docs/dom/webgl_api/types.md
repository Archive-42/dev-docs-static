WebGL types
===========

The following types are used in [WebGL](../webgl_api) interfaces.

WebGL 1
-------

These types are used within a [`WebGLRenderingContext`](../webglrenderingcontext).

<table><thead><tr class="header"><th>Type</th><th>Web IDL type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>GLenum</code></td><td><code>unsigned long</code></td><td>Used for enums. See also the list of <a href="constants">constants</a>.</td></tr><tr class="even"><td><code>GLboolean</code></td><td><code>boolean</code></td><td>A <a href="https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Boolean"><code>Boolean</code></a>.</td></tr><tr class="odd"><td><code>GLbitfield</code></td><td><code>unsigned long</code></td><td>A bit field that stores multiple, logical bits. Used for example in <a href="../webglrenderingcontext/clear"><code>WebGLRenderingContext.clear()</code></a>.</td></tr><tr class="even"><td><code>GLbyte</code></td><td><code>byte</code></td><td>8-bit twos complement signed integer.</td></tr><tr class="odd"><td><code>GLshort</code></td><td><code>short</code></td><td>16-bit twos complement signed integer.</td></tr><tr class="even"><td><code>GLint</code></td><td><code>long</code></td><td>32-bit twos complement signed integer.</td></tr><tr class="odd"><td><code>GLsizei</code></td><td><code>long</code></td><td>Used for sizes (e.g. width and height of the drawing buffer).</td></tr><tr class="even"><td><code>GLintptr</code></td><td><code>long long</code></td><td>Special type for pointer arithmetic.</td></tr><tr class="odd"><td><code>GLsizeiptr</code></td><td><code>long long</code></td><td>Special type for pointer arithmetic.</td></tr><tr class="even"><td><code>GLubyte</code></td><td><code>octet</code></td><td>8-bit twos complement unsigned integer.</td></tr><tr class="odd"><td><code>GLushort</code></td><td><code>unsigned short</code></td><td>16-bit twos complement unsigned integer.</td></tr><tr class="even"><td><code>GLuint</code></td><td><code>unsigned long</code></td><td>32-bit twos complement unsigned integer.</td></tr><tr class="odd"><td><code>GLfloat</code></td><td><code>unrestricted float</code></td><td>32-bit IEEE floating point number.</td></tr><tr class="even"><td><code>GLclampf</code></td><td><code>unrestricted float</code></td><td>Clamped 32-bit IEEE floating point number.</td></tr></tbody></table>

WebGL 2
-------

These types are used within a [`WebGL2RenderingContext`](../webgl2renderingcontext). All WebGL 1 types are used as well.

<table><thead><tr class="header"><th>Type</th><th>Web IDL type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>GLint64</code></td><td><code>long long</code></td><td>Signed 64-bit integer number.</td></tr></tbody></table>

WebGL extensions
----------------

These types are used within [WebGL extensions](using_extensions).

<table><thead><tr class="header"><th>Type</th><th>Web IDL type</th><th>Description</th></tr></thead><tbody><tr class="odd"><td><code>GLuint64EXT</code></td><td><code>long long</code></td><td>Unsigned 64-bit integer number.</td></tr></tbody></table>

Specifications
--------------

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/1.0/#5.1">WebGL 1.0<br />
<span class="small">The definition of 'Types' in that specification.</span></a></td><td><span class="spec-rec">Recommendation</span></td><td>Initial definition</td></tr><tr class="even"><td><a href="https://www.khronos.org/registry/webgl/specs/latest/2.0/#3.1">WebGL 2.0<br />
<span class="small">The definition of 'Types' in that specification.</span></a></td><td><span class="spec-ed">Editor's Draft</span></td><td>Defines additional types.</td></tr><tr class="odd"><td><a href="https://www.khronos.org/registry/webgl/extensions/EXT_disjoint_timer_query/">EXT_disjoint_timer_query<br />
<span class="small">The definition of 'GLuint64EXT' in that specification.</span></a></td><td><span class="spec-wd">Working Draft</span></td><td>Adds <code>GLuint64EXT</code></td></tr></tbody></table>

See also
--------

-   [`WebGLRenderingContext`](../webglrenderingcontext)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Types" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Types</a>
