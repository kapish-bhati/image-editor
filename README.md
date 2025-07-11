# 🖼️ Image Filter Suite – CS50 Project

This repository contains multiple image filtering algorithms implemented in **C** as part of the **CS50x** curriculum from **Harvard University**. Each filter applies a specific transformation to images represented as 2D arrays of RGB pixels.

## 📌 Project Objective

To understand how images are represented in memory and manipulate their pixels using classic image processing techniques like **grayscale**, **sepia**, **blur**, **edge detection**, **reflection**, and more.

---

## 📁 Files Included

* `helpers.c`: Contains implementations of various filters.
* `helpers.h`: Header file defining structures and function prototypes.
* `filter.c`: Main program that applies chosen filters based on command-line input.
* BMP images (before and after filters) – optional test assets.

---

## ✨ Features & Filters Implemented

### ✅ 1. Grayscale Filter

Converts a color image to shades of gray by averaging the red, green, and blue values of each pixel.

**Formula:**

```c
gray = round((red + green + blue) / 3.0);
```

### ✅ 2. Sepia Filter

Applies a warm, antique tone by transforming RGB values with weighted formulas.

**Formula:**

```c
sepiaRed   = 0.393*R + 0.769*G + 0.189*B
sepiaGreen = 0.349*R + 0.686*G + 0.168*B
sepiaBlue  = 0.272*R + 0.534*G + 0.131*B
```

### ✅ 3. Reflect Horizontally

Flips the image across a vertical axis — like mirroring it left to right.

**Logic:**
Swaps each pixel in a row with its corresponding pixel from the end.

### ✅ 4. Blur (Box Blur)

Softens the image by averaging each pixel’s RGB values with its neighboring pixels (3×3 box kernel).

**Steps:**

* Use a temporary buffer to store new values.
* For each pixel, calculate the average of itself and all surrounding pixels that are in bounds.

### ✅ 5. Edge Detection (Sobel Operator)

Highlights areas where there’s a significant color intensity change — i.e., edges.

**Approach:**

* Apply two 3×3 kernels: **Gx** and **Gy** (Sobel operators for x and y direction).
* Compute:

  ```c
  G = sqrt(Gx² + Gy²);
  ```
* Clamp RGB values to 255.

---

## 🧪 How to Run

1. **Install CS50 Library (if needed):**

   ```bash
   brew install cs50  # for Mac
   ```

2. **Compile:**

   ```bash
   make filter
   ```

3. **Run the filter:**

   ```bash
   ./filter -g images/lenna.bmp output.bmp   # grayscale
   ./filter -s images/lenna.bmp output.bmp   # sepia
   ./filter -r images/lenna.bmp output.bmp   # reflect
   ./filter -b images/lenna.bmp output.bmp   # blur
   ./filter -e images/lenna.bmp output.bmp   # edge
   ```

> *Use a BMP image as input (24-bit uncompressed BMP 4.0).*

---

## 💡 Concepts & Skills Learned

* **Working with structs** (RGBTRIPLE) to represent pixels
* **Pointer arithmetic** and multi-dimensional arrays
* **Image transformations** via kernel-based filters
* **Edge detection** using the Sobel operator
* **Boundary checking** for pixels on edges/corners
* **Memory safety** and avoiding data corruption during updates

---

## 🔍 Sample Output Preview

| Filter      | Example Preview     |
| ----------- | ------------------- |
| Grayscale   | `lenna-gray.bmp`    |
| Sepia       | `lenna-sepia.bmp`   |
| Reflect     | `lenna-reflect.bmp` |
| Blur        | `lenna-blur.bmp`    |
| Edge Detect | `lenna-edge.bmp`    |

---

## 👨‍💻 Author

**Kapish Bhati**
*CS50 Student | Systems & Algorithms Enthusiast*
Completed as part of [CS50: Introduction to Computer Science](https://cs50.harvard.edu/x/)

