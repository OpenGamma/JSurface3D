JSurface3D
==========

JSurface3d is an interactive WebGL surface built with Three.js. There are over 30 configurations that let you customize the look and feel, including vertex shading range, width, height, fontsize, colours etc and additional features include live updating, slicing, projecting smiles, rotation and zooming.

[Examples](http://opengamma.github.com/JSurface3D "JSurface3D.js examples") |
[Documentation](http://opengamma.github.com/JSurface3D/docs/symbols/JSurface3D.html "JSurface3D.js documentation")

Requirements
-----------

When we decided to release JSurface3D as a separate component I removed a number of OpenGamma specific dependencies, however it does still use **JQuery** and a number of fairly new JavaScript methods like **map** and **filter**. Additionally, if you want zoom support you need to add [jquery-mousewheel](https://github.com/brandonaaron/jquery-mousewheel "jquery-mousewheel") plugin, you may already have this as its bundled with various other plugins.

The 3D text requires a JavaScript font file. JSurface3D defaults to helvetiker but you can change this. You can use Typeface.js to convert fonts if needed. detector.js and stats.js are also required, they are scripts developed by the author of Three. Their not included in the actual project, yet used heavily by Three users.

Usage
-----
The actual JSurface3D code is split into two groups of files. The first is bunch of utility functions called Four. Four consist of a buffer manager, 3d text manager, material library etcetera. Basically anything that I thought I would use in other Three projects. The rest are the actual jsurface3d files, the actual surface, the smile planes, the slice geometry, interactions excetera.

### Creating: ###

    var surface = new JSurface3D({
        selector: '#surface',
        data: {
            vol       : [],  // Surface data points
            xs        : [],  // X axis data points
            xs_labels : [],  // X axis labels (optional)
            xs_label  : '',  // X axis label
            zs        : [],  // Z axis data points
            zs_labels : [],  // Z axis labels (optional)
            zs_label  : ''   // Z axis label
        }
    });

### Updating: ###
You can either update the whole world or just the surface. You can also reload it with the last data by omitting the data argument altogether

    surface.update('surface', data);

### Resizing: ###

    surface.resize();

### Cleanup: ###

    surface.die(true); // optional Boolean, use it to clear up after all surfaces.

&copy; 2013 - present by OpenGamma Inc. and the OpenGamma group of companies