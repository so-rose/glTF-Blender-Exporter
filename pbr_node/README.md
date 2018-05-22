# glTF Compatible PBR Nodes

From Blender, use `File --> Append` (`SHIFT + F1`) or `File --> Link` (`CTRL + ALT + O`).
- Locate `glTF2.blend` in the file manager.
- Navigate into `glTF2.blend/NodeTree`.
- Select `glTF Metallic Roughness` or `glTF Specular Glossiness`, depending on your preferred workflow.
- See the Blender documentation for the difference between Linking and Appending.

## Principled Version
Alternatively, you may use a PBR implementation based on the new `Principled Shader`.
- Repeat the steps using `glTF2_Principled.blend` instead of `glTF2.blend`.
- This requires a Blender version of 2.79+ .
- Specular workflows are incompatible with the `Principled Shader`; as such you will not find the `glTF Specular Glossiness` node there.

## Common Pitfalls
There are certain common errorless pitfalls that may prevent a successful glTF material export.
- **DO NOT** build a node tree of any size behind these PBR nodes - the exporter cannot yet read them.
- **ONLY** directly set the color or numeric values of properties marked with `*Factor`. Example: `GlossinessFactor`, `BaseColorFactor`.
- **ONLY** directly connect an image texture to properties **NOT** marked with `*Factor`. Example: `Glossiness`, `BaseColor`.

## More Information
More information on these nodes can be found in the user documentation.
