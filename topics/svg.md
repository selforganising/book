#SVG, viewBox and path

The `svg` element in a document defines a scalable vector graphic that is embedded in the document. The `path` defines a shape within it.

<svg viewbox="0 0 40 40" style="border:1px solid;">
  <path d="M 10 10 L 30 10 L 20 30 z" fill="red" stroke="blue" stroke-width="1">
</svg>

    <svg viewbox="0 0 40 40">
      <path d="M 10 10 L 30 10 L 20 30 z" fill="red" stroke="blue" stroke-width="1">
    </svg>

The `d` attribute of the `path` contains the data that defines the shape. It contain pairs of numbers to indicate coordinates and the letters `M` to indicate a start point (*moveto*), `L` to indicate the next point to draw to (*lineto*) and `z` to indicate the final point from which to close the shape by returning to the start point.

The `viewbox` attribute of the `svg` element identifies which part of the graphic to draw (it can be just a part of it).

<svg viewbox="15 15 40 40" style="border:1px solid;">
  <path d="M 10 10 L 30 10 L 20 30 z" fill="red" stroke="blue" stroke-width="1">
</svg>

    <svg viewbox="15 15 40 40">
      <path d="M 10 10 L 30 10 L 20 30 z" fill="red" stroke="blue" stroke-width="1">
    </svg>

See [SVG Getting Started tutorial](https://developer.mozilla.org/en-US/docs/Web/SVG/Tutorial/Getting_Started) on mozilla.org, [the viewBox attribute](http://www.w3.org/TR/SVG/coords.html#ViewBoxAttribute) and [paths on w3.org](http://www.w3.org/TR/SVG/paths.html).



  </body>
</html>

