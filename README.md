# OpenScad for Teachers
##### stachan 11.02.2024, License: CC-BY-SA-4.0
---
## Downloads
- [OpenScad](https://openscad.org/)
- [Ultimaker Cura](https://ultimaker.com/de/software/ultimaker-cura/)

## Links & Tutorials
- [OpenScad Tutorial](https://openscad.org/documentation.html#tutorial)
- [OpenScad Cheatsheet](https://openscad.org/cheatsheet/)

## Files
- [STC_3D_1ABEHIF_CABS1.pdf](https://github.com/wasp1337/openscad4teachers/files/14231742/STC_3D_1ABEHIF_CABS1.pdf)
- [STC_3D-Druck_STC_2022.pdf](https://github.com/wasp1337/openscad4teachers/files/14231756/STC_3D-Druck_STC_2022.pdf)

## Lesson Plan CABS1 (HIF, 1U/week)
### Lesson #1 - Theory
([STC_3D-Druck_STC_2022.pdf](https://github.com/wasp1337/openscad4teachers/files/14231756/STC_3D-Druck_STC_2022.pdf))
### Lesson #2 - Basic 3D
```
cube(10);
cube([25,35,55]);
cube([20,30,50],center=true);
sphere(r=10);
cylinder(h=3,r=8);
```
```
translate([x,y,z])
```
### Lesson #3 - Transformation, Boolean, Variables
```
translate([x,y,z])
rotate([x,y,z])
resize([x,y,z])
scale([x,y,z])
```
```
union(){ }
difference(){ }
intersection(){ }
```
```
i=8;
cube(i);
```
