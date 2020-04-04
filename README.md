# PathTracer

## Description
Creating a small path tracer (currently just a ray tracer).

## Features
- Spatial data structure: BVH using axis aligned bounding boxes. Defaults to using the surface area heuristic during construction.
- Blinn-phong illumination with reflection and refraction
- Supported shapes: triangle, sphere
- Supported lights: point, directional, area (defaults to 16 samples per area light for soft shadows)
- 3D model loading via Assimp
- Environment maps
- Configurable multisample anti-aliasing patterns
- Tonemapping and gamma correction
- Diffuse textures (no texture filtering/anti-aliasing yet)

## Configuring
Tested on GCC9 and MSVC 2019
```
git clone https://github.com/LiamTyler/PathTracer.git
cd PathTracer
mkdir build
cd build
(linux) cmake -DCMAKE_BUILD_TYPE=[Debug/Release] ..
(windows) cmake -G "Visual Studio 16 2016" -A x64 ..
```

## Building
Tested on GCC9 and MSVC 2019

Any platform:
```
cmake --build . --config [Debug/Release]
```

Linux specifc:
```
make -j6
```
Note: With GCC9 a full parallel build (make -j) freezes during the assimp build on my machine. Just lower the number if it does freeze

Windows:
Just open build/PathTracer.sln and build there

## Running
```
./bin/pathTracer[_debug] <path to scene file> (ex: ../resources/scenes/cornell.json)
```

## Example Output:
resources/scenes/cornell.json
![Alt text](docs_and_images/cornell.png)

resources/scenes/dragon.json
![Alt text](docs_and_images/dragon.png)
