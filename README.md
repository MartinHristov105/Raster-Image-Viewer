# Raster Image Viewer and Editor (Console Application)

## Project Description
This project is a console-based raster image editor. It supports loading, processing, transforming, and saving raster images through user sessions.

## Supported Image Formats
- PBM
- PGM
- PPM
- BMP

---

## Screenshots

![demo](saves/demo.png)

![saveas](saves/1.png)

![save](saves/1_20260225_173715.png)

---


## Application Workflow

### Sessions
- The application starts without any loaded files or sessions.
- Use the `load` command to start a new session with one or more image files.
- Each session receives an unique ID (a whole positive number) to allow managing multiple sessions.
  
- Transformations apply to **all images** loaded in the current session.
- You can load/add images from random directories.
- For **correct** work you must create a **"saves"** folder in the **main** directory of the console application.
- Save, exit and saveas(without correct amount of provided names) by default save the new images in the **"saves"** folder.
- If you want to save outside this directory you should use **saveas** and write the correct directory + the file name. 
  
### Commands and Features

- **Convert to Grayscale**  
  `grayscale`  
  Converts all color images in the current session to grayscale. Already grayscale images remain unchanged.

- **Convert to Monochrome (Black and White)**  
  `monochrome`  
  Converts all images to strictly black and white pixels (no gray shades). Monochrome images remain unchanged.

- **Negative**  
  `negative`  
  Creates a negative (inverted tones) of all images in the current session.

- **Rotate and Flip Images**  
  `rotate left` / `rotate right` / `flip top` / `flip left`  
  Performs rotation or mirror transformations.

- **Undo Last Transformation**  
  `undo`  
  Reverts the last transformation applied in the current session. Has no effect if no transformations have been made.

- **Redo Last Undo**  
  `redo`  
  Reapplies the last undone transformation, if any.

- **Add Image to Current Session**  
  `add image02.ppm`  
  Adds a new image to the session. Previous transformations are **not** applied to this new image.

- **Save Changes**  
  `save`  
  Saves transformed images with a timestamp appended to the filename. Undo operations still work after saving and does not delete the saved files.

- **Save As**  
  `saveas newName1 newName2 ...`  
  Saves transformed images using the specified filenames. If fewer names are provided than images, default names (with timestamps) are used for the rest.

- **Session Info**  
  `list session`  
  Displays the current session’s ID and the images loaded, including their names and formats.

- **Paste Image**  
  `paste image_src image_dest posX posY`  
  Inserts pixels from `image_src` into `image_dest` starting at position `(posX, posY)`. The destination image expands if needed, and empty pixels are white.
  
- **Switch Between Sessions**  
  `switch <session_id>`  
  Changes the active session to the specified ID.

- **Exit Application**  
  `exit`  
  Exits the editor. If there are sessions with unsaved transformations, ask the user to save them before exiting.

---

---

## Learning Outcomes

- Image Processing Fundamentals: Gained experience working with raster images in multiple formats (PBM, PGM, PPM, BMP), including reading, manipulating, and saving them.

- Object-Oriented Design: Applied advanced OOP concepts in C++, creating a modular and maintainable codebase.

- Command-Based Architecture: Developed a robust command handling system (Load, Add, Save, SaveAs, Undo, Redo, Paste, Switch, ListSession, Exit) allowing flexible session management and image operations.

- File Handling & I/O: Learned to handle binary and text-based image file formats, including managing file paths, error handling, and format-specific parsing.

- Problem Decomposition & Modular Programming: Practiced dividing a complex project into clear modules 

---

## Future Improvements

Support for Additional Formats: Extend the application to handle modern image formats such as PNG, JPEG, and TIFF.

Graphical User Interface (GUI): Develop a GUI to make the application more user-friendly and interactive, laying the foundation for a full-featured raster image editor.

Enhanced Transformations: Add advanced image transformations, including cropping, scaling, blurring, and filters.

---

## Project Structure

```text
RasterImages/
├── main
└──── include/ .h files
  ├── src/ .cpp files
  ├── tests/ files for testing
  ├── saves/ dir for saving the results
├── .gitignore
└── README.md
```

---

## Author
- Martin Hristov - https://github.com/MartinHristov105