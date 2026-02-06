---
title: "Converting GIS data to AutoCAD in ArcGIS Pro"
layout: "home"
description: "This tutorial will demonstrate how to convert geospatial datasets saved as shapefiles into AutoCAD format."
staff:
    - name: Nick Field
      link: https://library.utoronto.ca/staff/nick-field
      created_date: 2024-02-06
permalink: "/"  #! Remove this if not the homepage
---

# Converting GIS data to AutoCAD in ArcGIS Pro

This tutorial will demonstrate how to convert geospatial datasets saved as shapefiles into AutoCAD format.

1. Use the Add Data button to add each of the datasets you wish to convert to the map document.  
<img src='{{ '/assets/images/1_2.png' | relative_url }}' alt='drop down menu after clicking the Add Data button' title='' width='395' height='827' />
2. In order for your data layers to display properly in AutoCAD, they will all need to be projected into the appropriate coordinate system. (Unsure of what the appropriate projection is for your area of interest? Refer to[this help document](https://mdl.library.utoronto.ca/technology/tutorials/selecting-right-projection), or ask a staff member for assistance in helping you determine it.) You can find out what coordinate system each layer is associated with by right-clicking on the layer name in the Table of Contents, selecting Properties… and clicking on the Source tab in the Layer Properties window.  
<img src='{{ '/assets/images/2_1.png' | relative_url }}' alt='The properties window open, on the source tab with the projected coordinate system row highlighted' title='' width='992' height='504' />
3. If your datasets are correctly projected, skip to step 5. If any of your layers need to be projected, open the ArcToolbox window by clicking on the red toolbox. Expand Data Management Tools, then Projections and Transformations, then Feature, then click on Project.  
<img src='{{ '/assets/images/3_1.png' | relative_url }}' alt='three sub photos, just showing the steps below' title='' width='459' height='364' />
4. In the Input Dataset or Feature Class box, use the dropdown menu to select the dataset you are looking to project. (If it has not yet been loaded into the map document, click on the folder icon to browse to the appropriate folder and select it.) The software will auto-detect the coordinate system of this dataset and list it in a light blue font below the Input dataset box.

    In the Output Dataset or Feature Class box, browse to the location where you would like to save the projected dataset and specify the filename. It is a good idea to indicate that these are the projected versions of other datasets, e.g. by adding “_projected” to the end of each filename.

    Click the box next to the Output Coordinate System box to select the projection that you would like to assign to the dataset. (*Tip:*if another one of your layers already has the correct projection selected, you can use the Import tool to find the right projection faster.) If the transformation involves a change in datum, you will be prompted to select a geographic transformation in the following box – a list of applicable transformations will be found in the Geographic Transformation dropdown menu. Click OK to project your dataset.

    When all of your datasets are projected into the same coordinate system, start a new map document by going to File > New. Add all of the newly projected datasets to the map  
        <img src='{{ '/assets/images/4_1.png' | relative_url }}' alt='The geoprocessing tab with boxes filled in' title='' width='569' height='296' />
5. Open the ArcToolbox window by selecting the Analysis tab along the ribbon, then clicking on Tools. Under Toolboxes, expand Conversion Tools, then To CAD, then click on Export to CAD  
<img src='{{ '/assets/images/5_1.png' | relative_url }}' alt='Export to CAD is highlighted within the toolbox ' title='' width='373' height='360' />
6. In the Input Features list, you can add datasets to be included as individual layers in the exported .dwg file by selecting them via the dropdown menu or by dragging them into the box below from the Table of Contents. Ensure that the file type specified in the Output Type dropdown menu is compatible with the software installed on the machine you are working on (just in case an older version of AutoCAD is installed) if you want to, check that your export worked correctly before taking your files with you.  
<img src='{{ '/assets/images/6_1.png' | relative_url }}' alt='Geoprocessing tab with inputs filled in ' title='' width='566' height='340' />
7. *For advanced users*: Are you looking to project a number of datasets at once? You can use the Batch Project function (located within ArcToolbox > Data Management Tools > Projections and Transformations > Feature > Batch Project) to project several datasets at once. However, you will need to run the function multiple times, once for each group of input datasets that share a particular datum.

    e.g. all datasets going from GCS_North_American_1983 to NAD_1983_UTM_Zone_17N will need to be done as one batch, all datasets going from GCS_WGS_1984 to NAD_1983_UTM_Zone_17N as another batch…

    Before beginning the Batch Project process, you will need to note the appropriate geographic transformation to use for each set of datum shifts. You can do that by opening up the Project tool again, selecting an input dataset and the output coordinate system, and taking note of the recommended geographic transformations that appear in the dropdown menu. You’ll need to write down the exact name of the geographic transformation applicable to each group of datasets that you will be projecting – note that if you are projecting into a coordinate system that uses the same datum as the input datasets, no geographic transformation is required (such as the GCS_North_American_1983 to NAD_1983_UTM_Zone_17N example mentioned above).  
        <img src='{{ '/assets/images/7.png' | relative_url }}' alt='Batch project highlighted in the toolbox' title='' width='533' height='95' />

    The Batch Project tool works much in the same way as the Project tool outlined in this tutorial, except the Geographic Transformation needs to be typed in manually, instead of selected from a dropdown list of potential options.

Technique: [Projecting](https://mdl.library.utoronto.ca/technique/projecting), [Converting data formats](https://mdl.library.utoronto.ca/technique/converting-data-formats) | Tools: [ArcGIS Pro](https://mdl.library.utoronto.ca/taxonomy/term/70) | Data Format: [Vector](https://mdl.library.utoronto.ca/data-format/vector)
