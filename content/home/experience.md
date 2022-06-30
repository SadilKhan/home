---
# An instance of the Experience widget.
# Documentation: https://wowchemy.com/docs/page-builder/
widget: experience

# This file represents a page section.
headless: true

# Order that this section appears on the page.
weight: 20

title: Experience
subtitle:

# Date format for experience
#   Refer to https://wowchemy.com/docs/customization/#date-format
date_format: Jan 2006

# Experiences.
#   Add/remove as many `experience` items below as you like.
#   Required fields are `title`, `company`, and `date_start`.
#   Leave `date_end` empty if it's your current employer.
#   Begin multi-line descriptions with YAML's `|2-` multi-line prefix.
experience:
  - title: Research Intern
    company: Creatis, INSA Lyon
    company_url: 'https://www.creatis.insa-lyon.fr/site7/en'
    #company_logo: org-creatis
    location: Lyon, France
    date_start: '2022-02-07'
    date_end: ''
    description: |2-
        __Project__ : [Learning Shapes For The Effective Segmentation of 3D Medical Images.](/publication/masterThesis)
        * Developed a novel approach to perform 3d Image Segmentation using point clouds.
        * Modified RandLaNet, an attention-based point cloud segmentation network, with a Feature Extraction Layer to learn local spatial information.
        * Developed a model-independent step to use the trained RandLaNet to perform 3d Image Segmentation.
        

  - title: Research Intern
    company: Hubert Curien Laboratory
    company_url: 'https://laboratoirehubertcurien.univ-st-etienne.fr/en/index.html'
    #company_logo: org-x
    location: Saint-Etienne, France
    date_start: '2021-04-01'
    date_end: '2021-08-31'
    description: |2-
        __Project__ : [Detector-Encoder Autoencoders for unsupervised decomposition into visual parts.](/publication/dae)
          
        * Developed DEA (Detector-Encoder AutoEncoder), a novel autoencoder for anomaly segmentation. 
        * Optimized SSD Detector with GIOU loss. 
        * Designed AutoLabelMe, a GUI in Python for automatic Image Annotation. It’s suitable for researchers and practitioners to automatically annotate objects in images for object detection.


  - title: Data Science Intern
    company: Accenture Digital
    company_url: 'https://www.accenture.com/'
    #company_logo: org-a
    location: India
    date_start: '2020-05-01'
    date_end: '2020-06-30'
    description: |2-
        __Project__ : Intelligent Inventory Planning
        * Due to sudden unexpected changes such as increasing demand trend, introduction of competitive products, phasing out of a product result in forecast-demand gaps. The objective is to predict the daily or weekly hedging to cover for demand gaps based on past data of variation of forecast/Consumption.
        * Focused on Hypothesis driven approach and applied XgBoost algorithm.
        * Created a web-scrapper in Python to collect weather data. 
        * Model interpretation using What-IF tool in Google Cloud Platform. 

design:
  columns: '2'
---
