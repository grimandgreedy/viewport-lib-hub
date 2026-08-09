# viewport-lib-hub

An index of the plugins, helpers, and demo apps built on [viewport-lib](https://github.com/grimandgreedy/viewport-lib).

Some repos are public and linked below. The rest are private; they are listed here for reference but the source is not published.

## Plugins

Crates that extend viewport-lib through its `ItemTypePlugin` / `RuntimePlugin` traits.

- **[viewport-lib-terrain](https://github.com/grimandgreedy/viewport-lib-terrain)**
  Heightmap and splatmap terrain as an `ItemTypePlugin`. Quadtree LOD with per-patch decimation and crack-hiding skirts, frustum culling at patch granularity, and eight surface layers blended on the GPU through two splatmaps.

- **[viewport-lib-wind](https://github.com/grimandgreedy/viewport-lib-wind)**
  Smooth, cyclical wind-like motion for meshes: geometry sways and ripples the way grass, foliage, and banners move in a breeze.

- **[rapier-viewport-plugin](https://github.com/grimandgreedy/rapier-viewport-plugin)**
  [Rapier 3D](https://rapier.rs) physics as a `RuntimePlugin`.

- **hamilton_engine**
  XPBD rigid-body + soft-body physics `RuntimePlugin`.

## Helper crates

Reusable libraries. These stand on their own and avoid pulling in the renderer where they can.

- **[viewport-lib-io](https://github.com/grimandgreedy/viewport-lib-io)**
  File-format loaders and exporters. Decodes source files into neutral CPU-side data that several downstream paths can reuse, with no dependency on the viewport-lib runtime or upload structs.

- **[viewport-lib-lightbake](https://github.com/grimandgreedy/viewport-lib-lightbake)**
  Offline lightmap bake tools: UV1 unwrapping and atlas packing via xatlas, plus edge-aware denoise and encode into a neutral lightmap type. CPU-only; the GPU G-buffer and GI solve steps live in viewport-lib, which it uses only as a dev-dependency.

- **tetmesh_kit**
  Tetrahedral mesh construction: a surface/implicit voxelizer, STL loader, validator, and surface extraction. Renderer- and physics-agnostic; depends only on `glam` and `viewport-lib`.

- **tetmesh_skin**
  Embedded-deformation cage skinning. Binds a fine surface mesh to a coarse tet cage by barycentric coordinates and deforms it from per-frame cage positions. The pure-CPU path has no renderer dependency.

## Apps

Applications that demo the library and the plugins above.

- **[poincare](https://github.com/grimandgreedy/poincare)**
  An interactive 3D mathematical graphing application and a reusable 3D plotting library, using viewport-lib for its viewport and rendering. Install with `cargo install poincare-app`.
