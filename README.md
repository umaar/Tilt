# Tilt: a WebGL-based 3D visualization of a Webpage
#### [Development Blog](http://blog.mozilla.com/tilt/)
#### [Tilt Project Page](https://wiki.mozilla.org/Tilt_Project_Page)

### Description
> Tilt represents a new way of visualizing a web page. This tool creates a 3D representation of the document, with the purpose of displaying, understanding and easily analyzing the DOM. It will take advantage of the great tools Firefox has to offer, as it is an extension which contains a WebGL implementation, providing rich user-experience, fun interaction and useful information, while taking full advantage of 3D hardware acceleration, GLSL shaders and what OpenGL ES 2.0 has to offer.

> The implementation consists of a Firefox extension containing a 3D representation of a web page, as both a fun visualization tool and a developer-friendly environment for debugging the document’s structure, contents and nesting of the DOM tree. Various information besides the actual contents will be displayed on request, regarding each node’s type, class, id, and other attributes if available. The rendering will be dynamic, in-browser, using WebGL and GLSL shaders.
#### [Additional info](http://www.google-melange.com/gsoc/proposal/review/google/gsoc2011/victorporof/1#)

### Principles
Before submitting this proposal, I’ve experimented with various techniques of achieving the desired visualization results and polished user experience, by implementing a few of the required features and asking for feedback from knowledgeable people working in the domain. As a result, some key aspects must be pointed out:

*		Building an internal representation of the DOM shall be achieved by creating an iFrame overlay in XUL as a Firefox extension. From experience, other techniques like injecting code into a web page, using already existing extensions (like Firebug), or depending on cloud services or CGI scripts are all bad ideas, as they are not scalable, deliver inconsistent user experience and don’t leave the original DOM intact.
* 	Each node will be rendered as a stack element, roughly described as representing a “box”, having the X and Y positions grabbed from the object’s off-screen rendered coordinates using HTML5 canvas functions (therefore avoiding manually redrawing the entire web-page), and distributed on the Z depth axis based on the actual node depth in the DOM tree.
* 	The base node will be represented by the BODY, upon which the child elements are layered to form a 3D stack of platforms. These platforms shall be build at the addition of DIVS, ULs or other nodes containing children.
* 	Some elements are positioned in absolute or floating manners; these could be graphically represented in different ways, like a shadowing plane, or by graphically adding a floating animation.
* 	Various other minimal information, characteristics or attributes will be visually attached to each stack representation of a node, with the possibility of displaying these properties more in depth at the user’s interaction with the visualization. Therefore, it’s a good idea to implement features that help understanding and analyzing the DOM, not just displaying it.
* 	If required, a useful “map” of the DOM tree will be available, used for rapid navigation/orientation through the visualization.
* 	The display will require intuitive controls, therefore an arcball controlled camera will be used, from the papers of Ken Shoemake, describing general purpose 3D rotation. Moreover, panning will be required for navigation, and other yaw, pitch and roll controls could be implemented.
* 	Sliders or other UI elements could be used for modifying or setting the visualization parameters, like the distance between node layers, auto-rotation, and other effects.
* 	The tool will be used as part of a web-page inspector, therefore a clean visualization will be more suited. A polished representation, not a bloated one, with subtle screen space ambient occlusion, a bit of lighting and shadowing is more appropriate and visually pleasing, adding a “stark” feel to it, thus focusing on the beauty of the web page itself and the DOM, and not on the achievable effects.
* 	Ways of exporting the visualization to other WebGL compatible browsers should be implemented, for cross-platform and cross-browser user experience. This can be done by saving the representation parameters and passing them to other browsers. In the end, the export feature will actually be an URL.
* 	As Tilt is designed to also be fun, a few easter-eggs could be implemented :)

### The final deliverables
1. A stand-alone Firefox extension which will contain the visualization
2. A WebGL javascript library designed to facilitate creating web page DOM visualizations
3. Examples, test-cases, stress-tests and documentation, so that the tool will continue to be developed even after the finalization of GSoC, both by me and the desiring community.