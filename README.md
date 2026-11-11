# Depth of field calculator

Open `index.html` in a modern browser. It works offline, with no dependencies, external fonts, network requests or build step.

Defaults: 50 mm, f/1.8, 3 m focus distance and 0.03 mm circle of confusion. Edit any value to recalculate; the button also validates and focuses the first invalid input. 
Select “Focused at infinity” for infinite focus. Results use two decimal places: metres at 1 m and above, centimetres below 1 m, and millimetres below 1 cm. 
Units are selected before rounding; calculations retain full precision. Infinity is explicitly labelled.

## Mathematics

All internal distances are in millimetres. With focal length f, f-number N, circle of confusion c and focus distance s:

- A = f²/(N × c)
- Hyperfocal H = A + f
- Near limit = sA/(A + s − f)
- Far limit = sA/(A − s + f), when s < H; infinity when s ≥ H
- Total depth of field = far − near
- At infinite focus: near = A, far and total = infinity

These are consistent ideal thin-lens expressions, with object distances measured from the front principal plane. 
Many photography references substitute H for A in the limit equations as a practical approximation. 
This calculator retains H − f = A so the infinite far limit occurs exactly at the stated hyperfocal distance. T
he mathematical functions are annotated in the HTML.

The original reference, [Living Optics](https://www.livingoptics.com/glossary/depth-of-field-equation/), introduces the variables and photographic context. 
Its displayed limit formulas use the common approximation; its worked example also omits the +f term from the hyperfocal arithmetic. 
Consequently, results may differ slightly.

A circle of confusion is a chosen sharpness criterion, not a fixed sensor property. 
Results do not model diffraction, focus breathing, pupil magnification, tilted lenses or real-lens macro behaviour. 
Camera distance markings may use the sensor plane rather than the principal plane assumed here.

Inputs must be positive and finite, and finite focus distance must exceed focal length. Values outside numerical precision produce an error instead of a misleading result. 
No diagrams or presets are included.
