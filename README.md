![Molecular Addon for Blender](https://github.com/scorpion81/Blender-Molecular-Script/workflows/Molecular%20Addon%20for%20Blender/badge.svg)

Blender-Molecular-Script
========================

This is the molecular python script for blender, originally coded py Pyroevil. Inspired from the 2d simulator Really (1998) and Lagoa Multiphysic in Softimage.

To download the latest version go to the release section of this repository.

The script can be installed like any other addons in Blender:
First way:
- unzip the folder "molecular" in your "x.xx\scripts\addons" blender directory

or

Second Way:
- Open Blender
- Go in File > User Preferences > Addons tab
- Click on "Install from file" button.
- Browse and click the downloaded zip file and push the "Install from file..." button.

To activate the plugins:
- Open Blender
- Go in File > User Preferences > Addons tab
- In the "Object" categories, you must find "Molecular"
- Check it , close the "Blender user preferences" windows and have fun.


How to add UVs to molecular particle instances:
----------------------------------------------

This didnt seem to work in blender 3.2.x any more and was fixed in 1.1.4.
Should also apply to blender 3.1.x but that was not tested by me.

- Original Link:
https://blenderartists.org/t/moleculars-physics/521682/269

- Example File:
[test_UV_molecular.zip](https://github.com/scorpion81/Blender-Molecular-Script/files/9320719/test_UV_molecular.zip)

When the UV data is being baked during the simulation, it will be written into the angular velocity cache part 
of the particle system at the moment.

Hence you can retrieve it via a particle info node later on in order to feed it into the vector socket of the
texture node. Note that the Particle Info Node belongs to the Material on the Sphere aka the object which is being instanced.
In the example blend file there is also a Particle Info Node on the Cube material, but it doesnt really belong there. Rather
it was added by mistake.

Example with 10x10x10 Grid:
![molecular_bake_uv](https://user-images.githubusercontent.com/1172149/184380338-b07cb5de-4d54-45e0-9fa8-2967f4fb29cc.jpeg)

Same Example with 30x30x30 Grid
![molecular_bake_uv_high](https://user-images.githubusercontent.com/1172149/184380364-9e4a1ff9-8924-4619-9d77-f191950c52e7.jpeg)

Remarks:
- only in cycles
- only in rendered viewport and render
- need to re-bake the sim for UVs after loading (not persistent, it seems)
