# SDB_exercise
Leveling exercises for satellite derived bathymetry on Google Earth Engine

### A quick step by step tasks to complete the generation of a depth image on code editor:

STEP 01: CREATE AREA OF INTEREST. 
Tip: to generate the file in GEE reading format, an option can be using the link: https://geojson.io/#map=2/20.0/0.0

STEP 02: CONFIGURE THE TRAINING FILE TO IMPORT INTO GEE AS ASSET. PLOT THE POINTS ON THE MAP.
Tip: The example file can be downloaded from this repository (for Babitonga Bay, SC, Brazil). Don't forget to check the coordinate system!

STEP 03: SELECT AN IMAGE BY CHOOSING CLOUD COVERAGE, DATING AND CUTTING BY GEOMETRY FOR EACH MISSION (LANDSAT-5, LANDSAT-8, LANDSAT-9 AND SENTINEL-2). 
PLOT ALL ON THE MAP AND EXPORT ONE OF THE IMAGES TO GOOGLE DRIVE.
Tip: To complete the export, take care of submitting tasks in the right panel.

STEP 04: BUILD A COLLECTION BY CHOOSING CLOUD COVERAGE, CUT BY GEOMETRY AND ORGANIZE BY DATES FOR A MISSION OF YOUR CHOICE. PRINT THE COLLECTION ON THE CONSOLE GENERATED.
Tip: There are different functions in GEE to crop single images and collections from geometry.

STEP 05: REALIZING THAT FOR THE AREA OF INTEREST ARE TWO SENTINEL IMAGES REQUIRED, ASSEMBLE A MOSAIC.
Tip: create image-type variables from the name (ID) of the images, then an image collection that will make up the mosaic.

STEP 06: FROM THE GENERATED COLLECTION, APPLY NDWI TO THE ENTIRE COLLECTION.
Repeat the previous step (NDWI) for a single, better quality image.

STEP 07: MASK LAND VALUES FROM THE NDWI OF THE SINGLE IMAGE FROM THE PREVIOUS STEP, GENERATING NEW IMAGE. PLOT THE MASKED IMAGE ON THE MAP (WATER FEATURES ONLY).
Tip: use the NDWI values to mask the original single image.

STEP 08: FROM THE INDICATED CONSTANTS M0 = -96 AND M1 = 95, APPLY THE BATHYMETRIC INVERSION METHOD (STUMPF ET AL. 2003) ON THE ALREADY MASKED SELECTED IMAGE.
Tip: follow the GEE code model below:
      var m0…
      var m1…
      var nameFuncion = function (image) {
      var sdb = “write the STUMPF equation without the constants (m0 and m1) and rename”
      image = image.addBands(sdb);
      var depth = “re-write the equation applying the constants m0 and m1 and rename”
      return image.addBands(depth);
      };

STEP 08: PLOT THE RESULT OF THE BATHYMETRIC INVERSION ON THE MAP AND EXPORT THE DEPTH LAYER/BAND TO GOOGLE DRIVE.
Tip: select only the depth band created in the previous step (depth).

STEP EXTRA: IN GIS SOFTWARE, INTERPOLATE THE BATHYMETERY VALUES FROM THE TRAINING FILE TO THE SAME RESOLUTION OF THE GENERATED IMAGE (DEPTH), USE THE INTERPOLATOR OF YOUR PREFERENCE.
STEP EXTRA: SUBTRACT THE TWO RASTER LAYERS (DEPTH WITH BATHYMETRIC INVERSION AND TRAINING FILE INTERPOLATION). PLOT THE DIFFERENCE MAP WITH COLOR BAR.

👨‍💻💪 I hope you'll enjoy this quick start --> see the resolution in the repository 
