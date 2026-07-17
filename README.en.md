# RQSHC V64I

[日本語](README.md)

RQSHC V64I is experimental image-compression software for Windows. It converts images into the original `.rqi` format and lets users observe output size, reconstruction quality, and processing time.

Processing is performed on the user's PC. The applications are not designed to upload source images to an external cloud service for compression.

## Currently supported formats

### Input

- PNG (`.png`)
- PPM (`.ppm`)
- Windows Bitmap (`.bmp`)

JPEG, WebP, GIF, TIFF, and other image formats are not currently accepted as input. Convert unsupported images to PNG, PPM, or BMP before using the Observatory.

### Output

- The original RQI format (`.rqi`)
- PNG export from RQI Viewer

RQI is not directly supported by ordinary image applications, so use the included `RQI_Viewer.exe` to open it.

## Included applications

### RQSHC_Observatory.exe

Loads PNG, PPM, and BMP images, creates RQI files, and displays original size, output size, reduction ratio, quality, and processing time.

### RQI_Viewer.exe

A Windows viewer for RQI files.

- Open files by drag and drop
- Zoom with `Ctrl + mouse wheel`
- Scroll vertically with the mouse wheel
- Scroll horizontally with `Shift + mouse wheel`
- Pan by left-dragging the image
- Fit to window and 100% view
- Export as PNG
- Copy to the clipboard
- Switch instantly between Japanese and English

On first launch, the Viewer follows the Windows display language where possible. It stores only the selected interface language, not images or viewing history.

## Usage

1. Extract the ZIP archive.
2. Run `RQSHC_Observatory.exe` to compress an image.
3. Add a PNG, PPM, or BMP file and start compression.
4. Drag the resulting `.rqi` file onto `RQI_Viewer.exe` to view it.
5. Export to PNG only when needed.

Always keep the original copy of important images.

## Why I built it

The project started from a desire to explore the relationship between size reduction, reconstruction quality, and processing speed without simply calling an existing image-compression library.

RQSHC is not merely a front end for an existing image compressor. The core RQI compression and decoding paths are original native C++17 implementations, with selected x64 assembly and AVX2 optimizations in performance-critical areas.

The project uses Windows APIs and the C++ standard library, but the core compression and decoding work is not delegated to a third-party image codec. Image data and the RQI container are handled directly at the binary level.

AI has been used to assist implementation, testing, debugging, and documentation. Architecture, technical constraints, evaluation criteria, acceptance and rejection decisions, and disclosure boundaries are directed by the project designer.

## Current benchmark example

On the internal 14-image development test set, V64I recorded the following averages:

- Processing time: approximately 64.8 ms
- Size reduction: approximately 33.49%
- SSIM: approximately 0.999537

Results vary with image content, resolution, input format, CPU, and system conditions. These figures are not guaranteed for every image.

## Feedback

Feedback is especially welcome on:

- image types where compression performs well or poorly
- processing time on different AVX2-capable CPUs
- RQI Viewer usability
- reconstruction quality and compatibility
- reproducible bug reports
- benchmarks that include test conditions

Negative results are useful too, including files that compress poorly, become larger, or fail to display.

## Windows SmartScreen

The binaries are currently unsigned. Windows Defender SmartScreen may therefore show an “unrecognized app” or “unknown publisher” warning on first launch.

This does not necessarily mean that malware was detected. SmartScreen may also warn about new unsigned applications that do not yet have established publisher or download reputation. Download only from the official GitHub Releases page and verify the published SHA-256 hash.

There is no need to disable Windows Defender or other security software.

## Requirements

- 64-bit Windows 10 or Windows 11
- x64 CPU
- AVX2-capable CPU recommended
- A current desktop web browser for the Observatory interface

## Current limitations

- Input is limited to PNG, PPM, and BMP
- Windows 64-bit only
- RQI requires the included RQI Viewer
- As a research build, it does not make every image smaller
- The compression core is currently closed source

## Use and evaluation

Personal use, education, research, evaluation by universities and research institutions, and internal company evaluation or proof of concept are free. Publication of benchmarks, articles, videos, social-media posts, and papers is welcomed.

Separate permission is required for integration into commercial products, SaaS or API delivery, paid customer processing, or development of an RQI-compatible product.

See [LICENSE.txt](LICENSE.txt) for the full terms.

Contact
For comments, work, and collaborations, please contact us here and If you want to use it for commercial purposes, please contact me

murakami3tech6compres9sion@gmail.com

discord: [https://discord.gg/5G7VRjGEqf](https://discord.gg/GaFVFcrb)

X: @nagisa7654321

Zenn: https://zenn.dev/eiryou369/articles/4212b23bf1dcd3
## Privacy and disclaimer

See [PRIVACY.md](PRIVACY.md) and [DISCLAIMER.md](DISCLAIMER.md).

Copyright (c) 2026 Hideyoshi Murakami / RQSHC Project
