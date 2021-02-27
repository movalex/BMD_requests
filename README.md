# The most friendly list of requests for Blackmagic Design Fusion
## Fusion 16/17
### UI
1. Too much of unused UI space:
    - ~~Vewer UI elements can be twice as narrow: https://cl.ly/661278c2b3eb~~ (TimeView panel can be hidden with `comp:ShowView("LayoutStrip", false)`)
    - Keyframes has unusable lock icon before node name (does not reflect if the node is locked, so what is it for?)   https://cl.ly/ac13884063b2
2. There's too much empty space on the left side of the Inspector: https://cl.ly/15024d65d7e7, https://cl.ly/347084b4adcc
3. ~~Three dots buttons in the window corners that do nothing (Inspector, Nodes window). If the menu is empty, the button should not appear~~ https://cl.ly/a3f3ab9e9c55 <fixed in Fusion 17>
4. Some Viewer controls are hidden behind context menus, this triples the amount of clicks. We need ~~DoD~~, lock view, show normalized, Gain/Gamma buttons, `fit` view button. Also `show only selected tool` button in Splines and Keyframes (now DoD appears on long press of RoI button - v16.1)
5. Add an option for text-only Toolbar buttons, like in Fu9 (options like: only icons, only text, or both, icon with text). Also make it detachable ~~and customizable~~ toolbar. <customizable toolbar added in Fuison 17>
6. Set viewer scale button does not toggle the dropdown. Scale menu is not activated when clicked on the scale size (only on the down arrow) https://cl.ly/85c39c43955a. This goes to any dropdown triangle buttons.
7. Show animated parameters with green highlight in Inspector, like in Fu9. Here's how it can be implemented: https://cl.ly/01a0a24552de. This will help to distinguish whether High of Low group is animated in a Range Control.
8. ~~Polyline Shape animation does not have animation indicator at all https://share.getcloudapp.com/llu4z48w~~ (fixed in 17)
9. Multibutton control has to be actual buttons instead of dropdown menu - The dropdown hides the UI and produces unnecessary clicks: https://cl.ly/3bc9b8649f89
10. ~~Add flexible layout to Fusion 16 UI.~~. <Save and recall layouts feature is still available, but not implemented officially. See layouter script https://gitlab.com/WeSuckLess/Reactor/-/blob/master/Atoms/com.AlexBogomolov.Toolbar16/Scripts/Comp/Toolbar16/Layouter.lua Custom Fusion layouts now available in Davinci Resolve 17>
11. Node tile colors should not be limited to 16 pre-defined options. They should be adjusted with a full RGB spectrum
12. ~~Add fullscreen UI for Fusion Studion on Windows, add double monitor layout, like in Resolve.~~ <this can be achieved with floating windows>
13. Add parameters dropdown for current tool in Viewer, such as Transform Pivot, Rotation, Center, Size: https://cl.ly/b042d3674896
14. ~~Jump to currently viewed tool from the Viewer is not working~~ <fixed in Fusion 17>
15. Right-left arrows in the viewer has to move polygon mask points. They are moving playhead instead. Currently in Fusion 16 we can move a point by 10px with `Shift+Alt` pressed, and by 1px with `Shift+Ctrl+Alt`. This is not intuitive at all.
16. ~~Composition tabs dropdown shows `SubWnd` text instead of comp name. https://cl.ly/e2f0dfb261f6~~ <fixed in Fusion 17>
17. Timeline ruler can be hidden by the Ease In / Ease Out controls in Spline editor.
18. ~~Masked Background disappears on mask move: a) add BG with polygon, b) select all points and move: https://cl.ly/748406a06eb7~~ <fixed in v16.1>
19. ~~Remember panel sizes when show/hide -- Hide the flow by clicking the 'Nodes' button and then show it and the panel doesn't retain the size before hiding.~~ <fixed in 16.1>
20. Make an option for the Inspector panel to collapse down next to the flow when clicking the arrow toggle in the upper right corner.
21. ~~Add Alt-click action to the Spline and Keyframe buttons to collapse all other panels sharing the same space in one click. Click on 'Spline' while holding alt and the 'Nodes' and Keyframes' panels are hidden etc~~ <this can be achieved with layout commands binded with hotkeys>
22. ~~Trim 10 to 16 pixels from the top and bottom of the top panel button bar and the main toolbar. Trim 8 to 10 pixels from the height of the play control bar.~~ <Fusion 17 now has more dense font spacing in UI, Timeview and ActionStrip can be disabled via scripting>
24. Allow changing the currently viewed tool name by double-clicking the name in the view header bar.
25. Add long-click and/or right click dropdown to the toolbar buttons to show list of all alternate tools found in the same category as the default tool for the button.
26. Make the global and render frame range fields in the play control bar wider to fully display feet+frames when using that mode.
27. ~~Bring back tabbed view in the lower part between different aspect like nodes, spline, key frames. The current solution of having half of the space for each function is not ideal, there's just not enough space to work. So to go from the Nodes to Spline and back we have to do 4 clicks to instead of 2. Adding shortcut would be also useful.~~ tabbed view is possible with floating window. But this still has some bugs. 
28. The scaling on 4K monitors is problematic in Fusion and also in Resolve, there is only two options: 100% and 200%. On 4K laptop screen the scaling looks fine but on 32 inch 4K monitor the 100% is too small to see and 200% is too big, taking away lots of space with no use that could be used to view the image or navigate the node graph. Add native scaling support, at least 150%. Ideally - any Windows or Mac scaling (see https://www.steakunderwater.com/wesuckless/viewtopic.php?p=33497#p33497)
29. Nodes should light up when processed much more than currently is. In F9 it was easy to see what's going on in both the node-viewer and the navigator but in F16 it's very hard to see. On green nodes it's extremely hard to see and when zoomed out so the text in the nodes hide, nothing at all indicates that nodes are being processed any longer. One solution would be for the nodes to have a outline lighten up while they process. https://imgur.com/R22NNSJ
30. The expression-field should be multi-line to help writing big expressions. In F16 the field is even smaller than F9 and it's almost impossible to edit longer expressions. To spice things up, line number, syntax highlighting and error messages could also be added to even further help expression writing. https://imgur.com/uGWgIzT
31. Gamma/Gain sliders are affected by Show controls option (bug). https://cl.ly/818f85e53545
32. ~~3D Viewer lacks button controls for Display Lights, Shadows, Wireframe, Fast Transparency~~ implemented in 16.1
33. Here's a great Fusion [UI tweak](https://twitter.com/Fifty_5o/status/1191060578158166017) by [@Fifty_5o](https://twitter.com/Fifty_5o) to take into considereation ![](https://i.imgur.com/0UmaUsV.jpg)
34. Sticky notes should not have be highlighted on mouse hover. This will prevent unnecessary flow blinking. Sometimes notes are used as Underlays, since the text in the note is visible from any zoom size. This color blinking prevents Notes to be used the usual way in Fusion 16. Example: [blinking in Fusion 16](https://p27.f0.n0.cdn.getcloudapp.com/items/jkunJnKm/Screen+Recording+2019-12-10+at+02.14.56.72+PM.gif?v=d70c3e8a2fe51b31a9e71f00e2118136), [correct behavior in Fusion 9](https://p27.f0.n0.cdn.getcloudapp.com/items/yAuLoLZd/Screen+Recording+2019-12-10+at+02.20.33.88+PM.gif?v=d562c0fe92f59bd0a429754bd1114434)
35. Sticky Notes should be able to be recolored. Currently Set color option is `Clear color` only.

Other feature requests:

### Console and Scripting
0. We need an updated Scripting manual, with all new features and changes applied since Fusion 8.
1. Expandable console UI with syntax highlighting and optional multiline editing.
2. Console or any script window should be dockable
3. Save last Console commands history and preserve them on Fusion restart
4. Add option for verbose logging of all actions with and without hierarchy - This could be a separate tab within the console
    a. This will help with troubleshooting exactly where stuff breaks as we can see all actions executed up to that point
    b. This will help to quickly copy and paste paramters into expressions as we can tweak a paramter and then select and copy the console output.
    c. perhaps this would be useful for calling a script or command once, copying from console and then paste back into console input for repeated use.
5. Add a quick input field inline with the playhead controls or at the bottom of the page for console slash commands and drag and drop actions. This field would just be for typing or pasting in commands blindly without a feedback/log display. Right next to this field could be a button to bring up the whole console view
6. These Fusion features has to be implemented in scripting API. Scripting guide has to be updated accordingly:
    * Autodetect Clip Length with a command
    * Scale to fit FlowView with selected node with a command (center selected node in a Flow)
    * Select Upstream/Downstream nodes with a command
    * Force refresh source tile pictures
    * Show Tile Picture
7.FlowView:GetPos(tool) returns Integer values in Fusion 16 and 17. It should be Float instead! (bug)

### Rendering

1. Add cache to disk format options
2. Saver feature request: add option to skip existing (previously rendered) sequence frames on rendering stage to speed up delivery.
3. There should be a cache-node. Currently it's hard to see if the node is cached or not, also the caching acts how ever it wants. Sometimes it doesn't update, sometimes it updates even when it shouldn't. A node would give the user more options like disk cache format as some nodes might need high quality caching while others can take very low quality. A checkbox could also be added to opt in/out on auto-updating the cache so the user itself can update the cache when ever it fits.

### 3D

1. Add fully integrated 3D compositing environment with lights, camera snap, casted shadows.
2. 3D scene importing via FBX, Alembic, glTF and USDZ, including models, cameras, light, materials and rigs.
3. Add modify individual objects after Duplicate/Replicate/Particles/ https://www.steakunderwater.com/wesuckless/viewtopic.php?f=6&t=2839
4. Import 3D models from Maya, 3DSMax, Cinema4D and more
5. 3D importing from scenes with matched animation curves, stereo cameras, lighting and multilevel materials
6. Relighting using rich deep pixels and reshading tools to a full GPU renderer.
7. Add mesh clipping (not alpha, but real polygon slicing)
8. Add Polygon count optimization node (polygon reduction)
10. Add Level of Detail Node (adjust model complexity based on camera position)
11. Add option to cast shadows from all lights
12. Addition of own PBR Path Tracing Render Engine or support of already existing ones (like Octane, VRay, Redshift, Corona, Cycles, etc.)
13. Realtime PBR Render Engine for Previewing Shaders for Path Tracing Render Engine (or Hybrid PBR for previews, Redshift for Final Renders) 
14. Add Projection mode for spherical camera
15. Add Enable decay on camera projection
16. Add lights with specular only mode
17. Add a new tool for mesh point manipulation that gets all points from its input and creates a cage for morphing at various subdivision levels. (similar to the correction deformer in Cinema 4D)
18. Replace Material with preserve Bump option. Would allow complex modeling using normal maps, then apply a few Texture and Shading Materials while preserving the bump.
19. Matte object with inverse effect. Shows what is in front of object only (similar to slice)
20. Matte option to use alpha and inverse alpha from images applied to image planes and projections.
21. UV mapping ID's. This is very important if you want to use a different mapping for displace3D

### Nodes and Flow

1. ~~Add batch change properties for multiple selected nodes.~~ (see Attribute Spreadsheet script https://www.steakunderwater.com/wesuckless/viewtopic.php?p=35321#p35321)
2. Copy tool with keystroke-mouse drag (i.e. ALT+mouse drag)
3. Scripts with UI should be dockable within native interface
4. Add modifiers as tools for the flow. These nodes has to perform operations with channels, Gradients, texts, Points and so on. So the single modifier would be easily reused in the flow. And add an option for existing tools to expect input from these modifier nodes. Tool modifiers in their current state may become very messy in a short time. Here's an example of the setup for an object orienting along it's path https://cl.ly/64ffe5c24da4
5. Hold Output (CMD+U) does not work in Fusion 16 — it does not prevent the node tree from being calculated on playback.
6. TextPlus follower modifier: add an option to skip spaces between words in Follower Timing page. Delay type dropdown should include: Between each character -- Between each character excluding spaces -- Between First and Last Character 
7. Add alembic files by drag and drop
8. Add choose layouts buttons (i.e toggle single/dual viewer with single button)
9. Collapse nodes group by double-click on the group's header (currently CTRL+E shortcut)
10. ~~Add bookmarking to flow and include a docked bookmarks panel with a show/hide button just like all other panels~~ (done in 17)
11. OCIO nodes should have a pre-divide/post-multiply checkbox.
12. Right-Click on a node to see example comps with this node (like Houdini). The right-click "show example comp" option simply opens a sample comp demonstrating the tool usage.
13. Add the possibility to replace a node with another one from the flow with keystroke + mouse drag. Eg. I have a merge node connected to my tree but I want to change it to a Bool already existing in my flow viewer. I should be able to hold down Ctrl, drag the Bool over my merge and they should swap places, connecting FG and BG (or other equal named inputs) automatically.
14. Add the option to open node groups in full flow views (ether as sub tabs or replace the flow content with group and include an exit button)
15. Add a filtering dialog that highlights the border of all nodes in the flow of a selected type, active/inactive within a given frame range, contain expressions, contain custom controls, or contain keyframes.
15. Overhaul the Custom Controls interface so it is easier to use and commit changes without closing the interface. See Cinema 4D's Custom User Data Dialog as a perfect example of how it could be. https://help.maxon.net/us/pics/020053.jpg
16. Duplicate tool (Dup) should not clip DoD to the frame size. Instead we should have to move duplicate source beyond frame and still have correct duplicates. Right now it looks like this (wrong behavior): https://cl.ly/7bfad0d58350
17. ~~It is not possible to move keys a single frame left or right with a keystroke on Windows - Fusion 16 beta3. `ctrl+alt+right` instead moves to 0.1 frame (bug)~~.  <correct keyframe nudge shortcut on Windows is `WIN+ALT`>
18. Bookmarks implemented in Fusion 17 should not only recall Flow position, but should activate the bookmarked tool.

### Media Management and Workflow

1. Add a scaled down media management page with project management / version and revision features like Generation.
2. Add external referencing of other .comp files so that a loader can read for all available savers from the externally referenced comp, let the user select which saver to pull results from, then checks for dependencies on disk. If a dependency doesn't exist on disk, then the external comp frame gets rendered automatically and saved to disk according to the saver parameters and subsequently loaded into the current open comp. - This is useful for templating, adding overlays and watermarks, pre-comps, and merging split comps.

### Fuse Development

* Add a GUI/ integrated IDE for developing Fuses and Macros. Within this GUI, add a sidebar with a library of preset functions and all available classes, etc. Also include a GUI section with Checkboxes and naming fields for FuRegisterClass. Include a dropdown menu to select which category the Fuse belongs in or create a new category.
