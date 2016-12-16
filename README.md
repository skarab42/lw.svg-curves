# lw.svg-curves
SVG curves for [LaserWeb/CNCWeb](https://github.com/LaserWeb/LaserWeb4).

## Installation
Using NPM
```
npm install lw.svg-curves
```

Using GIT
```
git clone https://github.com/lautr3k/lw.svg-curves.git
cd svg-curves
npm install
```

Or download the last build from https://raw.githubusercontent.com/lautr3k/lw.svg-curves/master/dist/lw.svg-curves.js
```html
<script src="./lw.svg-curves.js"></script>
<script>
  var curves = SVGCurves.Curves();
</script>
```

## Settings (all are optional)
```javascript
let settings = {
    linear       : true, // Linear trace mode
    step         : 0.01, // Step resolution if linear mode = false
    resolution   : 500,  // Number of segments we use to approximate arc length
    segmentLength: 0.1   // Segment length
}
```

## Usages
```javascript
import curves from 'svg-curves'

let tracer = new curves.Arc(settings) // Set settings for this instance
let coords = tracer.trace({ p1, rx, ry, angle, large, sweep, p2 })

// Or mix settings in constructor
let tracer  = new curves.CubicBezier({ p1, p2, p3, p4, linear: false })
let coords1 = tracer.trace({ step: 0.1 })
let coords2 = tracer.trace({ step: 0.2 })

// new curves.QuadricBezier({ p1, p2, p3 })
```
