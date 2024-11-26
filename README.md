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
