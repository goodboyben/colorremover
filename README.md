# Color Remover
<img width="1293" height="766" alt="Screenshot 2026-03-19 190015" src="https://github.com/user-attachments/assets/46d0e4a9-aed2-4bb6-93b1-055770e5a93c" />

**Website:** [goodboyben.github.io/colorremover](https://goodboyben.github.io/colorremover)

## Overview

Color Remover is a lightweight, browser-based utility designed to remove specific colors from images and replace them with transparency. The application processes images locally using the HTML5 Canvas API, ensuring that data does not leave the user's system.

## Features

* **Interactive Selection:** Users can select a target color directly by clicking on the input image.
* **Similarity Threshold:** A sliding scale (0-100%) allows for the removal of colors within a specific Euclidean distance in the RGB color space.
* **Edge Smoothing:** An optional anti-aliasing toggle applies cubic easing to the alpha transition, reducing jagged edges around the selection.
* **High-Contrast Preview:** A diagnostic mode that renders the image as a binary mask (white for kept pixels, black for removed pixels) to assist in fine-tuning the threshold.
* **Client-Side Processing:** All pixel manipulation is performed in the browser, providing immediate feedback and maintaining privacy.

## Technical Implementation

The tool is contained within a single HTML file and utilizes the following technologies:

* **HTML5 Canvas API:** Used for pixel-level data manipulation (`getImageData`) and rendering the output.
* **Tailwind CSS:** Provides the responsive layout and interface components.
* **Vanilla JavaScript:** Handles the logic for color distance calculations, alpha channel modifications, and file I/O.

### Color Distance Formula

The similarity between the target color and the image pixels is calculated using the Euclidean distance formula:

$$d = \sqrt{(r_2 - r_1)^2 + (g_2 - g_1)^2 + (b_2 - b_1)^2}$$

The threshold is then applied against the maximum possible distance in the RGB cube to determine the transparency of each pixel.

## Usage

1.  **Upload:** Load a local image file (PNG, JPG, or WEBP) into the tool.
2.  **Select:** Click on the specific color in the input image that should be removed.
3.  **Adjust:** Use the threshold slider to expand or contract the range of affected colors.
4.  **Refine:** Toggle "Smooth Edges" to improve the transition between transparent and opaque areas.
5.  **Export:** Download the processed result as a transparent PNG file.
