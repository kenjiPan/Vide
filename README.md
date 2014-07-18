Vide
====

Easy as hell responsive video background.

Minified version size: ~3kb

## Notes

* All modern browsers are supported.
* IE9+

## Instructions

Download it from [GitHub](https://github.com/VodkaBears/Vide/archive/master.zip) or via Bower:
`bower install vide`

Add scripts:
```html
<script src="//ajax.googleapis.com/ajax/libs/jquery/1.11.1/jquery.min.js"></script>
<script src="js/jquery.vide.min.js"></script>
```

Prepare your video in several formats like '.webm' and 'mp4' for cross browser compability, also you can add a poster:
```
path/
├── to/
│   ├── video.mp4
│   ├── video.webm
│   └── video.png
```

Add `data-vide-bg` attribute with a path to the video and poster without extension, video and poster must have the same name. Add `data-vide-options` to pass vide options, if you need it. By default video is muted, looped and starts automaticly.
```html
<div style="width: 1000px; height: 500px; margin: 0;"
    data-vide-bg="path/to/video">
</div>
```
```html
<body style="width: 100%; height: 100%; margin: 0;"
    data-vide-bg="path/to/video" data-vide-options="muted: false, volume: 0.5">
</body>
```
```html
<div style="width: 1000px; height: 500px; margin: 0;"
    data-vide-bg="path/to/video" data-vide-options="position: 0% 50%">
</div>
```

Or you can initialize it with JS, in some situations it can be helpful, because vide doesn't have mutation observers, they are on you own:
```js
$("#myBlock1").vide("path/to/video");
$("#myBlock2").vide("path/to/video", {
...options...
});
```

Easy as hell.

## Options

Below a complete list of options and matching default values:

```js
$("#yourElement").vide({
    volume: 1,
    playbackRate: 1,
    muted: true,
    loop: true,
    autoplay: true,
    position: "50% 50%" // Alignment
});
```

## Methods

Below a complete list of medhods:

```js
// Get instance of the plugin
var instance = $("#yourElement").data("vide");

// Get video element of the background. Do what you want.
instance.getVideoObject();

// Resize video background. It calls automatically if window resize or element(if you will use something like https://github.com/cowboy/jquery-resize).
instance.resize();

// Destroy plugin instance
instance.destroy();
```

## Resizing

Vide plugin resizes, if window resizes. If you will use something like https://github.com/cowboy/jquery-resize, it will resize automatically, when element will resize. Or simply use `resize()` method whenever you need.

## License

The MIT License (MIT)

Copyright (c) 2014 Ilya Makarov, http://vodkabears.github.io

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
