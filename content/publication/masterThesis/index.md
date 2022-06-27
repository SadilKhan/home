---
abstract: "In this report, we present a novel approach for 3D medical image segmentation using
point clouds. 3D Convolutional Neural Networks have been the most dominating
networks in medical image processing but they require large memory footprints and
training samples. Hence we used point clouds to represent the image instead of voxels.
Point clouds are lightweight and contain shape and smoother surface information.
We extracted the point clouds from 3D voxel images using canny edge detection.
We modified RandLa-Net, an attention-based point cloud segmentation network
with a feature extraction layer to aggregate local geometrical features with spatial
point features for our large-scale point cloud segmentation task. Our proposed model
performed better than the original network in multi-class as well as binary point cloud
segmentation tasks in Visceral dataset. Finally, we propose a model-independent step
to perform the image segmentation of the original 3D volumetric images in Visceral
dataset by mapping voxels in the point cloud space and adding it to the input point
cloud before being passed to the trained model. We performed many experiments on
the weights of the Cross-Entropy loss function for the class imbalance problem as well
as the intrinsic architectural properties of the model architecture like downsampling
factor and distinct latent vector learning that can be improved to perform better
segmentation."
author_notes:
-
- University lecturer at INSA Lyon and Researcher at Myriad, CREATIS, INSA LYON.
- CNRS researcher at CREATIS, INSA Lyon.
- CNRS Researcher at LIRIS (Origami team)
authors:
- admin
- Razmig Kéchichian
- Sébastien Valette
- Julie Digne
date: "2022-06-23T00:00:00Z"
doi: ""
featured: true
# image:
#   caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/pLCdAaMFLTE)'
#   focal_point: ""
#   preview_only: false
# projects:
#  - "content/projects/DEA/index.md"
publication: In *UJM*
publication_short: Master Thesis
publication_types:
- "7"
publishDate: "2022-06-23T00:00:00Z"
# slides: example
tags: [Image Segmentation, Deep Learning, 3D Computer Vision, Point Cloud]
title: Learning Shapes for Efficient Segmentation of 3D Medical Images using Point Cloud
url_code: ""
url_dataset: ""
url_pdf: "publication/masterThesis/report.pdf"
url_poster: ""
url_project: ""
url_slides: ""
url_source: ""
url_video: ""
---