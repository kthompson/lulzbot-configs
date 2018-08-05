# lulzbot-configs

Simplify 3D configs for Lulzbot TAZ 5 with Hatchbox filaments


# Calibration

## Filament diameter

Measure filament in multiple locations, take average and enter into `Other - Filament Diameter` 

## Extrusion width calibration

Print 20mm calibration cube with 2 shells, zero infill, no top or bottom layers. The resulting print should be 2x the desired extrusion width. ie 0.5mm nozzle should result in 1.0mm. 

Take average of widths around the shell three measurements on each side for 12 values. Adjust extrusion multiplier accordingly.

> new extrusion width = (2*nozzle width) * (current extrusion width)/(average measured shell width)

## Full calibration cube

If top layer has gaps, increase `Infill - Overlap Percentage`

Check for dimensions of 20x20mm. Check top layer to make sure no scaring etc.

## Retraction/Bridging Calibration

TODO

# Useful links

* https://www.simplify3d.com/support/print-quality-troubleshooting/
* https://www.thingiverse.com/thing:52946
* http://reprap.org/wiki/G-code



# Other Notes

Start script that should setup temps but doesnt work:
```g-code
M140 S110; [bed0_temperature]
M104 S[extruder0_temperature] T0 ; heat t0 to 240
M190 S110; [bed0_temperature]
M109 S[extruder0_temperature]
```

# Flow rate

> Throughput = Layer Height * Layer Width * Printing Speed

Estimated max throughput is around 8-10 mm^3/s