# SVG `transform-origin` attribute

This page shows usage examples of SVG `transform-origin` attribute.

It's purpose is to demonstrate Safari's [Bug #201854](https://bugs.webkit.org/show_bug.cgi?id=201854).

Image in Figure 1 is composed from SVG primitives without any transform appplied to them. It's a reference image.

All other images are recreating the reference image with usage of transform. All those images should look the same. They look the same in Chrome and Firefox. In Safari images in section 2 and 4 are broken. It seems like `transform-origin` attribute is applied only to transformations defined in `transform` CSS property, but not in `transform` SVG attribute.

For example, this is broken in Safari
```svg
<use href="#target" fill="blue" transform="scale(0.75 0.75)" transform-origin="100 100"/>
```
while this is rendered correctly
```svg
<use href="#target" fill="blue" style="transform: scale(0.75, 0.75);" transform-origin="100 100"/>
```

## License

[![CC0-1.0](https://licensebuttons.net/l/zero/1.0/80x15.png) Creative Commons Zero 1.0 Universal (CC0 1.0) Public Domain Dedication](http://creativecommons.org/publicdomain/zero/1.0/)
