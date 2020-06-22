User guide
==========

About RadMap
------------

RadMap is a software that allows you to simulate how radiation interacts
with matter. With RadMap you describe an environment in terms of
geometrical objects and sources of radiation. RadMap then uses a full
Monte Carlo algorithm to calculate the effects of radiation in desired
points of your environment.

With RadMap you can

-  calculate external gamma dose due to a large number of radioactive
   isotopes in complex geometries
-  define new materials if the many predefined materials do not suite
   your needs
-  save your geometries and sources for later use and sharing

Starting RadMap
---------------

Starting RadMap brings up a program window divided in five principal
parts:

-  Geometry tree
-  Geometry view
-  Dose maps
-  Sources
-  Properties

There is also a menu bar at the top of the main window. To perform a
calculation with RadMap you will interact with these parts.

Geometry tree
~~~~~~~~~~~~~

This sub-window shows the geometrical objects that will be present in
your simulation. The objects are shown in a tree structure. Depending on
shape, material, density and position, each object will effect the
transportation of radiation differently.

Geometry view
~~~~~~~~~~~~~

Here the objects you create in the geometry tree will be shown visually.

Dose maps
~~~~~~~~~

This is a list of dose maps. Each dose map is a box shaped region in
your geometry that registers flux of particles and converts this flux to
dose.

Sources
~~~~~~~

Shows a list of sources of radiation in your geometry. Each source is
associated with a geometrical object in the geometry tree effectively
making this object the source of radiation.

Properties
~~~~~~~~~~

This sub-window shows properties of whatever element is selected in the
Geometry tree, the Dose maps or the Sources. You also set the properties
here.

A simple case - walk-through
----------------------------

Create a world volume
~~~~~~~~~~~~~~~~~~~~~

The first thing you need to do is to create a world volume. This is a
box-shaped region in which particles will be transported during
simulation. When a particle leaves the world volume they are lost and
will not affect the simulation here after. All other geometric objects
and dose maps must be contained in the world volume.

.. admonition:: *Interact*
    
    **Menu bar > File > New project**
    
    * An entry "World" is shown in the Geometry tree. This is the name of this solid.
    * Widgets are activated and ready for input in tabs in the Property panel.

Set the dimensions
~~~~~~~~~~~~~~~~~~

You cannot see the world volume in the geometry view yet because you
have not specified the dimensions of the world. You do this by entering
the dimensions in x, y and z direction in the Properties panel.

.. admonition:: *Interact*

    **Property panel > Dimensions**

    Set length X-side to 100. Set unit to cm.

    Set length Y-side to 100. Set unit to cm.

    Set length Z-side to 100. Set unit to cm.

    * The outline of a box is shown in the geometry view

Note that the widgets under the rotation tab and the position tab are
disabled. It is not possible to specify a rotation or a position for the
world volume.

Change the geometry view
~~~~~~~~~~~~~~~~~~~~~~~~

You can use the mouse an the keyboard to change the geometry view.

.. admonition:: *Interact*

    **Geometry view**
    
    Left-click and hold down the mouse button some where in the middle of the geometry view. Move the mouse.

    * The view is rotating.

    Press the up-arrow.

    * The view is zoomed in.

    Press the down-arrow.

    * The view is zoomed out.

    Hold down the shift-key and use the arrow keys simultaneously.

    * The view is panned up, down, left and right.

    Hold down the ctrl-key and use the arrow keys simultaneously.

    * The view is rotated up, down, left and right.

If you ever loose an object in the view and you cannot find it, you
can reset the view.

.. admonition:: *Interact*

    **Geometry tree > Right-click entry > Focus and fit to view**

    Right-click the solid you wish to display in the geometry view (in this case "World"). In the drop-down menu that appears, select "Focus and fit to view".

    * The world volume is displayed in the centre of the geometry view.

Set the material
~~~~~~~~~~~~~~~~

Every geometrical object must be associated with a material. You set the
material through a drop down menu under the general tab.

.. admonition:: *Interact*
    
    **Property panel > General tab > Material drop down menu**

    Set material to Air

    * Drop down menu shows that Air is set

The “Edit Material” button in the same tab opens a panel where yo can
create custom materials. This panel will be discussed in a different
tutorial.

Add a child solid to the world volume
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Adding an object as a child to an existing object in the geometry tree
is done through the drop down menu that appears when you right click an
entry in the geometry tree.

.. admonition:: *Interact*
    
    **Geometry tree > Right-click entry > New sub solid > Tube**

    * The general tab in the properties panel will display properties for the newly created tube

Set name of a solid
~~~~~~~~~~~~~~~~~~~

Most objects whose properties are shown in the properties panel have
names. Only normal letters, numbers and underscore characters can be
entered as name characters. If you try to enter a forbidden combination
of letters, the entry will not be registered.

.. admonition:: *Interact*
    
    **Properties panel > General tab > Solid > Name**

    Change the solid name by clicking in the field that reads "tube_1" and enter a new name. For example "lead_shielding"

    * The new name is shown both in the properties panel and in the geometry tree.

    Also: Select a material for the newly created volume as previously described.

Set dimensions for a tube
~~~~~~~~~~~~~~~~~~~~~~~~~

The dimensions of a tube are different from that of a box. The tube has
a length, an inner radius, an outer radius, a start angle and an opening
angle. Investigate these properties by changing the values under the
dimensions tab (make sure that the newly created tube is selected in the
geometry tree. If not, the properties panel will show properties for the
wrong volume).

.. admonition:: *Interact*

    **Properties panel > Dimensions > Tube dimensions**

    Set Inner radius to 10 cm

    Set Outer radius to 20 cm

    Set Length to 30 cm

    Set Start phi to 0.00 degrees

    Set Delta phi to 270 degrees

    * A non transparent tube is shown in the geometry view

    Change the values of Start phi and Delta phi and study the effect on the tube. When done, change the values back to those described above.

Set the position of the tube
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Under the position tab you can change the position of the tube relative
to the parent volume (the World in this case).

.. admonition:: *Interact*

    **Properties panel > Position > Local position**

    Set X to 5 cm

    Set Y to 10 cm

    Set Z to 15 cm

    * The tube shifts position in all three dimensions

Note that no volume is allowed to overlap with another volume. Every
volume must be completely contained by its parent volume and it is not
allowed to overlap any sibling volume. A check for overlapping volumes
is done when you start a simulation. **Note**: This check is done by
sampling random points on the surface of each volume and by making sure
that these points lies outside of all child and sibling volumes. Since
only a couple of thousand points will be sampled on each volume, it is
technically possible to fail to detect overlapping volumes.

How are the axis oriented?
~~~~~~~~~~~~~~~~~~~~~~~~~~

The axis of the internal coordinate system of a solid can be shown in
the geometry view.

.. admonition:: *Interact*

    **Geometry tree > Right click tube > Show coordinate system**

    * Rotating the geometry view should reveal three lines emerging from the centre of the tube. The lines are red, green and blue and represents the x, y and z axes of the tube system.

If the axis are hidden by the solid surface of the tube, you can make
the tube transparent by drawing it in wire-frame mode.

.. admonition:: *Interact*
    
    **Geometry tree > Right click tube > Draw wireframe**

    * The Contours of the tube are visible but the surfaces are transparent.

To see how the systems of the world and the tube are related you can
enable the coordinate system for the world as well

.. admonition:: *Interact* 
    
    **Geometry tree > Right click the world > Show coordinate system**
    
    * The coordinate system axis of the world volume is shown.

Set the rotation of the tube
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Through the Rotation tab it is possible to rotate a volume relative to
its mother volume. The rotation is sequential and rotates the volume
system around its axis. Rotation is performed first around the X-axis,
then the Y-axis and last the Z-axis.

.. admonition:: *Interact*

    **Geometry tree > Select tube**

    **Properties panel > Rotation tab > Sequential rotation**

    Set the X rotation to 45 degrees.

    * The tube and its internal coordinate system is rotated around the X-axis by 45 degrees

    Set the Z rotation to 45 degrees.

    * The tube and its internal coordinate system is rotated around the Z-axis by 45 degrees

Note that the effect of changing the X or Y rotation after the Z
rotation is set, can be difficult to predict. The easiest way to control
a rotation is to set it in the sequence x, y, z.

Add a source
~~~~~~~~~~~~

Sources are associated with solids registered in the geometry tree. To
add a source to the world, we must create a solid to associate with the
source.

.. admonition:: *Interact*

    **Geometry tree > Right-click world > New sub solid > Box**

    **Properties panel > Dimensions > Box dimensions** 

    Set Length X-side to 2 cm

    Set Length Y-side to 2 cm

    Set Length Z-side to 2 cm

    **Properties panel > Position > Local position**

    Set X position to 5 cm

    Set Y position to 10 cm

    set Z position to 15 cm

    * A box is shown inside the tube.

By default, all new solids have the colour red. The colour can be
changed under the general tab.

.. admonition:: *Interact*

    **General tab > Appearance > Left-click colour box**

    In the dialog that appears, chose a nice green colour to contrast to the red and click OK.

    * The newly created box turns green.

As before we need to select a material for the solid.

.. admonition:: *Interact*
    
    **Property panel > General Tab > Material**

    Set the material of the box to iron by selecting "Fe" as material.

    * Fe is set as material.

Note that you can choose almost any material defined in the NIST
database.

Give the box a new name if you wish. “contaminated_sample” might be a
suitable name.

A source can be associated with the box by right-clicking the box entry
in the geometry tree.

.. admonition:: *Interact*

    **Geometry tree > Right-click box > Attach source**

    * An entry "source_1" is shown in the "Sources" panel.
    * Properties for the source is shown in the general tab in the properties panel.

Now we can select the properties for the source.

.. admonition:: *Interact*
    
    **Properties panel > General tab > General**

    Give the source a suitable name, for example "Cs_contamination".
    * Name is set to "Cs_contamination"

    **Properties panel > General tab > Radioactive source**

    Set the "Element" to Caesium in the element drop down menu. The drop down list contains most elements in the predict table.
    The three columns in the list shows the atomic number, the element identifier (as shown in a periodic table) and the full element name.

    * Element is set to "Cs".

    Click the Isotope drop-down list.

    * A drop down list with numbers is shown.
        Each number in the list represents the mass number of a selectable Caesium isotope.

    Select "137".

    * 137 is selected.

Now the isotope :sup:`137`\ Cs is chosen as source for the box. What remains is
to set the activity of the source.

.. admonition:: *Interact*

    **Properties panel > General > Radioactive source**

    In the activity field, set the value to 100 and the unit to GBq (100 Giga Becquerel)

    * The value and unit is displayed.

.. caution::
    
    The decay scheme of an isotope is that of a
    nucleus in its ground state. Currently you cannot directly specify an
    excited state of an isotope. Thus :sup:`99`\ Tc will not yield the dose rate of
    the common metastable state of :sup:`99m`\ Tc. Selecting :sup:`137`\ Cs will however yield
    the expected dose rate since the Cs nucleus will decay to the metastable
    state :sup:`137m`\ Ba.

We also have an option to simulate the entire decay chain of an isotope.
In this case the decay products of the primary isotope will be tracked
during simulation and will undergo decay if they are unstable. Note
however that the half-life of a decay product of the primary isotope
will not be considered. Every unstable decay product of the primary
*will* decay during the simulation. From a purely physical point of view
this is only meaningful if the half-lives of the decay products are much
shorter than that of the primary isotope. It is up to the user to
evaluate if this is option should be used.

If the full chain option is not selected, the simulation will follow the
decay of a primary isotope to the ground state of the the first decay
product.

To select/deselect full chain simulation, do as follows

.. admonition:: *Interact*

    **Properties panel > General > Radioactive source**

    Click the check-box field labeled "Full chain"

    * The check-box is ticked / empty 

Adding dose maps
~~~~~~~~~~~~~~~~

We want to calculate the dose rate at some distance from the source when
it is exposed and shielded. We need to place two dose maps in the world
to do this. A dose map is not an active part of your geometry and
although the dose maps appear as non transparent boxes in your geometry,
they do not interfere with your objects or the radiation that is
simulated. Dose maps are allowed to overlap both solids and other dose
maps. If it is a good choice to place dose maps that overlaps solids can
however be discussed. A dose map registers radiation entering a
box-shaped region. The number of particles, their energies and incident
angles are registered an the corresponding fluence is converted to dose
using the conversion tables of ICRP 116.

You create a dose map by right clicking a solid in the geometry tree.
The association of a dose map with a specific solid decides in what
coordinate system the dose map will be defined. Apart from this the
parent solid and the dose maps have nothing to do with each other. It
can be good to think about what parent to chose though. When you save a
volume in the geometry tree to file, you have the option to also save
the associated dose maps.

.. admonition:: *Interact*

    **Geometry tree > Right click the tube entry > Attache dose map**

    * A new entry "dose_map_1" is shown in the Dose Map panel.
    * Properties for the dose map is shown under the General tab in the properties panel.

A dose map share properties with a solid of box type. It has dimensions,
a position and a rotation. Further it is possible to configure what type
of radiation it can registers (currently only gamma) and what kind of
dose measure it registers (currently only effective dose). You can also
set the geometry of the exposure situation. ICRP gives different
conversion tables for different exposure situations. You can choose from
the following:

-  AP: Antero-posterior geometry – the irradiation geometry in which a
   parallel beam of ionising radiation is incident on the front of the
   body in a direction orthogonal to the long axis of the body.
-  PA: Postero-anterior geometry – the irradiation geometry in which a
   parallel beam of ionising radiation is incident on the back of the
   body in a direction orthogonal to the long axis of the body.
-  RLAT, LLAT: Lateral geometry, right and left – the irradiation
   geometry in which a parallel beam of ionising radiation is incident
   from either side of the body in a direction orthogonal to the long
   axis of the body.
-  ROT: Rotational geometry – the geometry in which the body is rotating
   at a uniform rate about its long axis, while is is irradiated by a
   broad beam of ionising radiation from a stationary source located on
   an axis at right angles to the long axis of the body.
-  ISO: Isotropic geometry – defined by a radiation field in which the
   particle fluence per unit of solid angle is independent of direction.

In a general situation the rotational geometry is probably the most
meaningful setting. Alternatively, the isotropic geometry could be used.

.. caution::
    
    The user is responsible for setting meaningful
    properties of a dose map. Examples of less meaningful settings could,
    but does not need to, be:

    * Exposing a dose map to radiation fields that is highly non-homogeneous over a surface of the does map. The concept of effective dose (measured over the whole body) might lose its meaning in this case.

    * Exposing a dose map to fields form several sources and using geometry settings like AP or PA. In an exposure situation with several sources, a single exposed person cannot have her or his back side/front side facing each source. ROT or ISO would be more meaningful settings in this case.

.. admonition:: *Interact*

    **Properties panel > General tab > General > Name**

    Set the name of the dose map to "unshielded"

    * Name is changed

    **Properties panel > General tab > Dose > Geometry**

    Set the Geometry to ROT

    * ROT is shown in the drop down list

    **Properties panel > Dimensions tab > Box dimensions**

    Set the dimensions as follows:

    Length X-side: 7 cm

    Length Y-side: 1 cm

    Length Z-side: 7 cm

    * A transparent box with black contours is shown in the centre of the tube. This is the dose map.

    **Properties panel > Rotation tab > Sequential rotation**

    Set Z-rotation to 45 degrees

    **Properties panel > Position tab > Local position**

    Set the position to:

    X: 15 cm

    Y: -15 cm

    Z: 0 cm

    * The dose map is visible just outside of the slice opening of the tub. One of its sides is facing the source.

    * Note that the rotation is not necessary if you think that the radiation field is fairly uniform over the individual exposed surfaces.

You might also want to compare the non-shielded dose rate with the dose
rate shielded by the lead tube. This is simply done by creating a second
dose map and placing it outside the tube on the opposite side compared
to the first doe map.

.. admonition:: *Interact*

    **Create a new dose map associated with the tube**

    Use identical settings to the first dose map with the exception of the     position. Set the position to:

    X: -15 cm

    Y: 15 cm

    Z: 0 cm

    * A new dose map is visible on the opposite side of the tube compared to the location of the first dose map.
        The tube shields the new dose map from the source.

    Name the new dose map "shielded" or something similar.

Run the simulation
~~~~~~~~~~~~~~~~~~

What remains is to set the simulation parameters. You do that from the
menu bar.

.. admonition:: *Interact*

    **Menu bar > Simulation > Simulation settings**

    * A dialog is opened

Before you run a simulation you need to tell the algorithm when to
terminate the calculation. To do this you specify the stopping criteria.
Currently you can only set the number of primary events to simulate. For
a radioactive source this means the number of decays to simulate. The
higher number, the better precision in the calculation. But larger
number requires more time. Remember that the time scales linearly with
the number of particles but the precision (the standard deviation of the
simulated dose rate) typically improves with the square root of the
number of particles simulated. Scaling the number of particles with a
factor 10 will take 10 times longer but will only improve the precision
with a factor of 0.3 (approximately).

Depending on the license you have, the number of particles you can
simulate might be limited. Running a on a free license will typically
limit the number of particles to simulate so that the precision in the
result is very low. You can however ask the RadMap team for a time
limited free license to evaluate the full potential of RadMap.

.. admonition:: *Interact*

    Set the stopping criteria to 1000000 particles or the
    maximum allowed for you licenses. Typically this is 80 particles for a
    free license. Click “Start simulation”.

    * You will be prompted to save the project.

    Accept by clicking OK.

    * A save dialog will be displayed.

    Chose a path and a name that you think is representative for your setup. "shielding_tube" might be a good name. Click "Save".

    * A dialog informs you that the application is connecting to the local server.

    * A progress bar for the simulation is shown.

    * The simulation finishes and a dialog informs you that the result has been saved to the project.

    Dismiss the dialog.

    Select the non-shielded dose map from the dose map panel.

    * The dose rate registered by the dose map is shown among the
        properties under the general tab in the properties panel.
        The uncertainty (one standard deviation) of the registered value is also shown.

    Select the shielded dose map from the dose map panel.

    * The dose rate registered by this dose map is significantly lower that that of the non-shielded dose map.

If you look at the very top of the application window, you can see that
text [LOCKED] is shown next to the project name. As long as a result is
associated with the project, it is not possible to change most of the
properties of solids, sources and dosemaps. If you want to change
something in the project, you have to delete the results. This can be
done from the File menu

.. admonition:: *Interact*

    **Menu bar > File > Delete results**

    * The results are deleted. The [Locked] label is removed. It is possible to change the properties of all the project items.

Create a report file
~~~~~~~~~~~~~~~~~~~~

You can export the simulation results to a pdf file.

.. admonition:: *Interact*

    **Menu bar > Report > Create PDF report**

    * You will be prompted to select a location and a name for saving the report PDF file.
    * When saved, the file is opened by your default pdf viewer. If no default viewer is found you will have to open the file manually from where you saved it.

.. _acquire a time limited license:

Acquire a time limited license
------------------------------

To try out the full power of RadMap (no restriction on number of
simulated particles), you can ask for a time limited full license. First
you must send us an installation specific file that can be generated
from the RadMap interface.

.. admonition:: *Interact*

    **Menu bar > Help > License**

    * Follow the instructions in the dialogues. These will let you know where to find the generated file and how to send it to us.