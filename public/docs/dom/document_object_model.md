# Document Object Model (DOM)

The **Document Object Model** (**DOM**) connects web pages to scripts or programming languages by representing the structure of a document—such as the HTML representing a web page—in memory. Usually it refers to JavaScript, even though modeling HTML, SVG, or XML documents as objects are not part of the core JavaScript language.

The DOM represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects. DOM methods allow programmatic access to the tree. With them, you can change the document's structure, style, or content.

Nodes can also have event handlers attached to them. Once an event is triggered, the event handlers get executed.

**To learn more** about what the DOM is and how it represents documents, see our article [Introduction to the DOM](document_object_model/introduction).

## DOM interfaces

- [`Attr`](attr)
- [`CDATASection`](cdatasection)
- [`CharacterData`](characterdata)
- [`ChildNode`](childnode) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`Comment`](comment)
- [`CustomEvent`](customevent)
- [`Document`](document)
- [`DocumentFragment`](documentfragment)
- [`DocumentType`](documenttype)
- [`DOMError`](domerror) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`DOMException`](domexception)
- [`DOMImplementation`](domimplementation)
- [`DOMString`](domstring)
- [`DOMTimeStamp`](domtimestamp)
- [`DOMStringList`](domstringlist)
- [`DOMTokenList`](domtokenlist)
- [`Element`](element)
- [`Event`](event)
- [`EventTarget`](eventtarget)
- [`HTMLCollection`](htmlcollection)
- [`MutationObserver`](mutationobserver)
- [`MutationRecord`](mutationrecord)
- [`NamedNodeMap`](namednodemap)
- [`Node`](node)
- [`NodeFilter`](nodefilter)
- [`NodeIterator`](nodeiterator)
- [`NodeList`](nodelist)
- [`ParentNode`](parentnode)
- [`ProcessingInstruction`](processinginstruction)
- [`Selection`](selection) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`Range`](range)
- [`Text`](text)
- [`TextDecoder`](textdecoder) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`TextEncoder`](textencoder) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`TimeRanges`](timeranges)
- [`TreeWalker`](treewalker)
- [`URL`](url)
- [`Window`](window)
- [`Worker`](worker)
- [`XMLDocument`](xmldocument) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>

### Obsolete DOM interfaces

The Document Object Model has been highly simplified. To achieve this, the following interfaces present in the different DOM level 3 or earlier specifications have been removed. It is uncertain whether some may be reintroduced in the future or not, but for the time being they should be considered obsolete and should be avoided:

- [`DocumentTouch`](documenttouch)
- <span class="page-not-created">`DOMConfiguration`</span>
- <span class="page-not-created">`DOMErrorHandler`</span>
- <span class="page-not-created">`DOMImplementationList`</span>
- <span class="page-not-created">`DOMImplementationRegistry`</span>
- <span class="page-not-created">`DOMImplementationSource`</span>
- [`DOMLocator`](domlocator)
- [`DOMObject`](domobject)
- <span class="page-not-created">`DOMSettableTokenList`</span>
- [`DOMUserData`](domuserdata)
- [`ElementTraversal`](elementtraversal)
- <span class="page-not-created">`Entity`</span>
- <span class="page-not-created">`EntityReference`</span>
- <span class="page-not-created">`NameList`</span>
- [`Notation`](notation)
- [`TypeInfo`](typeinfo)
- [`UserDataHandler`](userdatahandler)

## HTML DOM

A document containing HTML is described using the [`Document`](document) interface, which is extended by the HTML specification to include various HTML-specific features. In particular, the [`Element`](element) interface is enhanced to become [`HTMLElement`](htmlelement) and various subclasses, each representing one of (or a family of closely related) elements.

The HTML DOM API provides access to various browser features such as tabs and windows, CSS styles and stylesheets, browser history, and so forth. These interfaces are discussed further in [the HTML DOM API](html_dom_api) documentation.

## SVG interfaces

### SVG element interfaces

- [`SVGAElement`](svgaelement)
- [`SVGAltGlyphElement`](svgaltglyphelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGAltGlyphDefElement`](svgaltglyphdefelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGAltGlyphItemElement`](svgaltglyphitemelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGAnimationElement`](svganimationelement)
- [`SVGAnimateElement`](svganimateelement)
- [`SVGAnimateColorElement`](svganimatecolorelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGAnimateMotionElement`](svganimatemotionelement)
- [`SVGAnimateTransformElement`](svganimatetransformelement)
- [`SVGCircleElement`](svgcircleelement)
- [`SVGClipPathElement`](svgclippathelement)
- [`SVGColorProfileElement`](svgcolorprofileelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGComponentTransferFunctionElement`](svgcomponenttransferfunctionelement)
- [`SVGCursorElement`](svgcursorelement)
- [`SVGDefsElement`](svgdefselement)
- [`SVGDescElement`](svgdescelement)
- [`SVGElement`](svgelement)
- [`SVGEllipseElement`](svgellipseelement)
- [`SVGFEBlendElement`](svgfeblendelement)
- [`SVGFEColorMatrixElement`](svgfecolormatrixelement)
- [`SVGFEComponentTransferElement`](svgfecomponenttransferelement)
- [`SVGFECompositeElement`](svgfecompositeelement)
- [`SVGFEConvolveMatrixElement`](svgfeconvolvematrixelement)
- [`SVGFEDiffuseLightingElement`](svgfediffuselightingelement)
- [`SVGFEDisplacementMapElement`](svgfedisplacementmapelement)
- [`SVGFEDistantLightElement`](svgfedistantlightelement)
- [`SVGFEDropShadowElement`](svgfedropshadowelement)
- [`SVGFEFloodElement`](svgfefloodelement)
- [`SVGFEFuncAElement`](svgfefuncaelement)
- [`SVGFEFuncBElement`](svgfefuncbelement)
- [`SVGFEFuncGElement`](svgfefuncgelement)
- [`SVGFEFuncRElement`](svgfefuncrelement)
- [`SVGFEGaussianBlurElement`](svgfegaussianblurelement)
- [`SVGFEImageElement`](svgfeimageelement)
- [`SVGFEMergeElement`](svgfemergeelement)
- [`SVGFEMergeNodeElement`](svgfemergenodeelement)
- [`SVGFEMorphologyElement`](svgfemorphologyelement)
- [`SVGFEOffsetElement`](svgfeoffsetelement)
- [`SVGFEPointLightElement`](svgfepointlightelement)
- [`SVGFESpecularLightingElement`](svgfespecularlightingelement)
- [`SVGFESpotLightElement`](svgfespotlightelement)
- [`SVGFETileElement`](svgfetileelement)
- [`SVGFETurbulenceElement`](svgfeturbulenceelement)
- [`SVGFilterElement`](svgfilterelement)
- [`SVGFilterPrimitiveStandardAttributes`](svgfilterprimitivestandardattributes)
- [`SVGFontElement`](svgfontelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGFontFaceElement`](svgfontfaceelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGFontFaceFormatElement`](svgfontfaceformatelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGFontFaceNameElement`](svgfontfacenameelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGFontFaceSrcElement`](svgfontfacesrcelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGFontFaceUriElement`](svgfontfaceurielement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGForeignObjectElement`](svgforeignobjectelement)
- [`SVGGElement`](svggelement)
- [`SVGGeometryElement`](svggeometryelement)
- [`SVGGlyphElement`](svgglyphelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGGlyphRefElement`](svgglyphrefelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGGradientElement`](svggradientelement)
- [`SVGGraphicsElement`](svggraphicselement)
- <span class="page-not-created">`SVGHatchElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`SVGHatchpathElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`SVGHKernElement`](svghkernelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGImageElement`](svgimageelement)
- [`SVGLinearGradientElement`](svglineargradientelement)
- [`SVGLineElement`](svglineelement)
- <span class="page-not-created">`SVGMarkerElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`SVGMaskElement`](svgmaskelement)
- <span class="page-not-created">`SVGMeshElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`SVGMeshGradientElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`SVGMeshpatchElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- <span class="page-not-created">`SVGMeshrowElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`SVGMetadataElement`](svgmetadataelement)
- [`SVGMissingGlyphElement`](svgmissingglyphelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGMPathElement`](svgmpathelement)
- [`SVGPathElement`](svgpathelement)
- [`SVGPatternElement`](svgpatternelement)
- [`SVGPolylineElement`](svgpolylineelement)
- [`SVGPolygonElement`](svgpolygonelement)
- [`SVGRadialGradientElement`](svgradialgradientelement)
- [`SVGRectElement`](svgrectelement)
- [`SVGScriptElement`](svgscriptelement)
- [`SVGSetElement`](svgsetelement)
- [`SVGSolidcolorElement`](svgsolidcolorelement) <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`SVGStopElement`](svgstopelement)
- [`SVGStyleElement`](svgstyleelement)
- [`SVGSVGElement`](svgsvgelement)
- [`SVGSwitchElement`](svgswitchelement)
- [`SVGSymbolElement`](svgsymbolelement)
- [`SVGTextContentElement`](svgtextcontentelement)
- [`SVGTextElement`](svgtextelement)
- [`SVGTextPathElement`](svgtextpathelement)
- [`SVGTextPositioningElement`](svgtextpositioningelement)
- [`SVGTitleElement`](svgtitleelement)
- [`SVGTRefElement`](svgtrefelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGTSpanElement`](svgtspanelement)
- [`SVGUseElement`](svguseelement)
- <span class="page-not-created">`SVGUnknownElement`</span> <span class="icon experimental" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This is an experimental API that should not be used in production code. </span>
- [`SVGViewElement`](svgviewelement)
- [`SVGVKernElement`](svgvkernelement) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

### SVG data type interfaces

Here are the DOM APIs for data types used in the definitions of SVG properties and attributes.

#### Static type

- [`SVGAngle`](svgangle)
- <span class="page-not-created">`SVGColor`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGICCColor`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGElementInstance`</span>
- <span class="page-not-created">`SVGElementInstanceList`</span>
- [`SVGLength`](svglength)
- [`SVGLengthList`](svglengthlist)
- [`SVGMatrix`](svgmatrix) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGNameList`</span>
- [`SVGNumber`](svgnumber)
- [`SVGNumberList`](svgnumberlist)
- <span class="page-not-created">`SVGPaint`</span>
- <span class="page-not-created">`SVGPathSeg`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegClosePath`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegMovetoAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegMovetoRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoCubicAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoCubicRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoQuadraticAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoQuadraticRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegArcAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegArcRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoHorizontalAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoHorizontalRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoVerticalAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegLinetoVerticalRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoCubicSmoothAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoCubicSmoothRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoQuadraticSmoothAbs`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegCurvetoQuadraticSmoothRel`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPathSegList`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGPoint`](svgpoint) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGPointList`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGPreserveAspectRatio`](svgpreserveaspectratio)
- [`SVGRect`](svgrect) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGStringList`](svgstringlist)
- [`SVGTransform`](svgtransform)
- [`SVGTransformList`](svgtransformlist)

#### Animated type

- [`SVGAnimatedAngle`](svganimatedangle)
- [`SVGAnimatedBoolean`](svganimatedboolean)
- [`SVGAnimatedEnumeration`](svganimatedenumeration)
- [`SVGAnimatedInteger`](svganimatedinteger)
- [`SVGAnimatedLength`](svganimatedlength)
- [`SVGAnimatedLengthList`](svganimatedlengthlist)
- [`SVGAnimatedNumber`](svganimatednumber)
- [`SVGAnimatedNumberList`](svganimatednumberlist)
- <span class="page-not-created">`SVGAnimatedPathData`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGAnimatedPoints`](svganimatedpoints)
- [`SVGAnimatedPreserveAspectRatio`](svganimatedpreserveaspectratio)
- [`SVGAnimatedRect`](svganimatedrect)
- [`SVGAnimatedString`](svganimatedstring)
- [`SVGAnimatedTransformList`](svganimatedtransformlist)

### SMIL-related interfaces

- <span class="page-not-created">`ElementTimeControl`</span>
- [`TimeEvent`](timeevent)

### Other SVG interfaces

- <span class="page-not-created">`GetSVGDocument`</span>
- <span class="page-not-created">`ShadowAnimation`</span>
- <span class="page-not-created">`SVGColorProfileRule`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGCSSRule`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGDocument`</span>
- <span class="page-not-created">`SVGException`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGExternalResourcesRequired`](svgexternalresourcesrequired) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGFitToViewBox`</span>
- <span class="page-not-created">`SVGLangSpace`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- <span class="page-not-created">`SVGLocatable`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGRenderingIntent`](svgrenderingintent) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGStylable`](svgstylable) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGTests`](svgtests)
- [`SVGTransformable`](svgtransformable) <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGUnitTypes`](svgunittypes)
- <span class="page-not-created">`SVGUseElementShadowRoot`</span>
- [`SVGURIReference`](svgurireference)
- <span class="page-not-created">`SVGViewSpec`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>
- [`SVGZoomAndPan`](svgzoomandpan)
- <span class="page-not-created">`SVGZoomEvent`</span> <span class="icon deprecated" viewbox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img"> This deprecated API should no longer be used, but will probably still work. </span>

## Specifications

<table><thead><tr class="header"><th>Specification</th><th>Status</th><th>Comment</th></tr></thead><tbody><tr class="odd"><td><a href="https://dom.spec.whatwg.org/">DOM</a></td><td><span class="spec-living">Living Standard</span></td><td></td></tr></tbody></table>

## See also

- [DOM Examples](document_object_model/examples)
- [CSS Object Model (CSSOM)](css_object_model)

<a href="https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model</a>
