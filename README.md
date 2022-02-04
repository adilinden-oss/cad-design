# CAD Designs for 3D Printing

Just sharing my CAD designs for 3D printing. For now I am using Autodesk Fusion 360.

## My Cura Settings

For reference, these are my preferred settings in Cura.

### Settings

- Quality
    * Initial Layer Height
- Material
    * Printing Temperature Initial Layer
    * Build Plate Temperature                   60
    * Build Plate Temperature Initial Layer     70
    * Flow                                      100%
    * Initial Layer Flow                        100%
- Speed
    * Print Speed                               50mm/s
    * Initial Layer Print Speed                 20mm/s
    * Enable Acceleration Control
    * Print Acceleration                        300mm/s
    * Enable Jerk Control
    * Print Jerk                                5mm/s
- Travel
    * Enable Retraction
    * Retraction Distance                       5.0mm
    * Retraction Speed                          25mm/s
- Support (When enabled)
    * Support Density                           5% - 15%
    * Support Z Distance                        ~ 1.1 x layer height

### Printer

- Start G Code

        ; Ender 3 Custom Start G-code
        G28 ; Home all axes
        G92 X-6.5 Y-13 ; Apply offset specific to MY printer
        G92 E0 ; Reset Extruder
        G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
        G1 X0 Y20 Z0.3 F5000.0 ; Move to start position
        G1 X0 Y200.0 Z0.3 F1500.0 E15 ; Draw the first line
        G1 X0.3 Y200.0 Z0.3 F5000.0 ; Move to side a little
        G1 X0.3 Y20 Z0.3 F1500.0 E30 ; Draw the second line
        G92 E0 ; Reset Extruder
        G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
        ; End of custom start GCode

- End G Code

        ; Ender 3 Custom End G-code
        G4 ; Wait
        M220 S100 ; Reset Speed factor override percentage to default (100%)
        M221 S100 ; Reset Extrude factor override percentage to default (100%)
        G91 ; Set coordinates to relative
        G1 F1800 E-3 ; Retract filament 3 mm to prevent oozing
        G1 F3000 Z20 ; Move Z Axis up 20 mm to allow filament ooze freely
        G90 ; Set coordinates to absolute
        
        G1 X0 Y{machine_depth} F1000 ; Move Heat Bed to the front for easy print removal
        M106 S0 ;Turn-off fan
        M104 S0 ;Turn-off hotend
        M140 S0 ;Turn-off bed

        M84 ; Disable stepper motors
        ; End of custom end GCode

- Creality Ender-3
    * X (Width) 220mm
    * Y (Depth) 220mm
    * Z (Height) 250mm

### Materials

**Neat Filament**

- Colours: white, turkois, trans blue
- Bed
    * Initial Temp  70
    * Temperature   60
-Nozzle
    * Initial Temp  210
    * Temperature   200

**AMAZ3D Filament**

- Colours: light brown, purple
- Bed
    * Initial Temp  70
    * Temperature   60
- Nozzle
    * Initial Temp  195
    * Temperature   195

**Hatchbox Filament**

- Colours: orange, silk silver
- Bed
    * Initial Temp  70
    * Temperature   60
-Nozzle
    * Initial Temp  200
    * Temperature   200

**Amazon Basics Filament**

- Note: Not impressed with this stuff, random underextrusion.
- Colours: grey
- Bed
    * Initial Temp  70
    * Temperature   60
- Nozzle
    * Initial Temp  225
    * Temperature   225

