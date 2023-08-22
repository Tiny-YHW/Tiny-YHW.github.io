---
layout: wiki
title: What’s New
cate1: Cadence Allegro
cate2: 
keywords: 
---

* * *

## 22.1

*   [What’s New in 22.1](https://tiny-yhw.github.io//2023/06/06/cadence-allegro-whats-new-in-22-1/){:target="_blank"}
*   [What’s New in 22.1 QIR1&2（hotfix4）](https://tiny-yhw.github.io//2023/06/06/cadence-allegro-whats-new-in-22-1-QIR1+2/){:target="_blank"}

### 22.1 Base Release

*   On-Canvas Structure Update and Variant Creation. When reusing structures multiple times, easily update one instance and push the changes to all instances. 
*   Dimensioning Update. Easily make changes to a dimension without having to delete and regenerate it. 
*   Route Keepout Exception. Easily locate stacked vias and flag them with DRC markers in restricted areas. 
*   Performance Enhancements. Enhancements include better performance on designs with a large number of DRCs, faster update to smooth, better move performance, better performance for shape parameter per layer override, capping of command window messages, and faster DRC checking on designs with negative layers. 
*   Expanded GPU Support. GPU support now includes modern discrete or integrated GPUs from Intel and AMD. Enhancements to NVIDIA GPUs include performance gain in panning and zooming and augmented quality of display. 
*   Normalized Forms for High Resolution Displays. Easily specify a scaling factor to normalize forms that are partially cut off due to display scaling in devices with 4k or higher resolution. 


* * *

## 17.4

*   [What’s New in 17.4 2019](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-2019/){:target="_blank"}
*   [What’s New in 17.4 2019 QIR1（hotfix7）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir1-hotfix-007/){:target="_blank"}
*   [What’s New in 17.4 2019 QIR2（hotfix13）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir2-hotfix-013/){:target="_blank"}
*   [What’s New in 17.4 2019 QIR3（hotfix19）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir3-hotfix-019/){:target="_blank"}
*   [What’s New in 17.4 2019 QIR4（hotfix28）](https://tiny-yhw.github.io//2023/06/12/cadence-allegro-whats-new-in-17-4-qir4-hotfix-028/){:target="_blank"}
*   [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}

### QIR 3

*   GPU Acceleration Rendering. Leverage GPU in Allegro Layout Editors to improve response time during panning and zooming, toggling layers, and render quality.
*   DRC Browser Updates. Navigation improvements for the DRC Browser and the ability to waive DRC by group select.
*   Fillet DRC Control. New analysis mode option to enable line based checks for fillets.
*   Shape Performance and Quality Updates. Improved shape performance for copper pours and editing smooth shapes. Fast mode replaces rough mode and drastically improves the performance during active etch editing including slide, add connect, move, and more. Improved performance in shape voiding quality including crosshatch shape fill improvement, fillet void quality improvement, and trim void improvement.
*   3D Canvas Updates. Isometric view has been added for the bottom side of the board. Other updates include realistic plating thickness, increased model realism, and secondary model support.
*   Reuse Module Enhancement. Dynamic shapes are automatically converted to static shapes to ensure consistent voiding. Modules applied to the design remain locked to avoid accidental modification. Addition of copper planes, constraint regions and text notes within the module file. Quickly swap a placed reuse module with a different variant in one or multiple locations.
*   Scribble Enhancements. Multi-pin scribble support when routing allows you to digitize a path through a pin field to make connections. Recognizes the same net pins and snaps to center while routing.

### QIR 2

*   Viewer Integration. Launch PCB Editor viewer from the project hierarchy.
*   3D Canvas enhancements.  3D mapper now a part of 3D canvas, replacing Allegro (2D) menu. Simplified use model and GUI enhancements. Improved accuracy of collision detection and distance measurements. Additional support for mapping native CAD models (Parasolid, Siemens NX, CREO, SOLIDWORKS).
*   IPC2581 enhancements. Additional support for rigid flex (bend detail and stack-up profiles), Countersink/counterbore, square drill features, net shorts, and impedance specifications and nets.  
*   IDX enhancements. Bend sequence ordering, Geometry use identification, primary pin identification, and time stamps.

### QIR 1

*   PCB Panelization. Setup and manage your fabrication panels directly within PCB Editor (OrCAD Pro & Allegro Feature).
*   New Design Setup Workflow. You can now use the new Design Setup Workflow to prepare for analysis by setting up your design for the different checks. You can set up cross-section, DC nets, components, Xnets, and differential pairs. You can then save the design with the changes. As with all other work flows, you can access this workflow from the Analysis Workflows pane (Analyze – Workflow Manager).
*   3D Canvas Updates. A number of improvements and enhancements have been made to the 3D canvas including:
    *   Performance Improvements. In this release, performance improvements is a top priority resulting in greatly improved launch times and reduced memory usage. 
    *   3D Canvas Filter Dialog.  You will see the re-designed filter dialog. With this redesigned dialog. You have the choice of selecting what layers to visualize in 3D Canvas – All Layers or Outer Layers only, and what objects you wish to bring into the 3D Canvas. You can now visualize much larger designs in 3D Canvas by eliminating memory straining objects. 
    *   Nets Pane. A new pane has been added to 3D Canvas – the Nets pane. Prior to this release, nets were visualized on the 3D Canvas, but no underlying information regarding nets were imported. With this release, net information (names, type, properties, and so on) are also imported into 3D Canvas and the new Nets pane allows you to control how to visualize the nets in 3D Canvas. You can select All Nets (the default view) and any other groups of nets contained in a design.
    *   Variable Highlighting. Prior to this release, components selected on the 2D side or selected in 3D Canvas were shown in 3D Canvas as selected (red). With this release, two new highlighting choices are available – Dim and Vanish. With the Dim option, selected objects still appear on the canvas as red while the remainder of the elements are dimmed. With the Vanish option, selected objects appear on the canvas as red while the remainder of the elements disappear.

### 17.4 Base Release

IPC 2581 Spec Properties. By defining a SPEC that is composed of the fabrication notes, the notes become part of the IPC-2581 data and are directly read by an IPC-2581 viewing tool, reducing the need to locate the correct drawing or document to read the notes. Another example would be to define assembly notes for a heat sink to be added to a part. The assembly note might instruct users to add a specific thermal epoxy first, then add the heatsink after the epoxy is applied.

*   Mask Defined Pin Annular Ring Check. A new Mask Defined Pad check has been added to the Design for Manufacturing Annular Ring checks and the DesignTrue DFM Wizard template file. There are two common types of padstack definitions when it comes to soldermask to pin pad size ratios. The first, metal-defined padstack (sometimes referred to as non-mask defined padstack), is where the solder mask opening is typically larger than the pin pad. The other is a mask-defined padstack, where the solder mask size is typically smaller than the pin pad. The mask-defined pad is often used for BGA components to contain the solder ball within the pin pad and prevent outflow of solder.
*   Hierarchical Route and Via Keepouts. You can now define keepout by layer type and location using the additional Route and Via Keepout subclasses that have been added to Symbol Editor. Following a model similar to Constraint Regions, use the OUTER\_LAYERS, INNER\_SIGNAL\_LAYERS, and INNER\_PLANE\_LAYERS subclasses to create keepout shapes.
*   Contour Routing Update. The 17.4-2019 release now supports the previous Enhanced Contour behavior as the default contouring method. In addition to the previously supported functionality of latching/unlatching and shoving, this release focuses on ease of use and power by adding additional spacing controls and full constraint region support.
*   Copy/Paste Update. In previous versions of layout editors, copying of objects was performed by selecting objects and pasting them to one location at a time. While the use model was simple, the functionality was limited. The 17.4-2019 release aligns the copying functionality of the layout editors with other popular software applications by adding familiar behaviors. This new copy command combines the precision of single click or single location pasting with the power of window select or multi-location pasting. As with most applications, copied objects are buffered for pasting at a later time. You can paste the last copied object at any time simply by using the paste command.
*   Copy. The Copy command now adds the selected objects to a buffer and automatically starts the Paste command to enable the placing of objects on the canvas.
*   Paste. The Paste command supports all legacy “copy” options as well as new support for shape net retention. In addition to these options, pasting can be used in two different manners:

*   Single Location Pasting
    *   Copying of objects and pasting at one location per click
    *   Object snaps to the singular selected object or location
*   Multiple Location Pasting
    *   Copying of objects and pasting at multiple locations through window select
    *   Objects snap to all selected objects

*   3DMechanical Symbol Transparency. Designers who wish to “peek” inside a PCB assembly encased with a mechanical cover can now do so. Now look through the mechanical cover into an assembly by setting the global transparency/opaqueness setting.
*   Unplated Holes in Footprints. Unplated holes in footprint (.dra) files can now be visualized when the footprint is brought into 3D Canvas. Previously, unplated holes were not represented.
*   STEP Models and Pastemask. In some system designs, such as complicated telephony devices, even the most minuscule space is critical. With the 17.4-2019 release, the position of 3D models can now be globally adjusted to take the thickness of solderpaste into account in the “z” direction. By default, the STEP model location in the “z” direction is the bottom of the model located directly on top of the copper pads.


## 17.2

-  [What’s New in 17.2 2016](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR1（hotfix4）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-1-hotfix4/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR2（hotfix9）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-2-hotfix9/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR3（hotfix16）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-3-hotfix16/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR4（hotfix25）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-4-hotfix25/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR5（hotfix31）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-5-hotfix31/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR6（hotfix38）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-6-hotfix38/){:target="_blank"}
-  [What’s New in 17.2 2016 QIR7（hotfix48）](https://tiny-yhw.github.io//2023/06/08/cadence-allegro-whats-new-in-17-2-2016-qir-7-hotfix48/){:target="_blank"}
-  [BUG修复记录](https://layouto.lanzouf.com/i1LVI0tkym7i){:target="_blank"}


### QIR 7

*   Design for Fabrication Rule Enhancements. In the Design for Fabrication constraints, a new category Copper Features has been added in this release. This category applies rule to cover minimum line width, antenna, and acid traps.
*   Design for Assembly Rule Enhancements. A new category PkgToPkg Spacing has been added in the Design for Assembly constraints. You can now maintain the DFA table within Constraint Manager and assign different DFA rules based on stack up technology, specifically within rigid-flex designs. All existing functionalities are still maintained from previous versions.
*   Design for Testability Rule Enhancements. A new Design for Test constraints have been added in the Manufacturing category in the QIR 7 release. These group of checks are related to issues in the final testing of the PCB assembly.
*   DesignTrue DFM Ecosystem. To make designs ready for fabrication, the information about various manufacturing constraints and rules and the supported values are obtained from PCB fabricators in the form of spreadsheets. The spreadsheet is then transferred into Constraint Manager by a PCB designer. This process is error-prone and time consuming. The easiest way to obtain the rules would be in the form of direct import of fabricator rules into the Constraint Manager using technology files recognized by Constraint Manager.
*   DesignTrue DFM Web-Based Rules Request. The DesignTrue DFM Partner Program was developed to facilitate the request for fabrication rules directly from the supplier and receive those rules in the constraint technology file format. You can then directly import the rule files received into Constraint Manager.
    *   To request rules, open the request login site from a Web browser at https:\\\\pcb.cadence.com\\dfm\_customer.
*   3D Canvas Update. The recently productized 3D Canvas continues its growth and maturity with the QIR7 release. With additional features still under development, this release covers incremental updates that will enhance the user experience.
    *   Selecting a specific area of a design to visualize in 3D is now easier with “window select” on the 2D workspace
    *   The popular Cutting Plane feature has been supplemented with a “reverse cutting plane” option
    *   The original Perspective View has been paired with an additional Orthographic View choice
    *   The 3D Canvas now recognizes STEP model colors assigned in the STEP Package Mapper
    *   Color Theme layers now have transparency control sliders and objects falling within holes
    *   Cutouts and outside the board outline are now eliminated from view
*   Place Vision. Place Vision, available in PCB Editor, is a graphical environment designed to increase productivity and efficiency with various component placement strategies. While the concept is similar to Timing Vision, Place Vision offers guidance with respect to:
    *   Xnet rat filtering
    *   Timing driven Placement
    *   Component Association
*   Sigrity Technology Driven High-Speed Signal Analysis and Checking. OrCAD® Integrated Analysis and Checking is a new, unique environment blending the best of OrCAD® and Sigrity™ technologies that provides analysis and checking capability entirely within the PCB Editor framework. For rule checking, DRC and ERC capabilities continue to depend on Constraint Manager as the single cockpit. This release introduces two new workflow analysis capabilities for impedance and coupling. The workflows provide guided access to Sigrity analysis with results returned as dockable tables and plots, or as new Vision overlays.
*   Timing Path support for Z-Axis Delay. The Z dimension of Vias and Through Hole Pins can now be included in timing path DRC calculations. 
*   Pin Delay Property for Extended Timing Path into Packages. System level constraints typically require the creation of a Design Link and possession of mating boards or package databases in order to create a multi-board constraint solution. A timing path from the die of one chip to the die of another requires the MCM file from Allegro Package Designer (APD) or SiP Layout to create the extended timing path. Obtaining these databases from Chip vendors is not always possible and the alternative for many was to create formulas in applications like Excel. The Pin Delay property allows external delay values like package length to be entered into the OrCAD PCB Editor and assigned to a component from a CSV file, assigned as properties/values to pin instances, or entered in the PIN Delay column of the Propagation Delay or Differential Pair worksheets in Constraint Manager.
*   Differential Pair Dynamic Phase Control. Differential Pair technology has evolved where more stringent checking is required in the area of phase control. This is evident with higher data rates associated with parallel buses. In the simplest of terms, Differential Pair technology is sending opposite and equal signals down a pair of traces. Keeping these opposite signals in phase is essential in assuring that they function as intended. As the current “Static Phase” is limited to a one time check across the entire Driver-Receiver path, the “Dynamic Phase” check performs phase checks at bend point intervals across the differential pair. The check is designed to meet the guidelines suggesting the path lengths of the true and complement signals within the differential pair must differ by no more than “x mils” along the entire path of the net. If at any point on the net, the skew between true and complement exceeds “x mils”, this mismatch needs to be compensated within “y mils”. Representative values for x and y might be x = 20 and y = 600.
*   Backdrill. The Backdrill application, originally introduced in the Allegro PCB Editor, has undergone some significant enhancements and now introduced to OrCAD Professional. Backdrill data is now stored in the library padstacks and utilized at the design level during the analysis and backdrill generation process. Padstacks which do not have predefined backdrill information can be automatically updated at the design level by the entering the backdrill criteria prior to running backdrill. Design layers which are backdrilled will have Route Keepout Shapes generated to ensure design integrity is maintained with separate padstack definition controls for the backdrill start layer, internal layer and negative layer anti-pad geometries without the need of custom padstacks or scripts. All backdrill data is available on the individual Pin/Via objects displayed on the canvas or by simply querying the object using Show Element, and generating the Backdrill Legends and detailed Backdrill Report. In addition, the setup time for backdrill can now be improved as a result of algorithms designed to create intelligent layer pairs.
*   Net Group Enhancements. The Net Group constraint object introduced in release 16.6 to replace the Bus constraint object has been enhanced in OrCAD Professional to support Nesting conditions. This may be useful in defining High Speed Interfaces.
*   Design Previews. QIR 7 introduces design previews for a faster way of identifying and opening designs. Located on both the start page as well as the “open” dialog, users are now presented with a visual representation of their board files. Previews are generated and linked to the database with each save to ensure that they are always up to date.
*   New Board Creator. When starting a new board file, you are presented with a dialog allowing for quick and easy database setup. Using the same parameters as found in the Design Parameters dialog, you can adjust the database units, sheet size, accuracy, extents, and origin location for designs. As the you update or change the parameters, the dynamic preview located on the right side of the form updates to reflect the selections. The origin is represented by the location of the red dot.

### QIR 6

*   New Design for Assembly (DFA) Rules. Newly added Design for Assembly (DFA) constraints are located under the Manufacturing category in Constraint Manager.
*   DFA Outline Rules. Outline checks for DFA provide rules for checking minimum spacing between component bodies to the DESIGN\_OUTLINE and component bodies to CUTOUT subclasses. For every component, DFA\_BOUND takes first precedence followed by PACKAGE\_BOUND.
    *   Minimum spacing for pastemask to DESIGN\_OUTLINE and CUTOUT subclass rules are also part of this category.
*   DFA Spacing Rules. Minimum DFA spacing rules for various mechanical hole types to component bodies, as well as component pins to other component bodies, are defined in Constraint Manager. Other spacing checks include pastemask to pastemask and pastemask to via minimum spacing.
*   DFA Pastemask Rules. Pastemask checks detect the annular ring of the pastemask to SMD copper pin pad, missing pastemask on any SMD pin pad, and pastemask to other mask openings, such as soldermask and coverlay.
*   STEP Package Mapping. The ability to remove the mapping of all STEP models to all symbols in a layout has been added to the Device/Package STEP Mapping dialog box. Click Purge button located in the lower center of the dialog box. A confirmation message displays.
*   STEP Export Options. An option to use the basic symbol geometry and ignore mapped STEP models for of a layout drawing to a STEP file has been added. Enabling the Ignore STEP model definitions option in the STEP Export dialog ignores the STEP models assigned to the package symbols during the export process. The place\_bound height associated with those symbols are exported instead. Enclosure and assembly models are still exported as 3D STEP data.
*   Refresh Symbol Enhancement. You can now refresh symbols to the latest STEP models. A new option Update STEP mapping data only has been added in the Update Modules and Symbols dialog box.
*   Dynamic Shape Quality and Performance Initiative. Dynamic shape voiding has been improved in this QIR. Abnormalities referred to as “spikes” or “slits” in shapes are addressed. This enhancement reduces or eliminates the need to add oversize clearance properties as a workaround.
*   Place Replicate Enhancements. The MDD files can now be reused and replicated on boards with differing stackups. When a module stackup does not match the target board stackup, the layer mapping window appears. This window allows quick drag and drop operations to adjust and map the module stackup to the target board. Color coding helps to easily identify plane layers and signal layers. All via types are supported including through, micro, blind, and buried. Currently, all module layers must be mapped and reordering of module layers is not supported.
*   Route Clearance View. A new option Clearance View is added in the Options pane of the add connect command. When enabled, generates polygon around objects and displays the space available for routing in a channel.
*   Enhancements in Copy and Paste Commands. The Paste command now supports Retain net of shapes option that allows you to decide if the copied shape should retain the source net or inherits the net of the destination object. By default, this setting is enabled and source net is retained for a copied shape, which is the previous behavior.
*   Basic PDF Export. A non-intelligent PDF Export command that provides a method to print 2D PDF without tree structures and meta data is available in all OrCAD and Allegro layout editors. If the PDF Publisher license is not found, this version of PDF Export command becomes available.
*   Show Measure Update. Improvements has been made in areas of measuring to and from slots and embedded component mask pads.
*   Mechanical Hole Checking. A new design mode DRC, Mechanical Drill Hole Checks Use Hole Spacing Values checks mechanical pin to conductors spacing using layer-based spacing controls. This check restores the DRC to pre-17.2-2016 behavior.
*   Mechanical Pin to Mechanical Pin Spacing. is replaced by a more descriptive Mechanical Drill Hole to Mechanical Drill Hole spacing. Similarly, Mechanical Pin to Conductor spacing check is replaced by Mechanical Drill Hole to Conductor spacing check.
*   Zones with Placed Symbols. Now, you can edit or delete stackup of a zone that has placed symbols. You can modify the surface layers of the stackup. Modifying the stackup will update symbols and vias based on the layers defined in the modified stackup.

### QIR 5

*   Start Page. A new Start Page is now part of the editor canvas in the form of a second tab in the workspace. The Start Page tab allows you to access information, such as best practice papers, migration information, tips and tricks, and provides easy access to recently opened designs.
*   Design Workflow Pane. To assist new users, workflows are introduced into a new pane called Design Workflow. This initial workflow can be used to guide users in performing basic tasks. The workflow eliminates the need to search for the necessary menu, toolbar icons, or knowing the command. Clicking any option in the workflow pane brings up the dialog for that command.
*   Frequently-Used Icons. You can now assign frequently used icons to access right-click context menu. A maximum of 16 icons can be added.
*   Customizable Design Canvas. It is now easier to customize the canvas design to meet your requirements or design intent. Different views can be tailored to different aspects of the design. You can create a view for placement and maybe, another for routing, and a third for checking and producing deliverables. Each view can be customized, saved, and recalled when needed, including locating panes on a second or third monitor.
*   Improved Graphic Response Time. To improve graphic redraw response time, particularly for large designs with many small objects, you now have the ability to control the granularity of the design objects at different zoom levels. A new Object Filter control is provided in the Color dialog. This new control reduces the visual complexity of large designs and results in quicker redraws, panning and zooming. You can customize the level of pin/via granularity using a slider, which allows you to set the level of zoom at which small objects will come into view.
*   Find by Query Update. The find\_by\_query command allows viewing of all the objects in the Find by Query dialog. You can query a design database for certain type of objects by filtering them based on associated properties. The resulting matching objects are displayed in a table. Selecting items from the results table selects them in the canvas.
*   Assign Net to Via. The command is available in General Edit and Etch Edit Application modes. It is now possible to assign a net to a via. Hover over a single via or select multiple vias, right-click, and choose Assign Net to Via option.
*   Via Label Enhancement. As HDI trends continue to increase, the via labels become more important in identifying the begin/end layers of buried/blind vias that are used in the design. Labels are sequentially numbered beginning from the Top (as layer 1) to Bottom (as layer N). This ordering is not always synchronized with the actual layer names and forces designers to create matrices to understand the mapping.
*   Padstack Editor Enhancements:
    *   Donut pads, are now supported on mask layers
    *   Copy and paste functionality has been improved. You can now copy and paste layer information between design and mask layers
    *   Auto-scrolling within the working grid has been improved
*   In-Design DFx. For PCB designs, design for manufacturing flow has traditionally consisted of creating fabrication data at the end of the design, which is then sent to the fabricator. Hours, or days later, the fabricator sends back a list of issues to be addressed. The issues are corrected, and the cycle of data creation is repeated, resulting in lost days in the design to fabrication phase. File Locking: The File Properties dialog box now supports five categories of data lock types. They include Manufacturing, Database, Logic, Constraints, and MCAD/ECAD. If a particular option is selected, then the export command belonging to that group are disabled. For example, enabling the Manufacturing option disables the export of 2581, ODB++, artwork, stream out, DFx check, drill legend, NC Drill, NC Route, and Variant options.

### QIR 4

*   DRC Browser. The layout editors now include an advanced tool that enhances the ability to locate, review, and address DRCs. The DRC Browser UI contains various navigation, sorting, and filtering capabilities making it easier to focus on resolving design issues by DRC violation types and areas. The DRC Browser provides feedback on the number of errors, including bar and pie charts that are dynamically updated as issues are corrected or introduced, while editing the design.

The DRC Browser assists in correcting issues by providing:

*   Windowing into the location of a selected DRCA tristate status of DRC violations (Read, Unread, Review)
*   Various Navigation Methods
*   The ability to assign the waive DRC attribute to a selected DRC
*   DRC chart for graphical representation

### QIR 3

*   3D Canvas Update ([View Video](https://www.orcad.com/resources/library/orcad-3d-enhancements-172-qir3))
    *   3D to 2D Move Command. In this release, this 3D to 2D interaction has been enhanced so you can move a component in the 3D Canvas and that change is reflected and updated in the 2D design.
    *   Zone-Aware 3D. Zones now display actual thickness as specified in the Cross Section Editor.
    *   2D PDF and Export Dialog. A new Export dialog is added that can export a 2D PDF file.
    *   Display of Silkscreen Text, Rectangles, and Shapes in 3D Canvas. In the previous release, component silkscreen outlines (lines) were visible; in this release, text (both reference designators and free text) is also visible on the 3D Canvas.
    *   Isometric View. By default, the loaded design appears in an isometric view for better articulation of the 3D nature of the canvas and the design.
    *   Updated and New Panes. Two new panes: Messages and Options are added, and the Visibility pane is upgraded.
    *   Preferences Dialog. This release introduces a new Preferences dialog within the 3D Canvas window.
    *   Dynamic Ratsnets Movement. Rat lines are updated dynamically as the component is moved.
    *   Route Keepout Net Exceptions Quickly create route keepout groups with shapes.
    *   Visual Route Clearance. Visualize clearance rules in real time while you design. This feature visually evaluates if the spacing constraints defined in Constraint Manager are consistent with design intent.
    *   Padstack Editor XML Importability. New capability to import an XML file that contains the full padstack definition
    *   Import File Manager. The new Import File Manager function in the PCB Editor detects new or updated import files and displays a pop-up notification indicating the file is ready for import. 

### QIR 2

*   3D Canvas Update
    *   Full layer modeling. Including Dielectric, Soldermask, Pastemask, and Silkscreen layers.
    *   2D to 3D communication. When both 2D and 3D Canvas are visible, actions on the 2D workspace will be shown on the 3D Canvas.
    *   Export Capability. HSF, HMF, OBJ, PLY, and STL formats, exported files can be viewed.

### QIR 1

*   New 3D Canvas ([Watch Demo Video](https://www.orcad.com/resources/library/orcad-introduces-new-interactive-3d-canvas)):  Major 3D improvements have been added to OrCAD PCB Editor, delivering higher quality visualization and speed for design planning and viewing in 3D.
    *   3D Canvas Navigation: Mouse wheel zoom in and out, move canvas, and rotate canvas in any direction.
    *   3D Canvas Controls: Control visibility (on/off) of etch layers including lines, pins, shapes, and vias; controls the step model or placebound visibility for top, bottom, or embedded component layers.
    *   Basic Collision Detection: Overlapping symbols are checked and reported in the collision pane. Also, the symbol blinks a few times, so you can easily spot the symbol.
    *   Step Model Mapping to Devices: The Step Mapper user interface has been enhanced to support the mapping of a step model to a device as well as the package symbol.
    *   Bend Editor for Flex Design Applications: A new Bend Editor has been introduced, allowing you to define a bend line that represents the center of a bend zone arc. Once the line is defined, a bend area is created that visually displays the extents of the bend based on the bend values.
    *   Group Routing Update: A new option, Control Trace, shifts adjacent routes from that respective anchor trace
    *   Shape Application Mode Update: New functions to Shape Application Mode including: Add notch support for any angle; Assign parameters to multiple dynamics shapes; and Slide IX/IY support.
    *   Find by Query: The Find by Query function has been modernized to give you quick query access to all design elements on the canvas.

### 17.2 Base Release

*   Rigid Flex [(Watch Demo Video)](https://www.orcad.com/resources/library/orcad-flex-and-rigid-flex-technologies)
    *   Stack up by zone. The new feature improves MCAD-ECAD co-design and provides faster, easier definition of stack-ups for rigid-flex rigid designs.
    *   Inter design layer checks. The new inter layer functionality provides ability to check geometries between two different class/ subclasses for flex and rigid flex designs.
*   **Arc routing**. A new prototype feature to provide more efficient method to add routing during Add Connect by following an existing connect line or a route keep-in.
*   **Cross section editor.** Redesigned Cross Section Editor based on the spreadsheet technology found in Constraint Manager to provide one stop shop for features requiring cross section for their setup.
*   **New padstack editor.**Introducing modern user interface for convenient padstack creation with addition of new geometries and support for counter-bore/ counter-sink definitions and several new drill features.  ([Watch Demo Video](https://www.orcad.com/resources/library/orcad-172-2016-release-new-padstack-editor))
*   **Shape Edit Application Mode.** Introducing new functionality that is a fine tuning editing environment to increase efficiency with shape boundary editing and simplifying actions such as sliding a shape edge or adding a notch etc.
*   **Color and Visibility enhancements.** The Color Dialog box has been enhanced for better efficiency and ease of use for designers and the Visibility pane now provides access and control over layers other than the conductor layers.
*   **64 Bit Support**. Now available support for 64 bit OS with increase in memory size from 4GB to 18 Quintillion and support for Database sizes up to 3GB.More gains in performance for CPU intensive applications.
*   Display segment over voids. A new command _Segment Over Voids_ detects cline segments crossing adjacent plane layer voids. [(Watch Demo Video)](https://www.orcad.com/resources/library/orcad-pcb-designer-segment-over-voids)
*   Spread Line between Voids. New command to provide semi-automatic solution to spread channel based clines with respect to adjacent plane layer voids.
*   **Via2Via Line Fattening.** Users can increase line width between vias based on their definition of edge to edge clearance by using the “Line fattening” utility. [(Watch Demo Video)](https://www.orcad.com/resources/library/orcad-pcb-designer-via2via-line-fattening)
*   **Contour routing**. Now available in both single and multi-routing modes, contour hugging locks the current route to either the route keepin or adjacent cline.
*   **Group routing.** User can now perform group routing by window selecting around a group of objects(Clines, Vias, Pins, Rats) and be able to change the control trace from its initial location to user defined and go into single trace mode to complete routes.
*   **Gloss Commands.** Richer set of gloss commands like Eliminate Vias, Convert corners to ARC, Fillet and Taper traces and many more now available in OrCAD PCB Designer.
*   **Differential Pair Routing and DRC.** Users can now define physical and electrical rules for Differential pairs complemented by routing support.
*   Layer Set DRC and Routing. The new layer set functionality insures layer constrained nets are routed to wiring requirements by ‘locking routes’ to within the appropriate layer set(s) for the net based objects. [(Watch Demo Video)](https://www.orcad.com/resources/library/orcad-pcb-designer-layer-set-drc-and-routing)


* * *

## 16.6

- [What’s New in 16.6-2015](https://tiny-yhw.github.io//2023/06/13/cadence-allegro-whats-new-in-16-6-2015/){:target="_blank"}

### QIR 6

* Intelligently Exchange Stackup Information with IPC-2581. Automatically import and export stackup information from Allegro with the open IPC-2581 standard. This reduces manual entry errors and enables better collaboration and planning with manufacturers early in the design stage.
* IDX ECAD-MCAD Enhancements. A number of enhancements have been added to incremental data exchange (IDX) format for ECAD-MCAD collaboration
	- Bend Area Support: Flex circuit bend areas can be defined and/or imported from MCAD. Keepouts will automatically be generated and the bend area visually displayed on the PCB Editor canvas.
	- Multiple Heights for Components: Extruded components can contain multiple height areas using IDX.
	- Component Height DRC Updates: Component Height DRC can now account for global offset used to account for mask thickness.
	- User Defined Layers Exchange: Import/Export of user defined layers is now supported in IDX.
	- Copper Exchange: External layer etch can now be passed to the MCAD environment from PCB Editor. Allows for collaboration on Faraday cages and thermal analysis.
	- ECAD MCAD Data Compare: Verify MCAD and ECAD data are in synch before committing to manufacture. New compare tool will display differences visually in PCB Editor.
* File Locking Improvements. Additional capabilities have been added to specify file locking duration and what protocol to use to check lock time against.
* New Drafting Capabilities. Extend segments and trim segments drafting commands have been added
* Split Views. View multiple areas of the board at once with new split views feature. Great for helping with bus breakout routing and unraveling at each end of the interface.
* Find By Query (Unsupported Prototype). New query building engine to provide finer grained search and filter capabilities with AND, OR, and NOR logical operators.
* Windows 8.1 Support. OrCAD is officially supported on Windows 8.1.

### QIR 5

* Move Components with “Slide Etch” Option. New option designed to reroute etch attached to components being moved using conventional angles (45, 90).
* Dynamic Rat Suppression. When ‘Add Connect’ command is invoked, all rats except the active net are temporarily suppressed.
* New Drafting Commands. Added the relative move & copy command to move and copy elements about a user specified axis.
* Text Block Name Field. Select Text block by functional name (Assembly, Silkscreen, etc).
* Snap Pick Enhancement. Can now snap pick to pad edge, pad edge midpoint, and pad edge vertex.

### QIR 4

* STEP Support Enhancements. STEP support has been enhanced with the following new and improved capabilities:
	- Zoom capability was added to the mapping environment to aid in faster and more accurate STEP model mapping
	- Added fine-grain keyboard arrow key control to help with model alignment
	- Added the ability to map a course and detailed 3D model to a footprint
* Voids in Keepouts. OrCAD PCB Editor now supports voids in route keepout, placement keepout, via keepout, and test probe keepout.

### QIR 3

* STEP Update. Improved performance, fixed issues with export and import from MCAD tools.
* Allegro Drafting Prototypes (Early Adopter Features):
	- Delete by line
	- Delete by rectangle
	- Offset copy
	- Offset move
	- Add perpendicular line
* Pastemask DRC Update. Shapes drawn on the package geometry, top and bottom subclasses are now factored into the DRC check.
* Database Diary. Maintain a running log of comments with the design file (Available in OrCAD PCB Designer Professional ONLY).

### QIR 2

* STEP 3D and Model Support. STEP support 3D visualization, mapping, import and export (Early Adopter).

* * *

## 16.5

### New OrCAD Suites:

* OrCAD PCB Designer Standard (formerly OrCAD PCB Basics) without limitations of numbers of pins and net layers.
* OrCAD PCB Designer Professional (formerly OrCAD PCB Designer) with a larger number of high-speed features, constraint management capabilities, and included signal integrity analysis.

### GUI updates

* Access the status bar: Classes, sub-classes, and the Super Filter Modes applications and selections are available by the bar status of the tool.
*  Textures of the color: Fixtures are differentiated with filling and customizable, each color panel coloring can be completed by a texture.
*  Zoom-in window pick: Refreshes the display on a point or precise coordinates.
*  Differentiation between insulation and short-circuit DRCs: Net shorting the DRC are short-circuits and recognized as such in the error-count DRCs.

### New commands
* Minimum metal-to-metal DFF checks: Ensures that the distance between objects and copper is inspected, particularly when certain spacing rules are disabled.
* Duplicate drill hole: This audit checks for overlapping holes at the same coordinates.
* Table of cross-section: This new command allows creation of a cross-section image of the PCB with all types of vias used on design.
* Placement: The import file placement now includes an option to import components to contact with the face and the angle indicated in the file place_txt.txt.
* Viewing via label: As soon as a blind via, buried, or μvia is used, its label can be displayed.

### New Placement Mode. Dedicated environment for tailored placement tasks:

* Single click to move a component.
* Accessible by simply passing through the object
* Alignment of components
* Placement replication (including etch)

### Constraints and High-Speed Design (PCB Professional Only)

* Differential Pair Support: Differential pairs can be routed according constraints with DRCS recognized by the constraint manager (primary gap, length uncoupled, coupled tolerance, gap and neck width).
* Rules by zones (Regions): Stress areas are present in the Structure Constraint Manager, with rules routing and physical spacing by region, region class, region class-class, same net, differential pair gap, width, and layer.
* Min/max etch-length constraints: Total etch-length control is possible on the net in the Constraint Manager with a minimum and maximum distance.
* Delay tuning: The length adjustment (Delay Tune) is available using forms of elongation type accordion, trombone, and teeth saw.
* Automated test prep: Automatically generate test points for test fixtures in PCB.

### Other Updates

* 3D display: Added option for dynamic update of PCB layers.
* File lock: When sharing files, it is possible to have multiple open instances of the same file. The \*.lck file now protects the edited file from being overwritten.
* Pad behavior: When the Enhanced Pad Entry option is selected when routing or sliding, the pads based on a form of shape are now recognized.
* Delete via structure: The structure of vias created with the fanout command can now be deleted.
* Color: The Color View window has a Save option, Flip Preserve State.