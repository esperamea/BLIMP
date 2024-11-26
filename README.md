# BLIMP
A simple, bitmap-based font format designed for ease of use and minimal complexity. 

BLIMP Specification v1.0
Blimp-Like Image and Metadata Package


---

## Introduction

The BLIMP (Blimp-Like Image and Metadata Package) format is a simple, bitmap-based font file format designed for ease of use and simplicity. It is intended for applications where traditional vector font formats like TrueType (TTF) are unnecessarily complex or resource-intensive. BLIMP provides a straightforward way to store bitmap fonts starting with the full ASCII character set and supports the inclusion of additional Unicode characters as needed.
---

## Overview

BLIMP files encapsulate both the bitmap image data of a font and metadata describing the font's characteristics. The format includes:

- Metadata about the font and its bitmap representation.
- The complete ASCII character set by default (Unicode code points `0x00` to `0x7F`).
- Support for additional Unicode characters through an extended character map.

This format is particularly suitable for embedded systems or applications requiring a simple, bitmap-based font without the overhead of complex font rendering engines.
---

## File Structure

A BLIMP file is composed of the following sections, each serving a specific purpose:

1. [Magic Identifier](#magic-identifier)
2. [Version Header](#version-header)
3. [Metadata Header](#metadata-header)
4. [Character Map](#character-map)
5. [Bitmap Data](#bitmap-data)

### Magic Identifier

- **Size:** 4 bytes  
- **Content:** ASCII characters `"BLMP"`  
- **Purpose:** Identifies the file as a BLIMP format file.

---

### Version Header

- **Size:** 1 byte  
- **Content:** Format version number.  
  - Current version is `0x01`.  
- **Purpose:** Allows for future enhancements and backward compatibility.

---

### Metadata Header

The metadata header provides essential information about the font and its bitmap image.

| Field             | Size (bytes) | Description                                         |
|-------------------|--------------|-----------------------------------------------------|
| Image Width       | 4            | Width of the bitmap image in pixels.                |
| Image Height      | 4            | Height of the bitmap image in pixels.               |
| Character Count   | 4            | Total number of characters included.                |
| Font Size         | 2            | Font size used to render the bitmap (e.g., 16px).   |
| Reserved          | 2            | Reserved for future use (currently set to `0`).     |

- **Image Width and Height:** Define the dimensions of the bitmap image containing all characters.  
- **Character Count:** Includes the default 128 ASCII characters and any additional Unicode characters.  
- **Reserved:** Placeholder for potential future features.

---
