<!-- MD024 - The Headers from the Platform-Specific Examples should be identical  -->
<!-- markdownlint-disable-file MD024 -->

# Examples

These examples demonstrate the main features of Bevy and how to use them.
To run an example, use the command `cargo run --example <Example>`, and add the option `--features x11` or `--features wayland` to force the example to run on a specific window compositor, e.g.

```sh
cargo run --features wayland --example hello_world
```

**⚠️ Note: for users of releases on crates.io!**

There are often large differences and incompatible API changes between the latest [crates.io](https://crates.io/crates/bevy) release and the development version of Bevy in the git main branch!

If you are using a released version of bevy, you need to make sure you are viewing the correct version of the examples!

- Latest release: [https://github.com/bevyengine/bevy/tree/latest/examples](https://github.com/bevyengine/bevy/tree/latest/examples)
- Specific version, such as `0.4`: [https://github.com/bevyengine/bevy/tree/v0.4.0/examples](https://github.com/bevyengine/bevy/tree/v0.4.0/examples)

When you clone the repo locally to run the examples, use `git checkout` to get the correct version:

```bash
# `latest` always points to the newest release
git checkout latest
# or use a specific version
git checkout v0.4.0
```

---

## Table of Contents

- [Examples](#examples)
  - [Table of Contents](#table-of-contents)
- [The Bare Minimum](#the-bare-minimum)
  - [Hello, World!](#hello-world)
- [Cross-Platform Examples](#cross-platform-examples)
  - [2D Rendering](#2d-rendering)
  - [3D Rendering](#3d-rendering)
  - [Application](#application)
  - [Assets](#assets)
  - [Async Tasks](#async-tasks)
  - [Audio](#audio)
  - [Diagnostics](#diagnostics)
  - [ECS (Entity Component System)](#ecs-entity-component-system)
  - [Games](#games)
  - [Input](#input)
  - [Reflection](#reflection)
  - [Scene](#scene)
  - [Shaders](#shaders)
  - [Tests](#tests)
  - [Tools](#tools)
  - [UI (User Interface)](#ui-user-interface)
  - [Window](#window)
- [Platform-Specific Examples](#platform-specific-examples)
  - [Android](#android)
    - [Setup](#setup)
    - [Build & Run](#build--run)
    - [Old phones](#old-phones)
  - [iOS](#ios)
    - [Setup](#setup-1)
    - [Build & Run](#build--run-1)
  - [WASM](#wasm)
    - [Setup](#setup-2)
    - [Build & Run](#build--run-2)

# The Bare Minimum

<!-- MD026 - Hello, World! looks better with the ! -->
<!-- markdownlint-disable-next-line MD026 -->
## Hello, World!

Example | Main | Description
--- | --- | ---
`hello_world` | [`hello_world.rs`](./hello_world.rs) | Runs a minimal example that outputs "hello world"

# Cross-Platform Examples

## 2D Rendering

Example | Main | Description
--- | --- | ---
`contributors` | [`2d/contributors.rs`](./2d/contributors.rs) | Displays each contributor as a bouncy bevy-ball!
`many_sprites` | [`2d/many_sprites.rs`](./2d/many_sprites.rs) | Displays many sprites in a grid arragement! Used for performance testing.
`mesh` | [`2d/mesh.rs`](./2d/mesh.rs) | Renders a custom mesh
`sprite` | [`2d/sprite.rs`](./2d/sprite.rs) | Renders a sprite
`sprite_sheet` | [`2d/sprite_sheet.rs`](./2d/sprite_sheet.rs) | Renders an animated sprite
`text2d` | [`2d/text2d.rs`](./2d/text2d.rs) | Generates text in 2d
`sprite_flipping` | [`2d/sprite_flipping.rs`](./2d/sprite_flipping.rs) | Renders a sprite flipped along an axis
`texture_atlas` | [`2d/texture_atlas.rs`](./2d/texture_atlas.rs) | Generates a texture atlas (sprite sheet) from individual sprites

## 3D Rendering

Example | File | Description
--- | --- | ---
`3d_scene` | [`3d/3d_scene.rs`](./3d/3d_scene.rs) | Simple 3D scene with basic shapes and lighting
`load_gltf` | [`3d/load_gltf.rs`](./3d/load_gltf.rs) | Loads and renders a gltf file as a scene
`msaa` | [`3d/msaa.rs`](./3d/msaa.rs) | Configures MSAA (Multi-Sample Anti-Aliasing) for smoother edges
`orthographic` | [`3d/orthographic.rs`](./3d/orthographic.rs) | Shows how to create a 3D orthographic view (for isometric-look games or CAD applications)
`parenting` | [`3d/parenting.rs`](./3d/parenting.rs) | Demonstrates parent->child relationships and relative transformations
`pbr` | [`3d/pbr.rs`](./3d/pbr.rs) | Demonstrates use of Physically Based Rendering (PBR) properties
`render_to_texture` | [`3d/render_to_texture.rs`](./3d/render_to_texture.rs) | Shows how to render to texture
`spawner` | [`3d/spawner.rs`](./3d/spawner.rs) | Renders a large number of cubes with changing position and material
`texture` | [`3d/texture.rs`](./3d/texture.rs) | Shows configuration of texture materials
`update_gltf_scene` | [`3d/update_gltf_scene.rs`](./3d/update_gltf_scene.rs) | Update a scene from a gltf file, either by spawning the scene as a child of another entity, or by accessing the entities of the scene
`wireframe` | [`3d/wireframe.rs`](./3d/wireframe.rs) | Showcases wireframe rendering
`z_sort_debug` | [`3d/z_sort_debug.rs`](./3d/z_sort_debug.rs) | Visualizes camera Z-ordering

## Application

Example | File | Description
--- | --- | ---
`custom_loop` | [`app/custom_loop.rs`](./app/custom_loop.rs) | Demonstrates how to create a custom runner (to update an app manually).
`drag_and_drop` | [`app/drag_and_drop.rs`](./app/drag_and_drop.rs) | An example that shows how to handle drag and drop in an app.
`empty` | [`app/empty.rs`](./app/empty.rs) | An empty application (does nothing)
`empty_defaults` | [`app/empty_defaults.rs`](./app/empty_defaults.rs) | An empty application with default plugins
`headless` | [`app/headless.rs`](./app/headless.rs) | An application that runs without default plugins
`logs` | [`app/logs.rs`](./app/logs.rs) | Illustrate how to use generate log output
`plugin` | [`app/plugin.rs`](./app/plugin.rs) | Demonstrates the creation and registration of a custom plugin
`plugin_group` | [`app/plugin_group.rs`](./app/plugin_group.rs) | Demonstrates the creation and registration of a custom plugin group
`return_after_run` | [`app/return_after_run.rs`](./app/return_after_run.rs) | Show how to return to main after the Bevy app has exited
`thread_pool_resources` | [`app/thread_pool_resources.rs`](./app/thread_pool_resources.rs) | Creates and customizes the internal thread pool

## Assets

Example | File | Description
--- | --- | ---
`asset_loading` | [`asset/asset_loading.rs`](./asset/asset_loading.rs) | Demonstrates various methods to load assets
`custom_asset` | [`asset/custom_asset.rs`](./asset/custom_asset.rs) | Implements a custom asset loader
`custom_asset_io` | [`asset/custom_asset_io.rs`](./asset/custom_asset_io.rs) | Implements a custom asset io loader
`hot_asset_reloading` | [`asset/hot_asset_reloading.rs`](./asset/hot_asset_reloading.rs) | Demonstrates automatic reloading of assets when modified on disk

## Async Tasks

Example | File | Description
--- | --- | ---
`async_compute` | [`async_tasks/async_compute.rs`](async_tasks/async_compute.rs) | How to use `AsyncComputeTaskPool` to complete longer running tasks

## Audio

Example | File | Description
--- | --- | ---
`audio` | [`audio/audio.rs`](./audio/audio.rs) | Shows how to load and play an audio file

## Diagnostics

Example | File | Description
--- | --- | ---
`custom_diagnostic` | [`diagnostics/custom_diagnostic.rs`](./diagnostics/custom_diagnostic.rs) | Shows how to create a custom diagnostic
`log_diagnostics` | [`diagnostics/log_diagnostics.rs`](./diagnostics/log_diagnostics.rs) | Add a plugin that logs diagnostics, like frames per second (FPS), to the console

## ECS (Entity Component System)

Example | File | Description
--- | --- | ---
`ecs_guide` | [`ecs/ecs_guide.rs`](./ecs/ecs_guide.rs) | Full guide to Bevy's ECS
`change_detection` | [`ecs/change_detection.rs`](./ecs/change_detection.rs) | Change detection on components
`event` | [`ecs/event.rs`](./ecs/event.rs) | Illustrates event creation, activation, and reception
`fixed_timestep` | [`ecs/fixed_timestep.rs`](./ecs/fixed_timestep.rs) | Shows how to create systems that run every fixed timestep, rather than every tick
`hierarchy` | [`ecs/hierarchy.rs`](./ecs/hierarchy.rs) | Creates a hierarchy of parents and children entities
`parallel_query` | [`ecs/parallel_query.rs`](./ecs/parallel_query.rs) | Illustrates parallel queries with `ParallelIterator`
`query_bundle` | [`ecs/query_bundle.rs`](./ecs/query_bundle.rs) | Shows how to query entities that contain components in a `Bundle`
`removal_detection` | [`ecs/removal_detection.rs`](./ecs/removal_detection.rs) | Query for entities that had a specific component removed in a previous stage during the current frame.
`startup_system` | [`ecs/startup_system.rs`](./ecs/startup_system.rs) | Demonstrates a startup system (one that runs once when the app starts up)
`state` | [`ecs/state.rs`](./ecs/state.rs) | Illustrates how to use States to control transitioning from a Menu state to an InGame state
`system_chaining` | [`ecs/system_chaining.rs`](./ecs/system_chaining.rs) | Chain two systems together, specifying a return type in a system (such as `Result`)
`system_param` | [`ecs/system_param.rs`](./ecs/system_param.rs) | Illustrates creating custom system parameters with `SystemParam`
`system_sets` | [`ecs/system_sets.rs`](./ecs/system_sets.rs) | Shows `SystemSet` use along with run criterion
`timers` | [`ecs/timers.rs`](./ecs/timers.rs) | Illustrates ticking `Timer` resources inside systems and handling their state

## Games

Example | File | Description
--- | --- | ---
`alien_cake_addict` | [`game/alien_cake_addict.rs`](./game/alien_cake_addict.rs) | Eat the cakes. Eat them all. An example 3D game
`breakout` | [`game/breakout.rs`](./game/breakout.rs) | An implementation of the classic game "Breakout"

## Input

Example | File | Description
--- | --- | ---
`char_input_events` | [`input/char_input_events.rs`](./input/char_input_events.rs) | Prints out all chars as they are inputted.
`gamepad_input` | [`input/gamepad_input.rs`](./input/gamepad_input.rs) | Shows handling of gamepad input, connections, and disconnections
`gamepad_input_events` | [`input/gamepad_input_events.rs`](./input/gamepad_input_events.rs) | Iterates and prints gamepad input and connection events
`keyboard_input` | [`input/keyboard_input.rs`](./input/keyboard_input.rs) | Demonstrates handling a key press/release
`keyboard_input_events` | [`input/keyboard_input_events.rs`](./input/keyboard_input_events.rs) | Prints out all keyboard events
`keyboard_modifiers` | [`input/keyboard_modifiers.rs`](./input/keyboard_modifiers.rs) | Demonstrates using key modifiers (ctrl, shift)
`mouse_input` | [`input/mouse_input.rs`](./input/mouse_input.rs) | Demonstrates handling a mouse button press/release
`mouse_input_events` | [`input/mouse_input_events.rs`](./input/mouse_input_events.rs) | Prints out all mouse events (buttons, movement, etc.)
`touch_input` | [`input/touch_input.rs`](./input/touch_input.rs) | Displays touch presses, releases, and cancels
`touch_input_events` | [`input/touch_input_events.rs`](./input/touch_input_events.rs) | Prints out all touch inputs

## Reflection

Example | File | Description
--- | --- | ---
`reflection` | [`reflection/reflection.rs`](reflection/reflection.rs) | Demonstrates how reflection in Bevy provides a way to dynamically interact with Rust types
`generic_reflection` | [`reflection/generic_reflection.rs`](reflection/generic_reflection.rs) | Registers concrete instances of generic types that may be used with reflection
`reflection_types` | [`reflection/reflection_types.rs`](reflection/reflection_types.rs) | Illustrates the various reflection types available
`trait_reflection` | [`reflection/trait_reflection.rs`](reflection/trait_reflection.rs) | Allows reflection with trait objects

## Scene

Example | File | Description
--- | --- | ---
`scene` | [`scene/scene.rs`](./scene/scene.rs) | Demonstrates loading from and saving scenes to files

## Shaders

Example | File | Description
--- | --- | ---
`animate_shader` | [`shader/animate_shader.rs`](./shader/animate_shader.rs) | Shows how to animate a shader by accessing a time uniform variable
`array_texture` | [`shader/array_texture.rs`](./shader/array_texture.rs) | Illustrates how to create a texture for use with a texture2DArray shader uniform variable
`hot_shader_reloading` | [`shader/hot_shader_reloading.rs`](./shader/hot_shader_reloading.rs) | Illustrates how to load shaders such that they can be edited while the example is still running
`mesh_custom_attribute` | [`shader/mesh_custom_attribute.rs`](./shader/mesh_custom_attribute.rs) | Illustrates how to add a custom attribute to a mesh and use it in a custom shader
`shader_custom_material` | [`shader/shader_custom_material.rs`](./shader/shader_custom_material.rs) | Illustrates creating a custom material and a shader that uses it
`shader_defs` | [`shader/shader_defs.rs`](./shader/shader_defs.rs) | Demonstrates creating a custom material that uses "shaders defs" (a tool to selectively toggle parts of a shader)

## Tests

Example | File | Description
--- | --- | ---
`how_to_test_systems` | [`../tests/how_to_test_systems.rs`](../tests/how_to_test_systems.rs) | How to test systems with commands, queries or resources

## Tools

Example | File | Description
--- | --- | ---
`bevymark` | [`tools/bevymark.rs`](./tools/bevymark.rs) | A heavy workload to benchmark your system with Bevy

## UI (User Interface)

Example | File | Description
--- | --- | ---
`button` | [`ui/button.rs`](./ui/button.rs) | Illustrates creating and updating a button
`font_atlas_debug` | [`ui/font_atlas_debug.rs`](./ui/font_atlas_debug.rs) | Illustrates how FontAtlases are populated (used to optimize text rendering internally)
`text` | [`ui/text.rs`](./ui/text.rs) | Illustrates creating and updating text
`text_debug` | [`ui/text_debug.rs`](./ui/text_debug.rs) | An example for debugging text layout
`ui` | [`ui/ui.rs`](./ui/ui.rs) | Illustrates various features of Bevy UI

## Window

Example | File | Description
--- | --- | ---
`clear_color` | [`window/clear_color.rs`](./window/clear_color.rs) | Creates a solid color window
`multiple_windows` | [`window/multiple_windows.rs`](./window/multiple_windows.rs) | Creates two windows and cameras viewing the same mesh
`scale_factor_override` | [`window/scale_factor_override.rs`](./window/scale_factor_override.rs) | Illustrates how to customize the default window settings
`window_settings` | [`window/window_settings.rs`](./window/window_settings.rs) | Demonstrates customizing default window settings

# Platform-Specific Examples

## Android

### Setup

```sh
rustup target add aarch64-linux-android armv7-linux-androideabi
cargo install cargo-apk
```

The Android SDK must be installed, and the environment variable `ANDROID_SDK_ROOT` set to the root Android `sdk` folder.

When using `NDK (Side by side)`, the environment variable `ANDROID_NDK_ROOT` must also be set to one of the NDKs in `sdk\ndk\[NDK number]`.

### Build & Run

To run on a device setup for Android development, run:

```sh
cargo apk run --example android
```

:warning: At this time Bevy does not work in Android Emulator.

When using Bevy as a library, the following fields must be added to `Cargo.toml`:

```toml
[package.metadata.android]
build_targets = ["aarch64-linux-android", "armv7-linux-androideabi"]
target_sdk_version = 29
min_sdk_version = 16
```

Please reference `cargo-apk` [README](https://crates.io/crates/cargo-apk) for other Android Manifest fields.

### Old phones

Bevy by default targets Android API level 29 in its examples which is the <!-- markdown-link-check-disable -->
[Play Store's minimum API to upload or update apps](https://developer.android.com/distribute/best-practices/develop/target-sdk). <!-- markdown-link-check-enable -->
Users of older phones may want to use an older API when testing.

To use a different API, the following fields must be updated in Cargo.toml:

```toml
[package.metadata.android]
target_sdk_version = >>API<<
min_sdk_version = >>API or less<<
```

Example | File | Description
--- | --- | ---
`android` | [`android/android.rs`](./android/android.rs) | The `3d/3d_scene.rs` example for Android

## iOS

### Setup

```sh
rustup target add aarch64-apple-ios x86_64-apple-ios
cargo install cargo-lipo
```

### Build & Run

Using bash:

```sh
cd examples/ios
make run
```

In an ideal world, this will boot up, install and run the app for the first
iOS simulator in your `xcrun simctl devices list`. If this fails, you can
specify the simulator device UUID via:

```sh
DEVICE_ID=${YOUR_DEVICE_ID} make run
```

If you'd like to see xcode do stuff, you can run

```sh
open bevy_ios_example.xcodeproj/
```

which will open xcode. You then must push the zoom zoom play button and wait
for the magic.

The Xcode build GUI will by default build the rust library for both
`x86_64-apple-ios`, and `aarch64-apple-ios` which may take a while. If you'd
like speed this up, you update the `IOS_TARGETS` User-Defined environment
variable in the "`cargo_ios` target" to be either `x86_64-apple-ios` or
`aarch64-apple-ios` depending on your goal.

Note: if you update this variable in Xcode, it will also change the default
used for the `Makefile`.

Example | File | Description
--- | --- | ---
`ios` | [`ios/src/lib.rs`](./ios/src/lib.rs) | The `3d/3d_scene.rs` example for iOS

## WASM

### Setup

```sh
rustup target add wasm32-unknown-unknown
cargo install wasm-bindgen-cli
```

### Build & Run

Following is an example for `headless_wasm`. For other examples in wasm/ directory,
change the `headless_wasm` in the following commands **and edit** `examples/wasm/index.html`
to point to the correct `.js` file.

```sh
cargo build --example headless_wasm --target wasm32-unknown-unknown --no-default-features
wasm-bindgen --out-dir examples/wasm/target --target web target/wasm32-unknown-unknown/debug/examples/headless_wasm.wasm
```

Then serve `examples/wasm` dir to browser. i.e.

```sh
basic-http-server examples/wasm
```

Example | File | Description
--- | --- | ---
`hello_wasm` | [`wasm/hello_wasm.rs`](./wasm/hello_wasm.rs) | Runs a minimal example that logs "hello world" to the browser's console
`assets_wasm` | [`wasm/assets_wasm.rs`](./wasm/assets_wasm.rs) | Demonstrates how to load assets from wasm
`headless_wasm` | [`wasm/headless_wasm.rs`](./wasm/headless_wasm.rs) | Sets up a schedule runner and continually logs a counter to the browser's console
`winit_wasm` | [`wasm/winit_wasm.rs`](./wasm/winit_wasm.rs) | Logs user input to the browser's console. Requires the `bevy_winit` features
