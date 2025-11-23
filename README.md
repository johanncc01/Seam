# Seam Carving (Content-Aware Image Resizing)

## Clausen Johann, Galhaud Victor


### Project Overview

This project implements the **seam carving** algorithm for content-aware image resizing. Seam carving is a technique to resize images by removing or inserting seams (paths of least importance) in an image, preserving important content and structure. The code is written in C++ and includes modular components for color processing, filtering, seam finding, and image manipulation.

**Key Features:**
- Convert images to grayscale and back to RGB.
- Apply smoothing and Sobel filters for edge detection.
- Find and highlight vertical and horizontal seams.
- Remove seams to resize images.
- Modular design with extensions for horizontal seam carving.
- Unit tests for core functionalities.

---

### Directory Structure

- rendu — Main source code and build files
  - main.cpp — Entry point, runs unit tests and demo functions
  - seam.cpp, seam.h — Core seam carving logic
  - extension.cpp, extension.h — Extensions (e.g., horizontal seams)
  - helper.cpp, helper.h — Image I/O utilities (PNG read/write)
  - unit_test.cpp, unit_test.h — Unit tests for all major functions
  - seam_types.h — Type definitions (images, graphs, paths)
  - Makefile — Build instructions
  - stb_image.h, `stb_image_write.h` — Image library (header-only)
- res — Resources
  - `img/` — Input images
  - `outputs/` — Output images
  - `expected_outputs/` — Reference outputs

---

### Build & Execution Instructions

#### **Requirements**
- C++11 or newer compiler (e.g., `g++`, `clang++`)
- Make
- No external dependencies (uses header-only image libraries)

#### **Build**

Open a terminal in the rendu directory and run:

```sh
make
```

This will build the main executable (`main`), as well as helper binaries.

#### **Run**

To run the main program (which executes unit tests and demo code):

```sh
make run
```
or
```sh
./main
```

**To process a specific image:**
- Place your image in img
- Edit main.cpp to set the desired input/output or uncomment demo/test functions as needed.
- Rebuild and rerun.

#### **Clean Build Files**

```sh
make clean
```

---

### Notes & Troubleshooting

- **Windows users:** If you encounter issues, change the `Node` struct in seam_types.h to use `long double` for `distance_to_target` and `costs`.
- The code is modular; you can extend it by adding new filters or seam strategies in the respective files.
- For horizontal seam carving, use the functions in extension.cpp/extension.h.

### Extensions
1) **Getcol, getrow, getid functions:** These utility functions help modularize the code, making it easier to read and maintain, especially in the graph creation part.
2) **Horizontal Seam Carving:** Implemented functions to create horizontal graphs, find horizontal seams, and highlight them. This allows resizing images horizontally using the same seam carving principles.

---

### References

- Seam carving algorithm: Avidan & Shamir, "Seam Carving for Content-Aware Image Resizing"
- [stb_image](https://github.com/nothings/stb) — Public domain image library
