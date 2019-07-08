# Texturizing-FARO-SCENE-model-in-Agisoft-Metashape

# Description
When FARO SCENE is creating a 3D model first it generalizes point cloud to reduce the number of the triangles of the model. This has a significant effect on the texture of the 3D model. In the big projects, this issue is more pronounced. This repository is for showing the method to bypass the texturing defect of the FARO SCENE. 3D model exported from FARO SCENE can be texturized afterward in Agisoft Metashape, by using the panoramic images and locations of the scanner, which are also exported from FARO SCENE.

# Instruction
- Create 3D model in FARO SCENE
- Export Panoramic images from FARO SCENE
- Export scan locations from FARO SCENE (*.txt file)

- Open Agisoft Metashape project and load 3D model and Panoramic images
- In the camera calibrations change camera type to the spherical
- Important to not change names of the panoramic images
- Mask the bottom white part of the first image in the chunk
- Open scripting conlose and load run.py in arguments field type full path to the scan locations text file
- Workflow-Build Texture

# Script
Script converts scan locations to the agisoft camera transformation matrix and georeference each image in chunk coordinate system. 
The panoramic image has a field of view 300x360 degree. Therefore blank parts of the images need to be masked out. If the first image of the chunk is masked the script will copy the mask of the first image to all rest of the images of the chunk.
