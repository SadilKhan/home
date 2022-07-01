---
date: "2022-06-28T00:00:00Z"
external_link: ""
summary: Introduction to Point Cloud
tags:
- Deep Learning
- Point Cloud
- Segmentation
- Graph 
- Voxel
- MLP
title: Point Cloud
sutitle: Introduction to Point Cloud
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""
share: false
commentable: true
show_related: true
---

<script src="https://mickael.canouil.fr/post/floating-toc-in-blogdown/index.en_files/header-attrs/header-attrs.js"></script>
<script src="https://cdn.jsdelivr.net/gh/google/code-prettify@master/loader/run_prettify.js"></script>
<div id="TOC">
<ul>
<li><a href="#First_Point_Header">1. Introduction</a>
				</li>
				<li><a href="#Second_Point_Header">2. Point Cloud Generation Methods</a></li>
				<li><a href="#Third_Point_Header">3. Point Cloud Sampling Methods</a></li>
				<li><a href="#Fourth_Point_Header">4. Point Cloud Segmentation Networks</a></li>
				<li><a href="#Fifth_Point_Header">5. Point Cloud Aggregation Methods</a></li>

</ul>
</div>

<div> 
  <h1 id="First_Point_Header">1. Introduction</h1>
  </div>
  <p>
  A Point Cloud is a set of points in 3D space which can represent the boundary or the whole object (including inside points). In a point cloud, the points are unordered and are not restricted by any grid which means a point cloud can be expressed in an infinite way (using translation). Each point can have 3D coordinates and feature vectors ($P=\{(X_i,F_i)\}^{i=N}_{i=1}, X_i\in\mathbb{R}^3,F_i\in\mathbb{R}^d$).
  </p>
  
  <p> $\textbf{Properties of Point Cloud in } \mathbb{R}^3$ </p>
  <p>
  <ul>
    <li> $\textit{Unordered:}$ Unlike images or arrays, point cloud is unordered. It has no restriction to be confined within a boundary. This causes a problem for CNN type architecture to learn since CNN uses convolutional operations which requires ordered and regular array like representation of the input. Point cloud networks are generally invariant to the $N!$ number of permutations in input.</li>
   <li> $\textit{Irregularity:}$ Points are not sampled uniformly from an image which means different objects can have dense points while others sparse [1, 2]. This sometimes causes class imbalance problems in point cloud dataset.</li>
    <li> $\textit{Connectedness:}$ Since points are not connected like graph structure and neighbouring points contain meaningful spatial and geometry information of the object, networks must learn to pass information from points to points.</li>
</ul>
  </p>
  
  
  <h1>Bibliography</h1>
      <ol>
         <li>
            <p>Anh Nguyen, Bac Le, <a href="https://ieeexplore.ieee.org/document/6758588">3D Point Cloud Segmentation - A Survey</a>, 2013 6th IEEE Conference on Robotics, Automation and Mechatronics (RAM), 2013, pp. 225-230.</p>
         </li>
         <li>
            <p>Charles R. Qi, Hao Su, Kaichun Mo, Leonidas J. Guibas., <a href="https://openaccess.thecvf.com/content_cvpr_2017/papers/Qi_PointNet_Deep_Learning_CVPR_2017_paper.pdf">PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation</a>, 2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017, pp. 77-85.</p>
         </li>
          <li>
            <p>Qingyong Hu, Bo Yang, Linhai Xie, Stefano Rosa, Yulan Guo, Zhihua Wang, A. Trigoni, A. Markham., <cite>RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds</cite>,  2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR).</p>
         </li>
      </ol>