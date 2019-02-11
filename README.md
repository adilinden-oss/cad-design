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
    * Initial Layer Flow                        103%
- Speed
    * Initial Layer Print Speed                 20mm/s
    * Enable Acceleration Control
    * Print Acceleration                        300mm/s
    * Enable Jerk Control
    * Print Jerk                                5mm/s

### Printer

- Start G Code

        ; Ender 3 Custom Start G-code
        G28 ; Home all axes
        G92 x-6.5 Y-13 ; Apply offset specific to MY printer
        G92 E0 ; Reset Extruder
        G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
        G1 X-1 Y20 Z0.3 F5000.0 ; Move to start position
        G1 X-1 Y200.0 Z0.3 F1500.0 E15 ; Draw the first line
        G1 X-0.7 Y200.0 Z0.3 F5000.0 ; Move to side a little
        G1 X-0.7 Y20 Z0.3 F1500.0 E30 ; Draw the second line
        G92 E0 ; Reset Extruder
        G1 Z2.0 F3000 ; Move Z Axis up little to prevent scratching of Heat Bed
        ; End of custom start GCode

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

- Colours: orange
- Bed
    * Initial Temp  70
    * Temperature   60
-Nozzle
    * Initial Temp  190
    * Temperature   190

**Amazon Basics Filament**

- Colours: grey
- Bed
    * Initial Temp  70
    * Temperature   60
- Nozzle
    * Initial Temp  225
    * Temperature   225

