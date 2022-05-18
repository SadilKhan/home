---
date: "2020-09-27T00:00:00Z"
external_link: ""
summary: Open Source Image Annotator in Python
tags:
- Image Annotation
- Computer Vision
- Object Detection
title: AutoLabelMe
sutitle: Open Source Image Annotator in Python
---
# <style>
# section {
# 	border-bottom: 1px solid rgba(0, 0, 0, 0.616);
# }
# </style>
<script src="https://mickael.canouil.fr/post/floating-toc-in-blogdown/index.en_files/header-attrs/header-attrs.js"></script>
<div id="TOC">
<section>
				<h1 id="First_Point_Header">1. Introduction</h1>
				<p style="line-height:2em">
					Data Collection is a major step in every Machine Learning
					projects. The quality and quantity of data alone can
					greatly impact the results of the model. </p>
				<p style="line-height:2em">
					AutoLabelme is an open-source automatic image annotator created using the Tkinter library in Python.
					It's an extension of LabelMe, the open-source Image Annotator available in
					<a \href="https://github.com/wkentaro/labelme}{https://github.com/wkentaro/labelme}"> Github
						LabelMe</a>. It matches the template provided by the user in an image and find same objects
					associating a bounding box and label for every object.
					Autolabelme uses Normalized Cross-Correlation to check whether two templates are
					similar. It is designed keeping in mind with the necessity of creating dataset
					for object detection purposes and currently can only find objects in the cropped
					image i.e the search space to find same object is the space around the current
					template.
				</p>
			</section>
			<section>
				<h1 id="Second_Point_Header">2. Properties</h1>
				<ol>
					<li>AutoLabelMe is simple to use. After LabelMe Manual Annotation just run AutoLabelMe.</li>
					<li> It is fast. The search space to the local neighbourhood of the template
						which makes it efficient for some projects.</li>
					<li> AutoLabelMe can identify rotated, scaled, horizontally and
						vertically flipped templates. There is no need for manually annotate
						rotated version of any template. It assigns a new label for the rotated
						templates with the rotaion information added in the label.</li>
					<li>AutoLabelMe also saves any meta information user stores during the LabelMe Manual Annotation
						step.
						For example, if for a bouding box, user assigns its label as "0 This is a Sun".
						AutoLabelMe will create a separate json file storing the new label for the
						bounding box and the meta information. This is helpful to save any additional
						information user wants for any object.</li>
				</ol>
			</section>
			<section>
				<h1 id="Third_Point_Header">3. Tutorial</h1>
				<p>
					<strong>Types of Windows</strong>
					<ol>
						<li><i>Left Pane</i>: Shows the image and matching for the current label.
							<span style="color:red" ;>Red</span> for the usual boxes. <span style="color:blue"
								;>Blue</span>
							for horizontally or vertically flipped boxes.
							<span style="color:green" ;>Green</span> for rotated. Although these
							are not final colors of the boxes. These are present only for checking.</li>
						<li>
							<i>Top-Right Pane</i>: Buttons.
						</li>
						<li>
							<i>Bottom-Right Pane</i>: Shows the image with all the matched templates.
							These image is helpful to recognise if every templates are matched or not.
							If any object is not annotated, it can be added using LabelMe.
						</li>
					</ol>
				</p>
				<p>
					<strong>Functions of Every Buttons and Boxes</strong>
					<ol>
						<li>
							<i>Next Line $>>$</i>: Template matching for next label.
						</li>
						<li>
							<i> $<<$Previous Line</i>: Template matching for previous label. </li> <li>
									$-$: Increases the threshold which results in less number of boxes.
						</li>
						<li>
							$+$: Decreses the threshold which results in detection of more boxes.
						</li>
						<li>
							<i>Save Json</i>: Saves a JSON file which can be read by LabelMe for further edits.
						</li>
						<li>
							<i>Save Images</i>: Save the cropped vignettes from the image.
						</li>
						<li>
							<i>min</i>: The minimum value of Rotation
						</li>
						<li>
							<i>max</i>: The maximum value of Rotation
						</li>
						<li>
							<i>Rematch</i>: Match again for the current label with the current setting. If min and max
							are provided, <i>Rematch</i> will match and activate rotation in template-matching.
						</li>
						<li>
							<i>Correct Label</i>:Transform all the boxes to red boxes (no flip).
						</li>
					</ol>
				</p>
				<p>
					<strong>How to Run</strong>
					<ol>
						<li> Open Terminal.</li>
						<li> Open Labelme. Write <i>labelme</i> or <i>"path/to/labelme"</i></li>.
						<li> Create one bounding box per label.</li>
						<li> Run AutoLabelme.py in Terminal <i>python3 /path/to/AutoLabelme.py.</i></li>.
						<li> Open JSON and press <i>Next Line $>>$</i> to start matching.</li>
						<li> The Left Pane will show the images with boxes for current Label. The smaller bottom-right
							pane is for showing the image with all the matched templates.</li>
						<li> Press <i> $<<$Previous Line</i> for viewing the matched boxes for the previous label. </li>
									<li>Press $+$ for more boxes and $-$ for less boxes.</li>
						<li>If you have rotated image, fill the rotation range or just enter
							<i>min</i> value. For example <i>min</i>=45 and <i>max</i>=90 will give the values
							<i>45,50,55,...90</i> or just enter <i>min</i>=45 which will only rotate the image once (45
							degree).</li>
						<li>The <i>search space value</i> is by default 2 which means the algorithm will check
							for the templates from two heights up to two heights down in the original image.
							Choose any value from 1 to 15. For example if your template starts from coordinate
							(200,200) and height and width is 100 and 100 respectively and search space=2,
							the algorithm will search for the template from (0,0) to (400,400) in the image.
							If you select more than 15 than it's just <i>heights-the value</i>. For example,
							if you choose 100 in the previous example, the it will be (0,100) to (300,300)
							where the templates will be searched in the image. In any case, value from 1 to 15 is
							sufficient.</li>
						<li>Press <i>Rematch</i> button or Press <i>Enter</i> or <i>Return</i> in your keyboard.</li>
						<li>(Optional) Sometimes if the template is symmetric, the algorithm picks up some templates as
							flipped,
							to fix this, press <i>Correct Label</i>.</li>
						<li>Press <i>Save Json</i> to save a json file.</li>
						<li> Open the saved json file in Labelme. Labelme will show the matched templates. Edit it if
							necessary.</li>
						<li>Press <i>Save Images</i> in AutoLabelme if all the boxes are okay. This will save the
							matched templates in JPEG.</li>
					</ol>
				</p>
			</section>
			<section>
				<h1>4. Future Work</h1>
				<p>In V2, AutoLabelme will be used independently to annotate manually or automatically.</p>
			</section>
</div>