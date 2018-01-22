# SVG-to-PDFKit
Insert SVG into a PDF document created with PDFKit.

## Install

    npm install svg-to-pdfkit --save

## Use

    let doc = SVGtoPDF(svg, x, y, options);


## Parameters

    svg [SVGElement or string] = the SVG object or XML code
    x, y [number] = the position where the SVG will be added
    options [Object] = >
      - width, height [number] = initial viewport, by default it's the page dimensions
      - preserveAspectRatio [string] = override alignment of the SVG content inside its viewport
      - useCSS [boolean] = use the CSS styles computed by the browser (for SVGElement only)
      - fontCallback [function] = function called to get the fonts, see source code
      - imageCallback [function] = same as above for the images (for Node.js)
      - documentCallback [function] = same as above for the external SVG documents
      - colorCallback [function] = function called to get color, making mapping to CMYK possible
      - warningCallback [function] = function called when there is a warning
      - assumePt [boolean] = assume that units are PDF points instead of SVG pixels
      - precision [number] = precision factor for approximative calculations (default = 3)
      

## Supported
 - shapes: rect, circle, path, ellipse, line, polyline, polygon
 - special elements: use, nested svg
 - text elements: text, tspan, textPath
 - text attributes: x, y, dx, dy, rotate, text-anchor, textLength, word-spacing, letter-spacing, font-size
 - styling: with attributes only
 - colors: fill, stroke & color (rgb, rgba, hex, string), fill-opacity, stroke-opacity & opacity
 - units: all standard units
 - transformations: transform, viewBox & preserveAspectRatio attributes
 - clip paths & masks
 - images
 - fonts
 - gradients
 - patterns
 - links

## Unsupported
 - filters
 - text attributes: font-variant, writing-mode, unicode-bidi
 - foreignObject (<a href="https://github.com/alafr/SVG-to-PDFKit/issues/37">#37</a>)
 - other things I don't even know they exist

## Warning
 - Use an updated PDFKit version (≥0.8.1): see <a href="https://github.com/alafr/pdfkit/wiki/How-to-install-and-build-a-PDFKit-branch">here</a> how to build it, or use the prebuilt file in the <a href="https://github.com/alafr/SVG-to-PDFKit/tree/master/examples">examples</a> folder.
 - There are bugs, please send issues and/or pull requests.

## License
&nbsp; &nbsp; <a href="http://choosealicense.com/licenses/mit/">MIT</a>

## Other useful projects
 - <a href="https://github.com/devongovett/pdfkit">PDFKit</a>, the JavaScript PDF generation library for Node and the browser.
 - For inserting SVG graphics into a PDFKit document there is also <a href="https://github.com/devongovett/svgkit">svgkit</a>.
 - For the opposite conversion, from PDF to SVG, you can use <a href="https://github.com/mozilla/pdf.js">Mozilla's PDF.js</a>.
