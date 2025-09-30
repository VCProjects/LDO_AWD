# LDO CNC AWD Kit <sub>by Mastur_Mynd and aTinyShellScript</sub>
CNC drive frames for the [Voron Trident](https://github.com/VoronDesign/Voron-Trident) and [Voron V2.4](https://github.com/VoronDesign/Voron-2)

![VT_rear_b_outer](Voron-Trident/IMG/Renders_by_hartk/rear_b_outer.png)

## Key Features
* Metal! - Improved heat dissipation of stepper motors at higher current
* Shorter effective belt length between toolhead and drive gear - Improves max acceleration, input shaper results and accuracy during direction change.
* Double shear shaft support - Allows for increased tension without deflecting the drive shaft
* Backwards compatible - Any toolhead or XY joint that was designed for the Voron Trident or Voron V2.4 will work! Keep in mind that different toolhead geometries may result in loss of travel near the front motor mounts.
* (Voron V2.4 only) Live shaft idlers - Like toothed idlers but utilizing more robust bearings for longevity

## Vendors
* [DREMC (AU)](https://store.dremc.com.au/products/ldo-voron-cnc-awd-kit-v2-4-trident)
* [3d lab tech (CA)](https://www.3dlabtech.ca/)
* [MYRIGS (FR)](https://myrigs3d.com/products/ldo-cnc-all-wheel-drive-kit-for-voron-v2-4-and-trident)
* [Partner 3D (GE)](https://partner-3d.de/)
* [Levendigs (NE)](https://levendigs.com/)
* [onetwo3D (UK)](https://www.onetwo3d.co.uk/product/ldo-voron-awd-all-wheel-drive-upgrade-kit/)
* [123-3D (UK)](https://www.123-3d.co.uk/) subsidiary of [H|2|E Commerce](https://h2ecommerce.com/)
* [Fabreeko (US)](https://www.fabreeko.com/products/ldo-cnc-all-wheel-drive-kit-for-voron-v2-4-and-trident)
* KB3D (US) [Voron Trident](https://kb-3d.com/store/voron/6134-pre-order-ldo-cnc-awd-conversion-kit-for-voron-trident-1757455457877.html) [Voron V2.4](https://kb-3d.com/store/motion/6133-pre-order-ldo-cnc-awd-conversion-kit-for-voron-v24-1757455457079.html)
* [West3D (US)](https://west3d.com/products/ldo-voron-cnc-awd-kit-v2-4-or-trident)

This kit was designed and tested in collaboration with LDO Motors. Kits produced by other manufacturers have not been vetted and may not have the same standard of quality.

## Belt Tensioning
While not required, ensuring your A and B belts are the same length will make tensioning easier.

1. Home your printer. `G28`
	* For the Voron V2 you will also need to perform a quad gantry level. `QUAD_GANTRY_LEVEL`
2. Raise the toolhead (or lower the bed) to prevent the nozzle from marring the build surface. `G0 Z+25`
3. Disable your A and B motors
   ```
   SET_STEPPER_ENABLE STEPPER=stepper_x ENABLE=0
   SET_STEPPER_ENABLE STEPPER=stepper_x1 ENABLE=0
   SET_STEPPER_ENABLE STEPPER=stepper_y ENABLE=0
   SET_STEPPER_ENABLE STEPPER=stepper_y1 ENABLE=0
   ```
4. Loosen the grub screws holding the front drive pulleys to the motor shaft. Ensure that the pulleys are able to move freely from the shaft.
5. Move your toolhead to the center of the bed
6. Adjust tension on each belt path using the M5 SHCS in the tensioner block. Try to adjust tension evenly across the two belt paths, reducing adjustments as you get closer to your desired tension
7. Move the toolhead in the X and Y directions to make sure it is moving freely.
8. Enable your A and B motors. This will send them to the nearest full step which will sync the motors and pulleys in the next step.
   ```
   SET_STEPPER_ENABLE STEPPER=stepper_x ENABLE=1
   SET_STEPPER_ENABLE STEPPER=stepper_x1 ENABLE=1
   SET_STEPPER_ENABLE STEPPER=stepper_y ENABLE=1
   SET_STEPPER_ENABLE STEPPER=stepper_y1 ENABLE=1
   ```
9. Tighten the grub screws holding the front drive pulleys to the motor shaft. Ensure that none of the grub screws are along the flat when using a D cut shaft motor.

## Credit and Attribution
**Lead Designer**\
Mastur_Mynd

**Lead Design Consultant**\
aTinyShellScript

**Project Coordinator**\
JasonFromLDO

**Design Consultant**\
CameronFromLDO\
DaveFromLDO

**Production**\
LDO Motors

**Testing**\
hartk\
JoseFromLDO us\
joshmurrah\
Kittie Katt\
Reth\
ThessienDSD

**Base Design**\
Voron Design Team
