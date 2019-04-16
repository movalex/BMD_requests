# The most friendly list of requests for Blackmagic Design Fusion and Resolve
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

10. Add flexible layout option. This is a huge theme, I'll just emphasize the small things. Fusion became an industry standard for VFX for the flexibility it gives the artist. It is not only about the tools you can build, but also about flexible UI. Someone needs huge node tree, someone needs vast viewer. Developers need a dockable console. Someone moves the Inspector to the left, because operates with left hand, and it just speeds up the whole workflow. Someone aligns the nodes vertically and put node tree on the right. So flexible layout is a must for Fusion.
* Currently we can add new floating frame and partially move UI elements there, as suggested here: https://forum.blackmagicdesign.com/viewtopic.php?f=22&t=88866&start=50#p499609. The layout is saved with comp metadata, so theoretically it can be reused, but it does not show proper UI on launch. Here's a brief report for this issue: https://www.steakunderwater.com/wesuckless/viewtopic.php?p=23222#p23222

11. Add fullscreen UI for Fusion, add double monitor layout, like in Resolve (yes, we love Resolve too!)

12. Add custom scripts buttons in a toolbar. Add movable toolbar. Ok, this goes to flexible UI too.

13. Add parameters dropdown for current tool in Viewer, such as Transform Pivot, Rotation, Center, Size.

14. Add jump to currently viewed tool from the Viewer.

15. Right-left arrows in the viewer has to move polygon mask points, not playhead.  

16. Composition tabs dropdown shows `SubWnd` text instead of comp name. https://cl.ly/e2f0dfb261f6

17. Move collapse group button to the right - or better, collapse by the doubleclick on the group header.


Other feature requests:

### Console
1. Expandable console UI with syntax highlighting
2. Dockable Console UI
3. Save last commands history on Fusion restart
4. Add switch between layouts with commands

### Rendering
1. Cache to disk format options

### 3d
1. Mesh clipping (not alpha, but real polygon slicing)
2. Polygon count optimisation node (ideally dependent on how far the camera is)
3. Projection mode for spherical camera
4. Enable decay on camera projection
5. Lights with specular only mode
6. Cast shadows from all lights.
7. Advanced UV Mapping tool

### Nodes and Flow
1. add batch change properties for multiple selected nodes.
2. add Copy tool with keystroke-mouse drag
3. add dock scripts UI in the main UI.
4. add modifiers as tools for the flow, like masks
5. add colorcode for expression links
6. add alembic files by drag and drop
7. add choose layouts buttons (i.e toggle single/dual viewer with single button)
