# [GLSL Instancing Utility](https://vimeo.com/359748391)

[![screenshot](/images/screenshot1.jpg)](https://vimeo.com/359748391)

The aim of this project is to push as much instancing control parameters/data onto the GPU. This means that all transform controls (translate/scale/rotate [and also color control]) is done using TOPs and then sampled in the vertex shader. The project uses a circle over a transparent background as this instance-transform TOP. Any instance that falls within the circle will be affected. Circle is shared between all transform control TOPs, but you can also have different circle for each. Also doesn't need to be a circle, it can be anything. Explained a bit more in UI section.

Vertex displacement is done in the vertex shader using 4D noise, so each instance essentially has a different seed noise function, giving each one unique displacement. A color height map is also included to gradiently shade the instance.

You can essentially plug in any source geometry you want to instance along any instance geometry's layout.

[![screenshot](/images/screenshot2.jpg)](https://vimeo.com/359748391)

## UI
### Basic
Control over the camera zoom (camera is also controlled by the purple arcball box).

SSAO Switch

### Transform
Control for the circle area of influence that affects all instances that fall within it. Move this circle with the 'Move Me' box.

RGB controls for each of the transforms. RGB = XYZ for each one. It will show up as RGB on the instance-transform TOP, but be calculated as xyz for the instances (except for the Color controller which will obviously affect the color of the instances).

### Shape
Selection for the instance geometry layout shape and density. 

Selection for the source geometry shape, poly count and size.

### Displacement

Control for the type of normal recalculation performed. If you're not displacing vertices, you can select None. Otherwise: Faceted or Smooth.

Control for the Displacement amount ("scale").

Control for the Noise scale and speed.

Control for the Colored height map scale/range and variance between instances.

![params](/images/Params.png)
