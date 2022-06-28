---
date: "2022-06-28T00:00:00Z"
external_link: ""
summary: Large-Scale Point Cloud Segmentation Network
tags:
- Deep Learning
- Point Cloud
- Segmentation
- Encoder
- Decoder
title: RandLaNet
sutitle: Large-Scale Point Cloud Segmentation Network
url_code: ""
url_pdf: ""
url_slides: ""
url_video: ""

---

<script src="https://mickael.canouil.fr/post/floating-toc-in-blogdown/index.en_files/header-attrs/header-attrs.js"></script>
<script src="https://cdn.jsdelivr.net/gh/google/code-prettify@master/loader/run_prettify.js"></script>
<div id="TOC">
<ul>
<li><a href="#First_Point_Header">1. Point Cloud</a>
				</li>
				<li><a href="#Second_Point_Header">2. RandLaNet - Architecture</a></li>
				<li><a href="#Third_Point_Header">3. RandLaNet - LFA</a></li>
				<li><a href="#Fourth_Point_Header">4. RandLaNet - Decoder</a></li>
				<li><a href="#Fifth_Point_Header">5. Results</a></li>
</ul>
</div>
<div> 

  <section>
  <h1 id="First_Point_Header">1. Point Cloud</h1>
  <p>
  $\textbf{A. Introduction}$
  </p>
  <p>
  A Point Cloud is a set of points in 3D space which can represent the boundary or the whole object (including inside points). In a point cloud, the points are unordered and are not restricted by any grid which means a point cloud can be expressed in an infinite way (using translation). Each point can have 3D coordinates and feature vectors ($P=\{(X_i,F_i)\}^{i=N}_{i=1}, X_i\in\mathbb{R}^3,F_i\in\mathbb{R}^d$).
  </p>
  <p>
  $\textbf{B. Properties of Point Cloud in}$ $\mathbb{R}^3$
  </p>
  <p>
 <ul>
    <li> $\textit{Unordered:}$ Unlike images or arrays, point cloud is unordered. It has no restriction to be confined within a boundary. This causes a problem for CNN type architecture to learn since CNN uses convolutional operations which requires ordered and regular array like representation of the input. Point cloud networks are generally invariant to the $N!$ number of permutations in input.</li>
   <li> $\textit{Irregularity:}$ Points are not sampled uniformly from an image which means different organs can have dense points while others sparse [1, 2]. This causes class imbalance problems in point cloud dataset.</li>
    <li> $\textit{Connectedness:}$ Since points are not connected like graph structure and neighbouring points contain meaningful spatial and geometry information of the organ, networks must learn to pass information from points to points.</li>
</ul>
  </p>
  
  <h1 id="Second_Point_Header">2. RandLaNet - Architecture</h1>
  <p>
  Large-scale point cloud segmentation is a challenging task because of huge computational requirements and effective embedding learning. RandLa-Net[3] is an efficient and lightweight neural architecture that segments every point in large-scale point clouds. It is an encoder-decoder-like architecture that uses random sampling to downsample the input point cloud in the encoder and upsample the point cloud in decoder blocks. It uses random sampling compared to other sampling methods because of faster computation. Although random sampling can discard key points necessary for efficient point cloud segmentation, RandLa-Net implements attention-based local feature aggregation to effectively share features of points that are removed into the neighbor points. Figure[1] is the architecture of RandLa-Net. The main properties of RandLa-Net are <ul>
  <li>It is lightweight and achieves state-of-the-art results compared to existing methods. The random sampling method reduces the computation.</li>
  <li> The proposed attention-based Local Feature Aggregation (LFA) can expand into larger receptive fields using Local Spatial Encoding (LSE) with attentive pooling of point and neighbor features.</li> 
  <li> The network consists of Shared MLP without any need of graph reconstruction or voxelization. </li>
  <li> The encoder-decoder architecture with downsampling aims to generate discriminative latent vectors using small samples which represent the objects of interest. </li>
  </ul>
  <figure>
					<center><img src="randlanet_architecture.png" width="800" /> </center>
					<figcaption class="figure-caption text-center">Figure 1:  RandLa-Net Architecture.  FC is the fully connected layer, LFA is the localfeature aggregation, RS is random sampling, MLP is shared multilayer perceptron,US is upsampling and DP is dropout.  (Image from [3])
					</figcaption>
				</figure>
  </p>
  <p>
  $\textbf{A. Random Sampling}$
  <p>
  <p>
   Compared to other sampling methods, Random sampling is extremely fast (time complexity $O(N)$). It is invariant to any changes to the points as well as the permutation of points. The random-sampling block is added in encoder part. To compensate for the loss of information, the author has added LFA module
  </p>
  
  
  
  </section>
  
  <section>
<h1>Bibliography</h1>
      <ol>
         <li>
            <p>Anh Nguyen, Bac Le, <cite>3D Point Cloud Segmentation - A Survey</cite>, 2013 6th IEEE Conference on Robotics, Automation and Mechatronics (RAM), 2013, pp. 225-230.</p>
         </li>
         <li>
            <p>Charles R. Qi, Hao Su, Kaichun Mo, Leonidas J. Guibas., <cite>PointNet: Deep Learning on Point Sets for 3D Classification and Segmentation</cite>, 2017 IEEE Conference on Computer Vision and Pattern Recognition (CVPR), 2017, pp. 77-85.</p>
         </li>
          <li>
            <p>Qingyong Hu, Bo Yang, Linhai Xie, Stefano Rosa, Yulan Guo, Zhihua Wang, A. Trigoni, A. Markham., <cite>RandLA-Net: Efficient Semantic Segmentation of Large-Scale Point Clouds</cite>,  2020 IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR).</p>
         </li>
      </ol>
  </section>

</div>