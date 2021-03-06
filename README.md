<img src="screenshots/splash.png" alt="Amethyst Game Engine" />

![Pic](/screenshots/blending.png)

The Voxel Mapper is a set of Amethyst-compatible systems for creating beautiful
voxel worlds.

![Demo](/screenshots/demo.gif)

## Usage

To build and run with the example assets:

```
GRAPHICS_BACKEND=metal
cargo run --bin editor --release --features amethyst/$GRAPHICS_BACKEND,amethyst/no-slow-safety-checks -- assets/maps/example_map.ron
```

When you exit the app, a binary file "saved_voxels.bin" will contain the map you just created.
You can load it back into the editor by setting `voxels_file_path: Some("saved_voxels.bin")` in "assets/maps/example_map.ron."

Control bindings can be found in "assets/config/map_editor_bindings.ron".

If you want to import your own material images, take a look at [material-converter](https://github.com/bonsairobo/material-converter).
It makes it easy to import material images from sites like freepbr.com (don't you wish they meant the beer?).

## Development

It's early days for this project. These features are currently supported:

- (de)serializable, chunked voxel map
- dynamic, smooth chunk meshing using Surface Nets
- multiple materials
- physically-based, triplanar material rendering, courtesy of Amethyst
- a voxel paintbrush
- a camera controller that resolves collisions with the voxels
- texture splatting

Planned features:

- more realistic texture splatting using depth textures
- texture detiling
- more materials
- dynamic voxel types (e.g. water, foliage)
- beautiful example maps
- level of detail
- procedural generation
