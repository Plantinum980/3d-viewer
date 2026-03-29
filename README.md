# 3D Models Folder

Place your OBJ files in this folder to load them into the 3D Viewer.

## How to Use

1. **Prepare your OBJ files**: Export or save your 3D models as `.obj` format
   - Make sure textures are optional (MTL files are not required but supported)
   
2. **Name them according to the viewer**: 
   - The filename in this folder must match the `filename` property in `MODEL_CONFIGS`
   - Example: If `filename: "component_1.obj"`, save your model as `component_1.obj` in this folder

3. **Update the HTML file**:
   - Open `index.html` in your 3D-viewer folder
   - Find the line: `const OBJ_FOLDER = "models/";`
   - Keep it as is (or adjust the path if needed)
   
4. **Update MODEL_CONFIGS**:
   - In `index.html`, modify the `MODEL_CONFIGS` array
   - Each config entry should have a matching `filename` property
   - Example:
   ```javascript
   {
     name: "My Part Name",
     filename: "my_model.obj",
     color: "#5792f2",
     // ... other properties
   }
   ```

5. **Test it**:
   - Open the HTML file in a web browser
   - The OBJ models should load automatically
   - If loading fails, check the browser console (F12) for error messages

## File Structure

```
3d-viewer/
├── index.html
├── models/
│   ├── component_1.obj
│   ├── component_2.obj
│   └── ...
└── README.md
```

## Supported OBJ Features

- ✓ Vertex positions (v)
- ✓ Vertex normals (vn)
- ✓ Texture coordinates (vt)
- ✓ Faces (f)
- ✓ Groups (g)
- ✓ Materials (mtllib / usemtl) - optional

## Notes

- OBJ files should be in ASCII format (not binary)
- Keep file sizes reasonable for web loading (usually < 10MB per file)
- Model materials and colors from the OBJ file are ignored; instead, colors from `MODEL_CONFIGS` are used
