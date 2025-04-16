# GCodeBending
 This is a quick and dirty Python code to deform GCode so that it follows a defined spline.
# Requirements
- ~~GCode needs to be sliced with relative extrusions activated, preferably in PrusaSlicer~~
- Disable G2 and G3 GCODE before slicing or the code will remove these lines and make a mess.
  - Print Settings → Advanced → Slicing → Arc Fitting → Disabled
- You need enough clearance around your nozzle to print significant angles
- The model can't be too large in the X dimension, otherwise you'll get self intersections
# Usage
- Place your part preferably in the middle of your print plate with known center X coordinates
- Place the sliced GCode in the same directory as the Python script
- Set *INPUT_FILE_NAME* to your GCode file name
- Set *LAYER_HEIGHT* to your slicing layer height. Important, because you don't set it correctly you'll get under- or over extrusions
- Set *WARNING_ANGLE* to the maximum angle your system can print at due to clearances
- Set *MINIMUM_EXTRUSION* so that when the script calculates the smaller extrusions it doesn't go into exponents and break your E-motor.
- Define your spline with *SPLINE_X* and *SPLINE_Z* and *SPLINE_ANGLES_DEGREES*
  - SPLINE_X marks each point of the spline on the X axis
  - SPLINE_Z marks each point of the spline of the Z axis
  - SPLINE_ANGLES_DEGREES determines the END angle for each segment of the spline
