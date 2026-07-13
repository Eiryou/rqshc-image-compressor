# RQSHC V64I

[日本語](README.md)

RQSHC V64I is experimental image-compression software for Windows. It converts images into the original `.rqi` format and lets users observe output size, reconstruction quality, and processing time.

Processing is performed on the user's PC. The applications are not designed to upload source images to an external cloud service for compression.

## Included applications

### RQSHC_Observatory.exe

Loads images, creates RQI files, and displays original size, output size, reduction ratio, quality, and processing time.

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
2. Run `RQSHC_Observatory.exe` to compress images.
3. Drag an `.rqi` file onto `RQI_Viewer.exe` to view it.
4. Export to PNG only when needed.

Always keep the original copy of important images.

## Development approach

RQSHC is not merely a front end that calls an existing image compressor. The core RQI compression and decoding paths are original native C++17 implementations, with selected x64 assembly and AVX2 optimizations in performance-critical areas.

The project uses Windows APIs and the C++ standard library, but the core compression and decoding work is not delegated to a third-party image codec. Image data and the RQI container are handled at the binary level, with emphasis on balancing size reduction, reconstruction quality, and processing speed.

AI has been used to assist implementation, testing, debugging, and documentation. Architecture, technical constraints, evaluation criteria, acceptance and rejection decisions, and disclosure boundaries are directed by the project designer.

## Requirements

- 64-bit Windows 10 or Windows 11
- x64 CPU
- AVX2-capable CPU recommended
- A current desktop web browser for the Observatory interface

## Use and evaluation

Personal use, education, research, evaluation by universities and research institutions, and internal company evaluation or proof of concept are free. Publication of benchmarks, articles, videos, social-media posts, and papers is welcomed.

Separate permission is required for integration into commercial products, SaaS or API delivery, paid customer processing, or development of an RQI-compatible product.

See [LICENSE.txt](LICENSE.txt) for the full terms.

## Privacy and disclaimer

See [PRIVACY.md](PRIVACY.md) and [DISCLAIMER.md](DISCLAIMER.md).

Copyright (c) 2026 Hideyoshi Murakami / RQSHC Project
