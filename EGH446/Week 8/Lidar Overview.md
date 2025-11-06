#Sensors #Lidar #Mapping

## What is Lidar?
* **LIDAR** stands for **Light Detection And Ranging**.
* It is **NOT** imagery. It is a point cloud of 3D data. This data can be shaded with intensity or color to create a relief image.
* **How it works**: An infrared (IR) beam is emitted from a sensor. The system calculates elevation based on the time it takes for the beam's echo to return.
* The **intensity** of the return signal can also be used to identify the surface type (e.g., water vs. land).

## Advantages
* Provides highly accurate elevation models.
* Can be used day or night.
* Can acquire data through cloud cover (unlike photography).
* Very cost-effective for large projects (e.g., airborne mapping).

## Limitations
* The IR beam **cannot penetrate tree cover** (except through gaps).
* Lidar **cannot penetrate deeply into water**.
* The **sheer size of the data** is a major issue (e.g., 250 GB for a small database), which prevents easy real-time use.
* Lidar is **indiscriminate**: it places elevation points on *everything*, including cars, houses, and trees, which must be filtered in post-processing.

## Lidar Data
* The data is a **point cloud**. Each point has at least 4 attributes: **X, Y, Elevation, and Intensity**.
* Common file extensions are:
    * **.las**: The standard exchange format from ASPRS.
    * **.laz**: A lossless compressed version of .las.
    * **.csv** or **.txt**: A text-based format.

## Applications
* 3D modeling.
* Powerline inspection.
* Forestry, flood studies, and large-scale mapping.