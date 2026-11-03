# viewport-lib-hub

A non-exhaustive index of the plugins, widgets and companion crates for [viewport-lib](https://github.com/grimandgreedy/viewport-lib).

## Plugins

Crates that extend viewport-lib through its `ItemTypePlugin` / `RuntimePlugin` traits.

- **[viewport-lib-plugins](https://github.com/grimandgreedy/viewport-lib/tree/master/crates/viewport-lib-plugins)**
  The item types viewport-lib ships with (point clouds, sprites, volumes, curves, vector and tensor fields, splats and the rest) and deformers such as a cut for section views. Built on the same public plugin API as any other plugin.

- **[viewport-lib-terrain](https://github.com/grimandgreedy/viewport-lib-terrain)**
  Heightmap and splatmap terrain as an `ItemTypePlugin`. Quadtree LOD with per-patch decimation and crack-hiding skirts, frustum culling at patch granularity, and eight surface layers blended on the GPU through two splatmaps.

- **[viewport-lib-wind](https://github.com/grimandgreedy/viewport-lib-wind)**
  Smooth, cyclical wind-like motion for meshes: geometry sways and ripples the way grass, foliage, and banners move in a breeze.

- **[rapier-viewport-plugin](https://github.com/grimandgreedy/rapier-viewport-plugin)**
  [Rapier 3D](https://rapier.rs) physics as a `RuntimePlugin`.

## Widgets

Interactive widgets for viewport-lib.

- **[viewport-lib-gizmo](https://github.com/grimandgreedy/viewport-lib-gizmo)**
  A move / rotate / scale transform gizmo. Hit-tests the handles, turns drags and G / R / S keyboard sessions into transforms, and builds overlay items for the renderer. Builds overlay items to be submitted to the vpl frame.

- **[viewport-lib-axis-gizmo](https://github.com/grimandgreedy/viewport-lib-axis-gizmo)**
  A configurable axes indicator: a triad or a CAD view cube that shows the world axes as the camera sees them and reports the view the user clicks. Builds overlay items to be submitted to the vpl frame.

## Helper crates

Reusable libraries. These stand on their own and avoid pulling in vpl.

- **[viewport-lib-io](https://github.com/grimandgreedy/viewport-lib-io)**
  File-format loaders and exporters. Decodes source files into neutral CPU-side data that several downstream paths can reuse, with no dependency on the viewport-lib runtime or upload structs.

- **[viewport-lib-lightbake](https://github.com/grimandgreedy/viewport-lib-lightbake)**
  Offline lightmap bake tools: UV1 unwrapping and atlas packing, seam stitching, edge-aware denoise, and encode into a neutral lightmap type. Pure Rust and CPU-only, and it builds for wasm. The GPU G-buffer and GI solve steps live in viewport-lib.

