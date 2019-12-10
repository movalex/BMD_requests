# The most friendly list of requests for Blackmagic Design Fusion
## Fusion 16
### UI
1. Node size scale is too big.
    - Currently Fusion 16 flow scale measurements are the same as in Fu9. For instance, the node name disappears from the view at the FlowView scale of 0.6 in both versions. But since the nodes in fu16 are initially bigger, the text disappears too early, and we end up with normal size nodes without any text. https://cl.ly/5741fc26e46e
    - minimum scale is also too large. Here's side-by-side comparison of the minimum size flow in Fu16 and Fu9 https://cl.ly/8d096181e9a4
    - node elements (arrows, lines) should gradually scale down when scale is below 1. Right now they are only scaled on flow scale < 0.6
2. Too much unused UI space:
    ~~- Vewer UI elements can be twice as narrower: https://cl.ly/661278c2b3eb~~ (TimeView panel can be hidden now, see Toolbar16 in Reactor)
    - Keyframes has unusable lock icon before node name (does not reflect if the node is locked, so what is it for?)   https://cl.ly/ac13884063b2
    - Tools window layout is aligned to the right, there's too much empty space on the left, and tool controls are too short: https://cl.ly/15024d65d7e7, https://cl.ly/347084b4adcc
3. Three dots buttons in the window corners that do nothing (Inspector, Nodes window). If the menu is empty, the button should not appear https://cl.ly/a3f3ab9e9c55
4. On-screen view controls are hidden behind context menus, this triples the amount of clicks. We need ~~DoD~~, lock view, show normalized, Gain/Gamma buttons, `fit` view button. Also `show only selected tool` button in Splines and Keyframes (now DoD appears on long press of RoI button - v16.1)
5. Add an option for text-only Toolbar buttons, like in Fu9 (options like: only icons, only text, or both, icon with text). Also detachable and customizable toolbar.
6. Set viewer scale button does not toggle the dropdown. Scale menu is not activated when clicked on the scale size (only on the down arrow) https://cl.ly/85c39c43955a. This goes to any dropdown triangle buttons.
7. Animated elements should be highlighted, like in Fu9. Red dot is just not enough https://cl.ly/01a0a24552de. This will help also to distinguish whether High of Low group is animated in a Range Control
7a. Polyline Shape animation does not have animation indicator at all https://share.getcloudapp.com/llu4z48w
8. Multibutton control has to be actual buttons instead of dropdown menu - The dropdown hides the UI and produces unnecessary clicks: https://cl.ly/3bc9b8649f89
9. Add flexible layout to Fusion 16 UI. This is a huge theme, I'll just emphasize the small things. Fusion became an industry standard for VFX for the flexibility it gives the artist. It is not only about the tools you can build, but also about flexible UI. Someone needs huge node tree, someone needs vast viewer. Developers need a dockable console. Someone moves the Inspector to the left, because operates with left hand, and it just speeds up the whole workflow. Someone aligns the nodes vertically and put the node tree to the right. Someone has a bunch of scripts moved to customizable toolbar. So flexible layout is a must for Fusion. Besides, flexible layout in standalone Fusion Studio can be a good selling point as opposed to Resolve's fixed UI Fusion.
10. Add fullscreen UI for Fusion Studion on Windows, add double monitor layout, like in Resolve (yes, we love Resolve too!)
11. Add parameters dropdown for current tool in Viewer, such as Transform Pivot, Rotation, Center, Size: https://cl.ly/b042d3674896
12. Add jump to currently viewed tool from the Viewer.
13. Right-left arrows in the viewer has to move polygon mask points. They are moving playhead instead. Currently in Fusion 16 we can move a point by 10px with `Shift+Alt` pressed, and by 1px with `Shift+Ctrl+Alt`. This is not intuitive at all. 
14. Composition tabs dropdown shows `SubWnd` text instead of comp name. https://cl.ly/e2f0dfb261f6
15. Masked Background disappears on mask move: a) add BG with polygon, b) select all points and move: https://cl.ly/748406a06eb7
16. Remember panel sizes when show/hide -- Hide the flow by clicking the 'Nodes' button and then show it and the panel doesn't retain the size before hiding.
17. Move the Audio Enable button to the other side of the play controls and include a volume slider (same as resolve edit page)
18. Make the Inspector panel collapse down next to the flow instead of the views when clicking the arrow toggle in the upper right corner.
19. Add Alt-click action to the Spline and Keyframe buttons to collapse all other panels sharing the same space in one click (click on 'Spline' while holding alt or middle clicking and the 'Nodes' and Keyframes' panels are hidden instead of having split view, etc.)
20. Trim 10 to 16 pixels from the top and bottom of the top panel button bar and the main toolbar.
21. Trim 8 to 10 pixels from the height of the play control bar.
22. Include the current frame number in small type and top-justified right next to the red playhead in the time ruler.
23. Allow changing the currently viewed tool name by double-clicking the name in the view header bar.
24. Add long-click and/or right click dropdown to the toolbar buttons to show list of all alternate tools found in the same category as the default tool for the button.
25. Make the global and render frame range fields in the play control bar wider to fully display feet+frames when using that mode.
26. Additional Subview options:
    a. Add ability to drag a subview outside of the view panel
    b. Add ability to display multiple subviews in a separate standalone panel next to each view (like a slide out drawer) instead of just as overlays within the views.
27. Bring back tabbed view in the lower part between different aspect like nodes, spline, key frames. The current solution of having half of the space for each function is not ideal, there's just not enough space to work. So to go from the Nodes to Spline and back we have to do 4 clicks to instead of 2. Adding shortcut would be also useful. 
28. The scaling on 4K monitors is problematic in Fusion and also in Resolve, there is only two options: 100% and 200%. On 4K laptop screen the scaling looks fine but on 32 inch 4K monitor the 100% is too small to see and 200% is too big, taking away lots of space with no use that could be used to view the image or navigate the node graph.
29. Nodes should light up when processed much more than currently is. In F9 it was easy to see what's going on in both the node-viewer and the navigator but in F16 it's very hard to see. On green nodes it's extremely hard to see and when zoomed out so the text in the nodes hide, nothing at all indicates that nodes are being processed any longer.
One solution would be for the nodes to have a outline lighten up while they process. https://imgur.com/R22NNSJ
30. The expression-field should be multi-line to help writing big expressions. In F16 the field is even smaller than F9 and it's almost impossible to edit longer expressions. To spice things up, line number, syntax highlighting and error messages could also be added to even further help expression writing. https://imgur.com/uGWgIzT
31. Gamma/Gain sliders are affected by Show controls option. Show controls should not affect Gamma/Gain UI (bug). https://cl.ly/818f85e53545
32. 3D Viewer lacks button controls for Display Lights, Shadows, Wireframe, Fast Transparency
33. TextPlus follower modifier: add an option to skip spaces between words in Follower Timing page. Delay type dropdown should include: Between each character -- Between each character excluding spaces -- Between First and Last Character 
34. Here's a great Fusion UI [tweak](https://twitter.com/Fifty_5o/status/1191060578158166017) by [@Fifty_5o](https://twitter.com/Fifty_5o) to take into considereation ![](https://i.imgur.com/0UmaUsV.jpg)
35. Sticky notes should not have their color changed on mouse hover. This will prevent unnecessary flow blinking. Sometimes notes are used as Underlays, since the text in the note is visible from any zoom size. This color blinking prevents Notes to be used the usual way in Fusion 16. Example: [blinking in Fusion 16](https://p27.f0.n0.cdn.getcloudapp.com/items/jkunJnKm/Screen+Recording+2019-12-10+at+02.14.56.72+PM.gif?v=d70c3e8a2fe51b31a9e71f00e2118136), [correct behavior in Fusion 9](https://p27.f0.n0.cdn.getcloudapp.com/items/yAuLoLZd/Screen+Recording+2019-12-10+at+02.20.33.88+PM.gif?v=d562c0fe92f59bd0a429754bd1114434)

Other feature requests:
### Console and Scripting
0. We need an updated Scripting manual, with all new features and changes applied since Fusion 8.
1. Expandable console UI with syntax highlighting and optional multiline editing.
2. Console should be dockable
3. Save last commands history on Fusion restart
4. Add switch between layouts with console commands or scripts
5. Add option for verbose logging of all actions with and without hierarchy - This could be a separate tab within the console
    a. This will help with troubleshooting exactly where stuff breaks as we can see all actions executed up to that point
    b. This will help to quickly copy and paste paramters into expressions as we can tweak a paramter and then select and copy the console output.
    c. perhaps this would be useful for calling a script or command once, copying from console and then paste back into console input for repeated use.
    
6. Add a quick input field inline with the playhead controls or at the bottom of the page for console slash commands and drag and drop actions. This field would just be for typing or pasting in commands blindly without a feedback/log display. Right next to this field could be a button to bring up the whole console view
7. All Fusion UI features has to be implemented in scripting API. Scripting guide has to be updated accordingly. Here's some missing features, but there can be more:
    * Autodetect Clip Length with a command
    * Scale to fit FlowView with selected node with a command (effectively centers selected node in a view)
    * Select Upstream/Downstream nodes with a command
    * Force refresh source tile pictures
    * Show Tile Picture
8. FlowView:GetPos(tool) returns Integer values in Fusion 16. It should be Float instead (bug)
### Rendering
1. Add cache to disk format options
2. Fusion should only process the needed frames and nodes when rendering, meaning only the frames within the render nodes start and end time should be rendered. The result should be like when you're writing your own frame ranges in the render settings, the render jumps to the frames I'm telling it to render and skips all the other frames.
3. Saver feature request: add option to skip existing sequence frames on rendering stage to speed up delivery.
4. There should be a cache-node. Currently it's hard to see if the node is cached or not, also the caching acts how ever it wants. Sometimes it doesn't update, sometimes it updates even when it shouldn't. A node would give the user more options like disk cache format as some nodes might need high quality caching while others can take very low quality. A checkbox could also be added to opt in/out on auto-updating the cache so the user itself can update the cache when ever it fits.
### 3D
1. Add fully integrated 3D compositing environment with lights, camera snap, casted shadows.
2. 3D scene importing via FBX, Alembic, glTF and USDZ, including models, cameras, light, materials and rigs. 
3. Render scenes with many millions of polygons and complex shading
4. Lightning fast GPU rendering with denoising
5. Import 3D models from Maya, 3DSMax, Cinema4D and more
6. 3D importing from scenes with matched animation curves, stereo cameras, lighting  and multilevel materials
7. Relighting using rich deep pixels and reshading tools to a full GPU renderer.
8. Add mesh clipping (not alpha, but real polygon slicing)
9. Add Polygon count optimization node (polygon reduction)
10. Add Level of Detail Node (adjust model complexity based on camera position)
11. Add cast shadows from all lights
12. Addition of own PBR Path Tracing Render Engine or support of already existing ones (like Octane, VRay, Redshift, Corona, Cycles, etc.)
13. Realtime PBR Render Engine for Previewing Shaders for Path Tracing Render Engine (or Hybrid PBR for previews, Redshift for Final Renders) 
14. Add Projection mode for spherical camera
15. Add Enable decay on camera projection
16. Lights with specular only mode
17. Add a new tool for mesh point manipulation that gets all points from its input and creates a cage for morphing at various subdivision levels. (similar to the correction deformer in Cinema 4D)
18. Replace Material with preserve Bump option. Would allow complex modeling using normal maps, then apply a few Texture and Shading Materials while preserving the bump.
19. Matte object with inverse effect. Shows what is in front of object only (similar to slice)
20. Matte option to use alpha and inverse alpha from images applied to image planes and projections.
21. UV mapping ID's. This is very important if you want to use a different mapping for displace3D
### Nodes and Flow
1. Add batch change properties for multiple selected nodes.
2. Add Copy tool with keystroke-mouse drag
3. Scripts with UI should be dockable within native interface
4. Add modifiers as tools for the flow ('Little nodes', like masks). These nodes has to perform operations
   with channels, Gradients, texts, Points and so on. So the single modifier would be easily reused in the flow. The
tools like: `Add`, `Mix`, `Extrapolate`, `Concatenate` and so on. And add an option for existing tools to expect input from
these modifier nodes. 
Tool modifiers in their current state may become very messy in a short time. Here's an example of the setup for an object orienting along it's path https://cl.ly/64ffe5c24da4
5. Add colorcode for expression links 
 
6. Add alembic files by drag and drop
7. Add choose layouts buttons (i.e toggle single/dual viewer with single button)
8. Collapse nodes group by double-click on the group's header.
9. Add bookmarking to flow and include a docked bookmarks panel with a show/hide button just like all other panels.
10. OCIO nodes should have a pre-divide/post-multiply checkbox.
11. Right-Click on option for example comps like Houdini. The right-click "show example comp" option simply opens a sample comp demonstrating the tool usage.
12. Add the possibility to replace a node with another one from the flow with keystroke + mouse drag. Eg. I have a merge node connected to my tree but I want to change it to a Bool already existing in my flow viewer. I should be able to hold down Ctrl, drag the Bool over my merge and they should swap places, connecting FG and BG (or other equal named inputs) automatically.
13. Add the option to open node groups in full flow views (ether as sub tabs or replace the flow content with group and include an exit button)
14. Add a filtering dialog that highlights the border of all nodes in the flow of a selected type, active/inactive within a given frame range, contain expressions, contain custom controls, or contain keyframes.
15. Overhaul the Custom Controls interface so it is easier to use and commit changes without closing the interface. See Cinema 4D's Custom User Data Dialog as a perfect example of how it could be. https://help.maxon.net/us/pics/020053.jpg
16. Duplicate tool (Dup) should not clip DoD to the frame size. Instead we should have to move duplicate source beyond frame and still have correct duplicates. Right now it looks like this (wrong behavior): https://cl.ly/7bfad0d58350
17. It is not possible to move keys a single frame left or right with a keystroke on Windows - Fusion 16 beta3. `ctrl+alt+right` instead moves to 0.1 frame (bug).
18. Hold Output (CMD+U) does not work in Fusion 16 — it does not prevent the node tree from being calculated on playback.
### Media Management and Workflow
1. Add a scaled down media management page with project management / version and revision features like Generation.
2. Add external referencing of other .comp files so that a loader can read for all available savers from the externally referenced comp, let the user select which saver to pull results from, then checks for dependencies on disk. If a dependency doesn't exist on disk, then the external comp frame gets rendered automatically and saved to disk according to the saver parameters and subsequently loaded into the current open comp. - This is useful for templating, adding overlays and watermarks, pre-comps, and merging split comps.
### Fuse Development
1. Add a GUI/ integrated IDE for developing Fuses and Macros. 
Within this GUI, add a sidebar with a library of preset functions and all available classes, etc. Also include a GUI section with Checkboxes and naming fields for FuRegisterClass. Include a dropdown menu to select which category the Fuse belongs in or create a new category.
