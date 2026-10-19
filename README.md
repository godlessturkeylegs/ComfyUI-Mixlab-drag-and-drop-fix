# ComfyUI Mixlab Drag-and-Drop Fix

A community workaround for an issue where **ComfyUI-Mixlab-Nodes interferes with ComfyUI's native drag-and-drop functionality**, preventing workflow JSON files from loading when dragged into the interface.

## The Problem

Some versions of Mixlab register a global JavaScript `drop` event listener that can interfere with ComfyUI's native file handling.

This may cause:

- Workflow `.json` files to fail when dragged into ComfyUI.
- Drag-and-drop behavior to stop working as expected.
- ComfyUI to ignore dropped workflows while Mixlab is installed.

## The Fix

The modified `ui_mixlab_fixed.js` file changes how Mixlab handles dropped JSON files to reduce interference with ComfyUI's native drag-and-drop functionality.

**Note:** This is an unofficial community workaround, not an official Mixlab update.

## Installation

1. **Close ComfyUI** before making changes.

2. Navigate to your Mixlab installation directory:

   ```text
   ComfyUI/custom_nodes/comfyui-mixlab-nodes/web/javascript/
   ```

3. Find the original file:

   ```text
   ui_mixlab.js
   ```

4. **Back up the original file** by renaming it:

   ```text
   ui_mixlab.js.bak
   ```

5. Download `ui_mixlab_fixed.js` from this repository.

6. Copy it into the same `javascript` directory.

7. Rename the downloaded file from:

   ```text
   ui_mixlab_fixed.js
   ```

   to:

   ```text
   ui_mixlab.js
   ```

8. Restart ComfyUI.

9. Hard-refresh your browser using `Ctrl + F5`.

10. Test by dragging a ComfyUI workflow `.json` file onto the canvas.

## Reverting the Fix

If the modified file causes problems:

1. Close ComfyUI.
2. Delete the replacement `ui_mixlab.js`.
3. Rename `ui_mixlab.js.bak` back to `ui_mixlab.js`.
4. Restart ComfyUI and refresh your browser.

## Important Notes

- This workaround was developed while troubleshooting Mixlab drag-and-drop interference in September 2026.
- It has not been verified against every Mixlab or ComfyUI version.
- Updating Mixlab may overwrite the modified JavaScript file.
- Replacing the original file with an older version may remove newer Mixlab functionality.
- Always keep a backup before making modifications.

## Credits

Original Mixlab project:

https://github.com/shadowcz007/comfyui-mixlab-nodes

This repository provides an unofficial workaround for the drag-and-drop issue. It is not affiliated with the original Mixlab developers.

## Feedback

If this fix works for you, or you encounter problems with a particular Mixlab version, feel free to open a GitHub issue and include your ComfyUI and Mixlab versions.
