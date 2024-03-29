# Windowing and Protrusion Package 

This package is designed to allow the user to analyze local cell edge motions (e.g. protrusion and retraction) and to locally sample intracellular fluorescence signals in 2D fluorescence microscopy data. The cell interior is divided up into sampling “windows”, each of which is associated with a region of the cell edge based on proximity. This therefore allows the fluorescence time-series which are extracted from the cell interior to be correlated with the calculated cell edge velocities. Alternatively, it may be used solely to analyze cell edge motion, or solely to analyze spatiotemporal patterns of intracellular fluorescence.

### Associated paper
[**Functional Hierarchy of Redundant Actin Assembly Factors Revealed by Fine-Grained Registration of Intrinsic Image Fluctuations**](https://doi.org/10.1016/j.cels.2015.07.001), *Cell Systems*, 2015, 1(1):37-50, written by Kwonmoo Lee, Hunter L. Elliott, Youbean Oak, Alex Groisman, Jessica D. Tytell, [Gaudenz Danuser](https://www.danuserlab-utsw.org/).

### Important Note
The cell outline and therefore the sampling window locations and geometry are determined by the masks derived from the segmentation – these mark each pixel in the image as either “cell” or “background.” Additionally, the cell edge protrusion and retraction velocities are calculated from the motions of the edge of the cell outline identified in these masks. It is therefore required that the movie first be processed with the segmentation before it can be windowed or have protrusion vectors (cell-edge velocities) calculated. It is also important that this segmentation be of high quality (i.e. accurately identifies the cell boundary), as it will determine the quality of the cell edge velocities and window sample geometries. Simply run “Step 1: Segmentation” and “Step 2: Mask Refinement” (if necessary) and use the “Results” button to visually inspect the segmentation results. Then proceed to the protrusion and windowing analysis step to analyze your segmented cells.

### Workflow
The general process for analyzing a cell with this package is as follows. Detailed information for each step can be found in the help section for each step and for the settings for each step:

1. Create cell masks by first running the Segmentation and Mask Refinement steps. (or if Biosensors Package was already run, the masked created in this package may be used)
    - NOTE: There must be only one cell or cell region in each movie to be analyzed, but multiple movies can be analyzed sequentially. This can be ensured by running the MaskRefinement process.
    - NOTE: Currently the software can only analyze cells which either do not touch the image border for the entire movie, or which do touch the border for the entire movie, but not those which only touch the image border for a part of the movie.
2. Run protrusion calculation step to calculate edge velocities (optional)
3. Run Windowing step to create sampling windows
4. Sample the protrusion vectors (edge velocities) for each window (if calculated)  
5. Sample the fluorescence in each window. And you’re done!

----------------------
### Danuser Lab Links
[Danuser Lab Website](https://www.danuserlab-utsw.org/)

[Software Links](https://github.com/DanuserLab/)
