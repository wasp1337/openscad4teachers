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
// comment
```
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
### Lesson #3 - Transformation, Union, Variables
```
translate([x,y,z])
rotate([x,y,z])
resize([x,y,z])
```
```
union(){ }
```
```
i=8;
cube(i);
```
### Lesson #4 - Cutting, Colors (for fun only)
```
difference(){ }
intersection(){ }
```
```
color("colorname",alpha)
color("#hexvalue")
color([r,g,b,a])
```
### Lesson #5 - Text, Fragmentation, Extrusion
```
text(t,size,font,halign,valign,spacing,direction,language,script);
text("OpenSCAD",size=20,font ="Liberation Sans:style=Bold Italic");
```
```
$fn=100;
```
```
rotate_extrude(angle,convexity)
linear_extrude(height,center,convexity,twist,slices)
```
### Lesson #6 OPTIONAL - Modules, Loops
```
module stc(){ 
	i=5;
	// some object code here
}
stc();
stc(i=8);
```
```
for(x=[-100:20:+100]){
	translate([x,0,0]) cube(10);
}
```
## Everything in 2 examples
```
//Variablen
hoehe=80;
durchmesser=60;
radius=30;
rklein=7;
rgross=25;
var1=10;
var2=50;
var3=100;

//translate([x,y,z]) verschiebt das objekt 

//cube(x);
color("red",1.0) cube(40);
color("blue",1.0) cube(40,center=true);

//cube([x,y,z]);
translate([-200,0,0]) color("blue",1.0) cube([var1,var2,var3]);
//center verschiebt den mittelpunkt des objekts
//cube([x,y,z]);
translate([-200,0,0]) color("red",1.0) cube([var1,var2,var3], center=true);

//cylinder(h=h,d=d);
translate([0,150,0]) cylinder(h=hoehe,d=durchmesser);
//cylinder(h=h,r=r);
translate([100,150,0]) cylinder(h=hoehe,r=radius);
//cylinder(h=h,r1=r1,r2=r2);
translate([200,150,0]) color("blue",1.0) cylinder(h=hoehe,r1=rklein,r2=rgross);

//variablen können auch durch rechenoperationen verändert werden
//cylinder(h=h,r1=r1,r2=r2);
translate([300,150,0]) color("red",1.0) cylinder(h=hoehe,r1=rgross+40,r2=rklein-6);

//sphere(r=r);
translate([0,-100,0]) sphere(r=radius);
//sphere(d=d);
translate([0,-200,0]) sphere(d=durchmesser);

//-----

// union, sinnlos bei nur 1 objekt!!!
translate([0,400,0]) union(){
    cube(100);
    sphere(50);
}
// difference
translate([0,400,200]) difference(){
    cube(100);
    sphere(50);
}
translate([-200,400,200]) difference(){
    sphere(50);
    cube(100);
}
// intersection
translate([0,400,400]) intersection(){
    cube(100);
    sphere(50);
}

//-----

//resize, sinnlos bei cube!!!
translate([600,0,0]) resize([100,500,300]) sphere(20);
```
```
$fn=200;
p=600;

// module mit text und extrude
module stc(s=50){ 	
    //s=50;
    color("blue",1.0) linear_extrude(height=300,center=true,convexity=100,twist=100,slices=30,scale=1.0){  
    text("STC",size=100,font="Consolas:style=Bold");
    }
    color("yellow",1.0) rotate_extrude(angle=270,convexity=10){  text("STC",size=100,font="Consolas:style=Bold");
    }
    translate([0,0,200]) sphere(s);
}

translate([p,p,p/4]) stc();
translate([-p,p,p/4]) stc(s=10);

// for loop
translate([-p,-p,0]){
for(z=[-180:45:+180])
  for(x=[10:5:50])
    color("blue",1.0) rotate([0,0,z]) translate([x,0,0]) cube(70);
 } 

// for loops mit module
module reihe(){
    translate([0,0,150]) sphere(30);
    translate([0,0,50]) cube(100,center=true); 
}

for(x=[-1000:200:+1000]){ translate([x,0,0]) reihe();
}

for(x=[+1200:200:+2200],z=[-180:45:+180]){ color("red",1.0) rotate([0,0,z]) translate([x,0,0]) reihe();
}

```

