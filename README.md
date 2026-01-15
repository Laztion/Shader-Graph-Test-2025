=
UNITY SHADER GRAPH
=
In Unity, Shader Graph for GUI (specifically uGUI) allows you to create procedurally generated, resolution-independent user interface elements such as buttons, health bars, and progress indicators.

1. Creating a GUI Shader Graph
As of 2026, the most streamlined way to create shaders for the Canvas system is using dedicated templates: 
New Shader: Right-click in the Project window and select Create > Shader Graph > URP (or HDRP) > Canvas Shader Graph.
Convert Existing: If you have an existing graph, go to Graph Settings, add a Universal or HDRP target, and change the Material dropdown to Canvas.

2. Key Features for UI
Resolution Independence: Because these elements are generated with math rather than textures, they remain sharp on any screen size (from mobile to 8K TVs) without consuming texture memory.
Aspect Ratio Adaptation: Shaders can automatically adjust to a UI element's dimensions using its width and height, eliminating the need for traditional nine-slicing.
UI-Specific Nodes: Special nodes like Render Type Branch allow you to handle different UI states (e.g., solid color vs. bitmap text) within a single graph.
Procedural Components: You can build interactive elements like sliders and meters that fetch their state directly from the UI component using nodes like Selectable State or Slider Value.

3. Customizing the Inspector GUI
If you want to customize how shader properties appear in the Unity Inspector (e.g., adding headers, toggles, or custom sliders), you can use the ShaderGUI API: 
Internal Support: In the Shader Graph Editor, you can use built-in attributes like [Enum], [PowerSlider], or [IntRange] on properties to change their display.
External Scripts: For advanced control, you can write a C# script inheriting from ShaderGUI and link it via the Custom GUI field in the graph's Master Node settings.

4. Implementation Example: Simple UI Distortion
To add a simple effect to a button: 
Create a UI Shader Graph.
Add a UV Distortion node.
Connect it to a Render Type Branch node.
Plug the branch output into the Base Color and Alpha ports of the Fragment node.
Apply the resulting material to your UI Image or Button component.

==================================================================================

THANKS
