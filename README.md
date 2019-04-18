# The most friendly list of requests for Blackmagic Design Fusion
## Fusion 16
### UI

1. Node size scale is too big.
    - Currently Fusion 16 flow scale measurements are the same as in Fu9. For instance, the node name disappears from the view at the FlowView scale of 0.6 in both versions. But since the nodes in fu16 are initially bigger, the text disappears too early, and we end up with normal size nodes without any text. https://cl.ly/5741fc26e46e
    - minimum scale is also too large. Here's side-by-side comparison of the minimum size flow in Fu16 and Fu9 https://cl.ly/8d096181e9a4
    - node elements (arrows, lines) should gradually scale down when scale is below 1. Right now they are only scaled on flow scale < 0.6 

2. Underlay draw
    - Underlays are drawn inconsistently. With minimum scale they are represented as outlines. They should be filled instead. https://cl.ly/2900fe6495f4

3. Too much unused space:
    - Keyframes view as an example:
    https://cl.ly/62fc6277d620
        * line space too wide 
        * nodes list column is also too wide
        * unusable lock icon before node name (does not reflect if the node is locked, so what is it for?)
        * Feature request: add more articulate indication if the single keyframe is selected.

4. Three dots buttons in the window corners that do nothing (Inspector, Nodes window). If the menu is empty, the button should not appear https://cl.ly/a3f3ab9e9c55

5. On-screen view controls are hidden behind context menus, this triples the amount of clicks. We need DoD, lock view, show normalized buttons. Also show only selected tool button in Splines and Keyframes.

6. Oddly enough some buttons remained text only, such as `HQ`, `MB`, `Some`. We need an option for text-only Toolbar buttons, like in Fu9

7. Set viewer scale button does not toggle the dropdown. Scale menu is not activated when clicked on the scale size (only on the down arrow) https://cl.ly/85c39c43955a. This goes to any dropdown triangle buttons.

8. Animated elements should be highlighted, like in Fu9. Red dot is just not enough https://cl.ly/01a0a24552de. This will help also to distinguish whether High of Low group is animated in a Range Control

9. Multibutton control has to be actual buttons instead of dropdown menu - The dropdow hides the UI and produces unnecessary clicks: https://cl.ly/3bc9b8649f89

10. Add flexible layout to Fusion 16 UI. This is a huge theme, I'll just emphasize the small things. Fusion became an industry standard for VFX for the flexibility it gives the artist. It is not only about the tools you can build, but also about flexible UI. Someone needs huge node tree, someone needs vast viewer. Developers need a dockable console. Someone moves the Inspector to the left, because operates with left hand, and it just speeds up the whole workflow. Someone aligns the nodes vertically and put the node tree to the right. Someone has a bunch of scripts moved to customizable toolbar. So flexible layout is a must for Fusion. 
* Currently we can add new floating frame and partially move UI elements there, as suggested here: https://forum.blackmagicdesign.com/viewtopic.php?f=22&t=88866&start=50#p499609. The layout is saved with comp metadata, so theoretically it can be reused, but it does not show proper UI on launch. Here's a brief report for this issue: https://www.steakunderwater.com/wesuckless/viewtopic.php?p=23222#p23222

11. Add fullscreen UI for Fusion, add double monitor layout, like in Resolve (yes, we love Resolve too!)

12. Add parameters dropdown for current tool in Viewer, such as Transform Pivot, Rotation, Center, Size.

13. Add jump to currently viewed tool from the Viewer.

14. Right-left arrows in the viewer has to move polygon mask points. They are moving playhead instead. Currently in Fusion 16 we can move a point by 10 px with `Shift+Alt` pressed, and by 1px with `Shift+Ctrl+Alt`. This is not intuitive at all. 

15. Composition tabs dropdown shows `SubWnd` text instead of comp name. https://cl.ly/e2f0dfb261f6

16. Masked Background disappears on mask move: a) add BG with polygon, b) select all poinst and move: https://cl.ly/748406a06eb7

17. Remember panel sizes when show/hide -- Hide the flow by clicking the 'Nodes' button and then show it and the panel doesn't retain the size before hiding.

18. Move the Audio Enable button to the other side of the play controls and include a volume slider (same as resolve edit page)

19. Make the Inspector panel collapse down next to the flow instead of the views when clicking the arrow toggle in the upper right corner.

20. Add Alt-click action to the Spline and Keyframe buttons to collapse all other panels sharing the same space in one click (click on 'Spline' while holding alt or middle clicking and the 'Nodes' and Keyframes' panels are hidden instead of having split view, etc.)

21. Trim 10 to 16 pixels from the top and bottom of the top panel button bar and the main toolbar.

22. Trim 8 to 10 pixels from the height of the play control bar.

23. Include the current frame number in small type and top-justified right next to the red playhead in the time ruler.

24. Allow changing the currently viewed tool name by double-clicking the name in the view header bar.

25. Add long-click and/or right click dropdown to the toolbar buttons to show list of all alternate tools found in the same category as the default tool for the button.

26. Make the global and render frame range fields in the play contorl bar wider to fully display feet+frames when using that mode.

27. Additional Subview options: a. Add ability to drag a subview outside of the view panel b. Add ability to display multiple subviews in a separate standalone panel next to each view (like a slide out drawer) instead of just as overlays withint the views.

28. Bring back tabbed view in the lower part between different aspect like nodes, spline, key frames. The current solution when you have half of the space for each function its not ideal, there is not enough space to work. So to go from the Nodes to Spline and back we have to do 4 clicks to instead of two. Adding shortcut would also useful. 

29. The scaling on 4K monitors is problematic in Fusion and also in Resolve, there is only two options: 100% and 200%. On 4K laptop screen the scaling looks fine but on 32 inch 4K monitor the 100% is too small to see and 200% is too big, taking avay lots of space with no use that could be used to view the image or navigate the node graph.

30. Nodes should light up when processed much more than currently is. In F9 it was easy to se what's going on in both the node-viewer and the navigator but in F16 it's very hard to see. On green nodes it's extremly hard to see and when zoomed out so the text in the nodes hide, nothing at all indicates that nodes are being processed any longer.
One solution would be for the nodes to have a outline lighten up while they process. https://imgur.com/R22NNSJ

31. The expression-field should be multi-line to help writing big expressions. In F16 the field is even smaller than F9 and it's almost imposible to edit longer expressions. To spice things up, line number, syntax highlighting and error messages could also be added to even futher help expression writing. https://imgur.com/uGWgIzT


Other feature requests:

### Console
1. Expandable console UI with syntax highlighting

2. Console should be dockable

3. Save last commands history on Fusion restart

4. Add switch between layouts with console commands or scripts

### Rendering
1. add cache to disk format options

2. Fusion should only process the needed frames and nodes when rendering, meaning only the frames within the render nodes start and end time should be rendered. The result should be like when you're writing your own frame ranges in the render settings, the render jumps to the frames I'm telling it to render and skipps all the other frames.

3. Saver feature request: add option to skip existing sequence frames on rendering stage to speed up delivery.

4. There should be a cache-node. Currently it's hard to see if the node is cached or not, also the caching acts how ever it wants. Sometimes it doesn't update, sometimes it updates even when it shouldn't. A node would give the user more options like disk cache format as some nodes might need high quality caching while others can take very low quality. A checkbox could also be added to opt in/out on auto-updating the cache so the user itself can update the cache when ever it fits.

### 3D
1. add mesh clipping (not alpha, but real polygon slicing)

2. add Polygon count optimisation node (polygon reduction)

3. add Level of Detail Node (dependent on how far the camera is)

4. add cast shadows from all lights

5. Addition of own PBR Path Tracing Render Engine or support of already existing ones (like Octance, VRay, Redshift, Corona, Cycles, etc.)

6. Realtime PBR Render Engine for Previewing Shaders for Path Tracing Render Engine

7. add Projection mode for spherical camera

8. add Enable decay on camera projection

9. Lights with specular only mode


### Nodes and Flow
1. add batch change properties for multiple selected nodes.

2. add Copy tool with keystroke-mouse drag

3. scripts with UI should be dockable within native interface

4. add modifiers as tools for the flow, like masks

5. add colorcode for expression links

6. add alembic files by drag and drop

7. add choose layouts buttons (i.e toggle single/dual viewer with single button)

8. Collapse nodes group by doubleclick on the group's header.

9. Add bookmarking to flow and include a docked bookmarks panel with a show/hide button just like all other panels.

10. OCIO nodes should have a pre-divide/post-multiply checkbox.

11. Add the possibility to replace a node with another one from the flow with keystroke + mouse drag. Eg. I have a merge node connected to my tree but I want to change it to a bool already existing in my flow viewer. I should be able to hold down ctrl, drag the bool over my merge and they should swap places, connecting FG and BG (or other equal named inputs) automaticly.


### Media Management and Workflow
1. Add a scaled down media management page with project management / version and revision features like Generation.

2. Add external referencing of other .comp files so that a loader can read for all available savers from the externally referenced comp, let the user select which saver to pull results from, then checks for dependencies on disk. If a dependency doesn't exist on disk, then the external comp frame gets rendered automatically and saved to disk according to the saver parameters and subsequently loaded into the current open comp. - This is useful for templating, adding overlays and watermarks, pre-comps, and merging split comps.
