# OPENGL TEMPLATE
template for working with opengl (glew, glfw, glm) in c++.
cmake is configured to output executable with the same name of the parent directory.

## INSTALL REQUIREMENTS
```bash
# debian
sudo apt install cmake make g++ libx11-dev libxi-dev libgl1-mesa-dev libglu1-mesa-dev libxrandr-dev libxext-dev libxcursor-dev libxinerama-dev libxi-dev
```

## HOW TO COMPILE
```bash
cd build
cmake ..
make
```

## LIBRARIES VERSION
|library|version|
|-------|-------|
|glew   |2.1.0  |
|glfw   |3.3.8  |
|glm    |0.9.9.8|
