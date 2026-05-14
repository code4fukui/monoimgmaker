# monoimgmaker

> 日本語のREADMEはこちらです: [README.ja.md](README.ja.md)

A web tool to convert JPG and PNG images into monochrome C language source files, specifically formatted for e-paper displays.

## Demo

**https://github.com/code4fukui/monoimgmaker

The web interface provides a simple area to drag and drop an image file. The conversion happens in the browser, and the resulting C source file is downloaded automatically.

## Features

-   **Web-Based:** No installation required; runs entirely in your browser.
-   **Drag and Drop:** Simple and fast user interface.
-   **Supports Common Formats:** Converts JPG and PNG files.
-   **E-Paper Ready:** Generates a `const unsigned char gImage_7in5_V2[]` array, a common format for 7.5" e-paper display libraries.
-   **Monochrome Conversion:** Converts images to 1-bit black and white data using a fixed threshold on the green channel (`G < 100`).

## How to Use

1.  Open the [demo page](https://code4fukui.github.io/monoimgmaker/) in your browser.
2.  Drag and drop a JPG or PNG image file onto the designated area.
3.  The converted C source file, `ImageData.c`, will be downloaded automatically.

**Important:** This tool generates a C array with a hardcoded size of 48,000 bytes. Your input image must have dimensions that produce this exact size (e.g., 800x480 pixels, since `800 * 480 / 8 = 48000`).

## Example Output

The generated `ImageData.c` file will contain the following structure:

```c
#include "ImageData.h"
const unsigned char gImage_7in5_V2[48000] = {
0x00, 0x01, /* ... more byte data ... */
};
```

## Acknowledgments

-   **App:** Created by [Taisuke Fukuno](https://twitter.com/taisukef) ([fukuno.jig.jp](https://fukuno.jig.jp/3448))
-   **UI Design:** Based on [Bootstrap](https://getbootstrap.com/)

## License

MIT License - see [LICENSE](LICENSE).