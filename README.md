# SOTA of Deep learning based from DSM to DTM

## Introduction

En français,  Modèle numérique de surface (*MNS*) et Modèle numérique de terrain (*MNT*).

In AI4GEO project, I need to investigate this topic, so 

From *DSM*(Digital Surface Model) to *DTM*(Digital Terrain Model) is a  traditional topic, i.e. *DEM*(Digital Elevation Model) filtering. Among the traditional methods, the most famous method is using  progressive *TIN* (Triangular Irregular Network).

With the development of deep learning,  many methods and dataset are published, in this document, the methods and dataset is listed.

## Method

Because the input may be different, this will significantly influence the method, so the methods will be classified by the input. The input can be point cloud, DSM, DSM+Image.

### Point cloud based

Point cloud based usually  means LiDAR based, because LiDAR point cloud is accurate and with penetrability. On the other hand,  the noise distribution of dense matching is different among methods, so DSM filter on dense matching based point cloud is rare. 

Using deep learning, the DEM filtering  is converted into a classification problem, ground and non-ground point. 

- [2D CNN based](https://www.mdpi.com/2072-4292/8/9/730)

  convert point cloud into image, then use 2D CNN based classification.

  

- [3D CNN based](https://arxiv.org/abs/2005.10745)

  

- other work

  (1) [two-level fusion network](https://www.sciencedirect.com/science/article/abs/pii/S0924271618300765?via%3Dihub)
  first use scene detection and then use deep learning to do point based classification

  

### DSM 





### DSM+Image





## Dataset

### AHN dataset

For the AHN2 the ground and non-ground are saved in two files, can be found [here](https://esrinl-content.maps.arcgis.com/apps/Embed/index.html?appid=a0fac0a69f5343a3bbd15f5605dee4cc).

### [OpenGF](https://github.com/Nathan-UW/OpenGF)

This dataset is from open LiDAR dataset. 

### Other 

In AI4GEO, the dataset summary is vey detailed, can be found [here](https://confluence.cnes.fr/pages/viewpage.action?pageId=53008454).

A summary of the LiDAR dataset can be found [here](https://arheologijaslovenija.blogspot.com/p/blog-page_81.html).

## Contact

If you think you have any problem, contact [Teng Wu]<whuwuteng@gmail.com>

