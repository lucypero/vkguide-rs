---
layout: default
title: Project Layout and Crates
parent: Introduction
has_children: false
nav_order: 2
---

# Project layout
For the Vulkan engine, we use a specific folder layout.

`/assets` will contain textures and 3d models that we use over the guide

`/shaders` will contain all our shaders, and their compiled output

# Crates
On the engine, we use a set of crates.

The crates we are using:

[nalgebra-glm](https://crates.io/crates/nalgebra-glm) Mathematics library. We use this for its matrix and vector math functionality. It’s a library that contains types that are directly compatible with GLSL types in most cases. For example, a `Mat4` has similar operations and is directly compatible with a `mat4` in a shader. While it says OpenGL in the name, it works great with Vulkan.

[winit](https://crates.io/crates/winit) Windowing and input library. We use it in the project to have a easy and fast way to open a window, and have detailed keyboard input.

[egui](https://crates.io/crates/egui) Easy to use immediate Graphical-User-Interface (GUI) library. This allows us to create editable widgets such as sliders and windows for the user interface. It’s widely used in the game industry for debug tools. In the project, we use it to create interactive options for rendering.

[vk-mem](https://crates.io/crates/vk-mem) Rust wrapper for VMA (Vulkan Memory Allocator). Implements memory allocators for Vulkan. In Vulkan, the user has to deal with the memory allocation of buffers, images, and other resources on their own. This can be very difficult to get right in a performant and safe way. Vulkan Memory Allocator does it for us and allows us to simplify the creation of images and other resources. Widely used in personal Vulkan engines or smaller scale projects like emulators. Very high end projects like Unreal Engine or AAA engines write their own memory allocators.