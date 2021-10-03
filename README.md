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

Using deep learning, the DEM filtering  is converted into a classification problem, ground and non-ground point. Actualy, this method is not a direct method, after classification, the DTM is generated from TIN using the ground points.

- [2D CNN based](https://www.mdpi.com/2072-4292/8/9/730)

  convert point cloud into image, then use 2D CNN based classification.

- 3D CNN based

  with the great sucess of [PointNet](https://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf), a lot of methods are proposed, for example, [PointNet++](https://arxiv.org/abs/1706.02413), [KPConv](https://openaccess.thecvf.com/content_ICCV_2019/papers/Thomas_KPConv_Flexible_and_Deformable_Convolution_for_Point_Clouds_ICCV_2019_paper.pdf), [RandLA-Net](https://openaccess.thecvf.com/content_CVPR_2020/papers/Hu_RandLA-Net_Efficient_Semantic_Segmentation_of_Large-Scale_Point_Clouds_CVPR_2020_paper.pdf) and so on. These methods are proposed based on computer vision dataset.

  From DSM to DTM, [Nearest Neighbor Network](https://arxiv.org/abs/2005.10745) combine two works, i.e. [Full 3D CNN](https://www.sciencedirect.com/science/article/pii/S0924271618300832) and  [PointNet](https://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf).

- other work

  (1) [two-level fusion network](https://www.sciencedirect.com/science/article/abs/pii/S0924271618300765?via%3Dihub)
  first use scene detection and then use deep learning to do point based classification using the scene recognition.

### DSM 

- DNN
  (1) [denoise problem](https://ieeexplore.ieee.org/document/8013741)

  convert the problem from DSM to DTM to a denoise problem in 1D.
  (2) [classifcation problme](https://www.isprs-ann-photogramm-remote-sens-spatial-inf-sci.net/II-3-W4/103/2015/)
  only classify the non-ground object in urban scenes.

### DSM+Image

- DNN

  [manul feature + FCN](https://www.sciencedirect.com/science/article/pii/S0924271618301643?casa_token=f0AKBx7DPNAAAAAA:-HQmTDB81ABV8pN81k4DHwfqVebwVPNyzVPi9RLiIpWaCmtyCoJfgeFXTMrsum1PrsSa_VuwdQ)

  calculate several man made features and then use FCN to obtain the final classification result.

### Other similar method

- normalized Digital Surface Model (nDSM) based 

  (1) [ResDepth](https://openaccess.thecvf.com/content_CVPRW_2020/papers/w11/Stucker_ResDepth_Learned_Residual_Stereo_Reconstruction_CVPRW_2020_paper.pdf)

  combine image and residual  DSM to improve the DSM result.

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

