<h2>TensorFlow-FlexUNet-Image-Segmentation-Teeth (2026/09/10)</h2>
Sarah T. Arai<br>
Software Laboratory antillia.com<br><br>
This is the first experiment in image segmentation for <b>Teeth </b> based on our 
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
(TensorFlow Flexible UNet Image Segmentation Model for Multiclass), 
and a 572x572 pixels PNG 
<a href="https://drive.google.com/file/d/1jpJznQZwQ5Kljk-b0TlXvbpdha37OWVp/view?usp=sharing">
<b>Augmented-Teeth-ImageMask-Dataset.zip</b></a> (CC BY 4.0),
 which was derived by us from <br><br>
<b>segmentation_final-images an masks</b> subset of 
<a href="https://www.kaggle.com/datasets/leonardoaranguiz/segmentation-teeth-images-and-masks/data">
<b>Segmentation teeth Images and Masks</b></a> by Leonardo Aranguiz.
<br><br>

<hr>
<b>Actual Image Segmentation for Teeth Images of 572x572 pixels </b><br>
As shown below, the inferred masks predicted by our segmentation are somewhat similar to the ground truth masks.
<br><br>
<a href="#3"><b>class_color_mapping_table</b></a>
<br><br>
<table >
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: tiled_inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/10484.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/10484.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/10484.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/distorted_0.01_rsigma0.5_sigma40_10339.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/distorted_0.01_rsigma0.5_sigma40_10339.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/distorted_0.01_rsigma0.5_sigma40_10339.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/distorted_0.02_rsigma0.5_sigma40_10366.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/distorted_0.02_rsigma0.5_sigma40_10366.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/distorted_0.02_rsigma0.5_sigma40_10366.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>
<h3>1  Dataset Citation</h3>
The dataset used here was derived from <br><br>
<b>segmentation_final-images an masks</b> subset of 
<a href="https://www.kaggle.com/datasets/leonardoaranguiz/segmentation-teeth-images-and-masks/data">
<b>Segmentation teeth Images and Masks</b></a> by Leonardo Aranguiz.
<br><br>
The following explanation (excerpt) was taken from the website above.
<br><br>
<b>About Dataset</b><br>
<b>Overview</b><br>
This dataset contains dental intraoral photographs with pixel-level segmentation masks for 32 individual teeth plus background, 
standardized to 572×572 px resolution. It is intended for training and benchmarking semantic 
segmentation models, particularly encoder-decoder architectures such as U-Net and its variants.
<br><br>
All images originate from a publicly available annotated intraoral dataset (see Data Provenance below) 
and were annotated following the FDI World Dental Federation notation system. 
This release applies standardized preprocessing — resolution normalization, aspect-ratio-preserving padding, 
and super-resolution upscaling — 
to make the data ready for direct use in segmentation model training.<br><br>
<b>Preprocessing Pipeline</b><br>
Standardization steps applied to all images:<br>
Non-square images received centered black zero-padding to preserve aspect ratio.
Images smaller than 572 px in any dimension were upscaled with Real-ESRGAN x4 (Wang et al., 2021) before 
Lanczos resize, to minimize sharpness loss.<br>
Segmentation masks were resized with nearest-neighbor interpolation exclusively, preserving integer 
class IDs without interpolation artifacts.
<br><br>
<b>License</b><br>
CC BY 4.0 — You are free to share and adapt this dataset for any purpose, provided appropriate credit 
is given to Odontify and to the original dataset authors (Ahmed et al., 2025).
<br><br>
<b>Citation</b><br>
Odontify. (2026). Odontify Dental Photos Segmentation Dataset (572×572).<br>
Kaggle. <a href="https://www.kaggle.com/datasets/leonardoaranguiz/odontify-dental-segmentation">
https://www.kaggle.com/datasets/leonardoaranguiz/odontify-dental-segmentation
</a><br>
<br>
<b>Original source:</b><br>
Ahmed, S. et al. (2025). Annotated intraoral image dataset for dental caries detection.<br>
Zenodo.<a href="https://doi.org/10.5281/zenodo.14827784">https://doi.org/10.5281/zenodo.14827784
</a>
<br>
<br>
<h3>
2 Augmented Teeth ImageMask Dataset
</h3>
<h3>
2.1 Download ImageMask Dataset
</h3>
 If you would like to train this Segmentation model,
please down load our dataset <a href="https://drive.google.com/file/d/1jpJznQZwQ5Kljk-b0TlXvbpdha37OWVp/view?usp=sharing">
<b>Augmented-Teeth-ImageMask-Dataset.zip</b> </a>
(CC BY 4.0)  on Google Drive.
Expand the downloaded, and put it under <b>./dataset/</b> to be:
<pre>
./dataset
└─Teeth
    ├─test
    │   ├─images
    │   └─masks
    ├─train
    │   ├─images
    │   └─masks
    └─valid
         ├─images
         └─masks
</pre>
<br>
<b>Teeth Statistics</b><br>
<img src ="./projects/TensorFlowFlexUNet/Teeth/Teeth_Statistics.png" width="512" height="auto"><br>
<br>
As shown above, the number of images of train and valid datasets is large enough to use as the training set for our segmentation model.
<br><br>
<h3>
2.2 Derivation ImageMask Dataset
</h3>
To address the limited size of the original dataset that contains 689 images and mask files, 
we generated our own Augmented-Teeth-ImageMask-Dataset from
the original <b>segmentation_final</b> by using  the following offline augmentation tools.<br>
<a href="https://github.com/sarah-antillia/Image-Deformation-Tool">Image-Deformation-Tool</a><br>
<a href="https://github.com/sarah-antillia/Image-Distortion-Tool">Image-Distortion-Tool</a><br>
<br>
We also used the following class color mapping table to define a <b>rgb_map</b> dict in a
<a href="./projects/TensorFlowFlexUNet/Teeth/train_eval_infer.config">train_eval_inferconfig</a> 
<br><br>
<b>
<a id="3">class_color_mapping_table</a></b>
<br><br>
<table border=1 style='border-collapse:collapse;' cellpadding='5'>
<tr><th>Indexed Color</th><th>Color</th><th>RGB</th><th>Class</th></tr>
<tr><td>1</td><td with='80' height='auto'><img src='./color_class_mapping/1.png' widith='40' height='25'></td><td>(209, 35, 69)</td><td>class_1</td></tr>
<tr><td>2</td><td with='80' height='auto'><img src='./color_class_mapping/2.png' widith='40' height='25'></td><td>(53, 13, 234)</td><td>class_2</td></tr>
<tr><td>3</td><td with='80' height='auto'><img src='./color_class_mapping/3.png' widith='40' height='25'></td><td>(71, 159, 254)</td><td>class_3</td></tr>
<tr><td>4</td><td with='80' height='auto'><img src='./color_class_mapping/4.png' widith='40' height='25'></td><td>(74, 100, 159)</td><td>class_4</td></tr>
<tr><td>5</td><td with='80' height='auto'><img src='./color_class_mapping/5.png' widith='40' height='25'></td><td>(71, 129, 68)</td><td>class_5</td></tr>
<tr><td>6</td><td with='80' height='auto'><img src='./color_class_mapping/6.png' widith='40' height='25'></td><td>(87, 35, 107)</td><td>class_6</td></tr>
<tr><td>7</td><td with='80' height='auto'><img src='./color_class_mapping/7.png' widith='40' height='25'></td><td>(238, 221, 66)</td><td>class_7</td></tr>
<tr><td>8</td><td with='80' height='auto'><img src='./color_class_mapping/8.png' widith='40' height='25'></td><td>(154, 76, 36)</td><td>class_8</td></tr>
<tr><td>9</td><td with='80' height='auto'><img src='./color_class_mapping/9.png' widith='40' height='25'></td><td>(240, 103, 219)</td><td>class_9</td></tr>
<tr><td>10</td><td with='80' height='auto'><img src='./color_class_mapping/10.png' widith='40' height='25'></td><td>(99, 187, 250)</td><td>class_10</td></tr>
<tr><td>11</td><td with='80' height='auto'><img src='./color_class_mapping/11.png' widith='40' height='25'></td><td>(34, 177, 111)</td><td>class_11</td></tr>
<tr><td>12</td><td with='80' height='auto'><img src='./color_class_mapping/12.png' widith='40' height='25'></td><td>(218, 221, 236)</td><td>class_12</td></tr>
<tr><td>13</td><td with='80' height='auto'><img src='./color_class_mapping/13.png' widith='40' height='25'></td><td>(42, 199, 145)</td><td>class_13</td></tr>
<tr><td>14</td><td with='80' height='auto'><img src='./color_class_mapping/14.png' widith='40' height='25'></td><td>(222, 34, 160)</td><td>class_14</td></tr>
<tr><td>15</td><td with='80' height='auto'><img src='./color_class_mapping/15.png' widith='40' height='25'></td><td>(167, 165, 112)</td><td>class_15</td></tr>
<tr><td>16</td><td with='80' height='auto'><img src='./color_class_mapping/16.png' widith='40' height='25'></td><td>(116, 219, 27)</td><td>class_16</td></tr>
<tr><td>17</td><td with='80' height='auto'><img src='./color_class_mapping/17.png' widith='40' height='25'></td><td>(93, 147, 200)</td><td>class_17</td></tr>
<tr><td>18</td><td with='80' height='auto'><img src='./color_class_mapping/18.png' widith='40' height='25'></td><td>(250, 250, 55)</td><td>class_18</td></tr>
<tr><td>19</td><td with='80' height='auto'><img src='./color_class_mapping/19.png' widith='40' height='25'></td><td>(147, 8, 91)</td><td>class_19</td></tr>
<tr><td>20</td><td with='80' height='auto'><img src='./color_class_mapping/20.png' widith='40' height='25'></td><td>(177, 159, 189)</td><td>class_20</td></tr>
<tr><td>21</td><td with='80' height='auto'><img src='./color_class_mapping/21.png' widith='40' height='25'></td><td>(28, 180, 19)</td><td>class_21</td></tr>
<tr><td>22</td><td with='80' height='auto'><img src='./color_class_mapping/22.png' widith='40' height='25'></td><td>(168, 238, 237)</td><td>class_22</td></tr>
<tr><td>23</td><td with='80' height='auto'><img src='./color_class_mapping/23.png' widith='40' height='25'></td><td>(178, 149, 232)</td><td>class_23</td></tr>
<tr><td>24</td><td with='80' height='auto'><img src='./color_class_mapping/24.png' widith='40' height='25'></td><td>(61, 78, 106)</td><td>class_24</td></tr>
<tr><td>25</td><td with='80' height='auto'><img src='./color_class_mapping/25.png' widith='40' height='25'></td><td>(59, 30, 191)</td><td>class_25</td></tr>
<tr><td>26</td><td with='80' height='auto'><img src='./color_class_mapping/26.png' widith='40' height='25'></td><td>(175, 199, 216)</td><td>class_26</td></tr>
<tr><td>27</td><td with='80' height='auto'><img src='./color_class_mapping/27.png' widith='40' height='25'></td><td>(118, 187, 24)</td><td>class_27</td></tr>
<tr><td>28</td><td with='80' height='auto'><img src='./color_class_mapping/28.png' widith='40' height='25'></td><td>(192, 118, 42)</td><td>class_28</td></tr>
<tr><td>29</td><td with='80' height='auto'><img src='./color_class_mapping/29.png' widith='40' height='25'></td><td>(200, 2, 60)</td><td>class_29</td></tr>
<tr><td>30</td><td with='80' height='auto'><img src='./color_class_mapping/30.png' widith='40' height='25'></td><td>(63, 112, 192)</td><td>class_30</td></tr>
<tr><td>31</td><td with='80' height='auto'><img src='./color_class_mapping/31.png' widith='40' height='25'></td><td>(217, 78, 15)</td><td>class_31</td></tr>
<tr><td>32</td><td with='80' height='auto'><img src='./color_class_mapping/32.png' widith='40' height='25'></td><td>(170, 162, 70)</td><td>class_32</td></tr>
</table>
<br>
<h3>
2.3 Train Sample Images and Masks
</h3>
<b>Train_images_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/train_images_sample.png" width="1024" height="auto">
<br>
<b>Train_masks_sample</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/train_masks_sample.png" width="1024" height="auto">
<br>
<h3>
3 Train TensorFlowFlexUNet Model
</h3>
 We trained the Teeth TensorFlowFlexUNet Model by using the 
<a href="./projects/TensorFlowFlexUNet/Teeth/train_eval_infer.config"> <b>train_eval_infer.config</b></a> file. <br>
Please move to the <b>./projects/TensorFlowFlexUNet/Teeth</b> folder and run the following bat file.<br>
<pre>
>1.train.bat
</pre>
This simply runs the following command.<br>
<pre>
>python ../../../src/TensorFlowFlexUNetTrainer.py ./train_eval_infer.config
</pre>
<hr>

<b>Model parameters</b><br>
Defined a small <b>base_filters=16</b> and a large <b>base_kernels=(11,11)</b> for the first Conv Layer of Encoder Block of 
<a href="./src/TensorFlowFlexUNet.py">TensorFlowFlexUNet.py</a> 
and a large num_layers (including a bridge between Encoder and Decoder Blocks).
<pre>
[model]
image_width    = 512
image_height   = 512
image_channels = 3
input_normalize = True
normalization  = False
num_classes    = 33
base_filters   = 16
base_kernels  = (11,11)
num_layers    = 8
dropout_rate   = 0.05
dilation       = (1,1)
</pre>
<b>Learning rate</b><br>
Defined a small learning rate.  
<pre>
[model]
learning_rate  = 0.00007
</pre>
<b>Loss and metrics functions</b><br>
Specified "categorical_crossentropy" and "dice_coef_multiclass".<br>
<pre>
[model]
loss           = "categorical_crossentropy"
metrics        = ["dice_coef_multiclass"]
</pre>
<b >Learning rate reducer callback</b><br>
Enabled the learning_rate_reducer callback and a small reducer_patience.
<pre> 
[train]
learning_rate_reducer = True
reducer_factor     = 0.5
reducer_patience   = 4
</pre>
<b>Early stopping callback</b><br>
Enabled early stopping callback with the patience parameter.
<pre>
[train]
patience      = 10
</pre>
<b></b><br>
<b>RGB color map</b><br>
RGB color map dict for Teeth 8 classes.<br>
<a href="#color-class-mapping-table">Color class mapping table</a>
<pre>
[mask]
mask_datatyoe    = "categorized"
mask_file_format = ".png"
;Teeth 1+32 
rgb_map = {(0,0,0):0, (51, 153, 104):1,(30, 170, 235):2,(33, 91, 166):3,(245, 97, 107):4,(42, 126, 100):5,(240, 86, 227):6,\
  (126, 102, 225):7,(146, 106, 210):8,(229, 156, 31):9,(39, 139, 138):10,(63, 42, 122):11,(4, 174, 154):12,(248, 80, 42):13,\
  (80, 111, 190):14,(138, 42, 162):15,(255, 102, 242):16,(119, 17, 192):17,(181, 76, 230):18,(28, 227, 190):19,(126, 129, 200):20,\
  (135, 213, 222):21,(89, 3, 226):22,(18, 105, 211):23,(200, 30, 58):24,(4, 195, 134):25,(178, 222, 59):26,(58, 203, 65):27,\
  (82, 203, 201):28,(240, 189, 112):29,(48, 126, 108):30,(61, 29, 191):31,(112, 219, 207):32,}
</pre>
<b>Epoch change inference callbacks</b><br>
Enabled epoch_change_infer callback.<br>
<pre>
[train]
epoch_change_infer     = False
epoch_change_infer_dir =  "./epoch_change_infer"
epoch_change_tiled_infer     = True
epoch_change_tiled_infer_dir =  "./epoch_change_tiled_infer"
</pre>
By using this epoch_change_infer callback, on every epoch_change, the inference procedure can be called
 for 6 images in <b>mini_test</b> folder. This will help you confirm how the predicted mask changes 
 at each epoch during your training process.<br> <br> 
<b>Epoch_change_inference output at starting (1,2,3)</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/epoch_change_infer_at_start.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (18,19,20)</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/epoch_change_infer_at_middlepoint.png" width="1024" height="auto"><br>
<br>
<b>Epoch_change_inference output at ending (38,39,40)</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/epoch_change_infer_at_end.png" width="1024" height="auto"><br>

<br>
In this experiment, the training process was terminated at epoch 40.<br><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/train_console_output_at_epoch40.png" width="1024" height="auto"><br>
<br>
<a href="./projects/TensorFlowFlexUNet/Teeth/eval/train_metrics.csv">train_metrics.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/eval/train_metrics.png" width="520" height="auto"><br>

<br>
<a href="./projects/TensorFlowFlexUNet/Teeth/eval/train_losses.csv">train_losses.csv</a><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/eval/train_losses.png" width="520" height="auto"><br>
<br>
<h3>
4 Evaluation
</h3>
Please move to  <b>./projects/TensorFlowFlexUNet/Teeth</b> folder, 
and run the following bat file to evaluate the TensorFlowFlexUNet model for Teeth.<br>
<pre>
>./2.evaluate.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetEvaluator.py  ./train_eval_infer.config
</pre>
Evaluation console output:<br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/evaluate_console_output_at_epoch40.png" width="1024" height="auto">
<br><br>Image-Segmentation-Teeth

<a href="./projects/TensorFlowFlexUNet/Teeth/evaluation.csv">evaluation.csv</a><br>
The loss (categorical_crossentropy) to the tiledly split <b>Teeth/test</b> was not low, and dice_coef_multiclass 
was not high, as shown below.
<br>
<pre>
categorical_crossentropy,0.0834
dice_coef_multiclass,0.963
</pre>
<br>
<h3>5 Inference</h3>
Please move to <b>./projects/TensorFlowFlexUNet/Teeth</b> folder, and run the following bat file to infer 
segmentation regions for images using the trained TensorFlowFlexUNet model for Teeth.<br>
<pre>
>./3.infer.bat
</pre>
This simply runs the following command.
<pre>
>python ../../../src/TensorFlowFlexUNetInferencer.py ./train_eval_infer.config
</pre>
<br>
<b>infer section</b> in <a href="./projects/TensorFlowFlexUNet/Teeth/train_eval_infer.config"> <b>train_eval_infer.config</b></a><br>
<pre>
[infer] 
images_dir    = "./mini_test/images/"
output_dir    = "./mini_test_output/"
</pre>
<hr>
<b>mini_test_images</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/mini_test_images.png" width="1024" height="auto"><br>
<b>mini_test_mask(ground_truth)</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/mini_test_masks.png" width="1024" height="auto"><br>
<hr>
<b>Augmented Inferred test masks</b><br>
<img src="./projects/TensorFlowFlexUNet/Teeth/asset/mini_test_output.png" width="1024" height="auto"><br>
<br>
<hr>
<b>Enlarged images and masks for Teeth Images of 572x572 pixels</b><br>
As shown below, the inferred masks predicted by our segmentation are somewhat similar to the ground truth masks.
<br>
<br>
<a href="#3"><b>class_color_mapping_table</b></a>
<br><br>
<table>
<tr>
<th>Input: image</th>
<th>Mask (ground_truth)</th>
<th>Prediction: tiled_inferred_mask</th>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/10151.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/10151.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/10151.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/deformed_alpha_1300_sigmoid_8_10288.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/deformed_alpha_1300_sigmoid_8_10288.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/deformed_alpha_1300_sigmoid_8_10288.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/deformed_alpha_1300_sigmoid_8_10360.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/deformed_alpha_1300_sigmoid_8_10360.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/deformed_alpha_1300_sigmoid_8_10360.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/distorted_0.01_rsigma0.5_sigma40_10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/distorted_0.01_rsigma0.5_sigma40_10217.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/distorted_0.01_rsigma0.5_sigma40_10217.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/distorted_0.02_rsigma0.5_sigma40_10051.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/distorted_0.02_rsigma0.5_sigma40_10051.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/distorted_0.02_rsigma0.5_sigma40_10051.png" width="320" height="auto"></td>
</tr>
<tr>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/images/distorted_0.02_rsigma0.5_sigma40_10476.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test/masks/distorted_0.02_rsigma0.5_sigma40_10476.png" width="320" height="auto"></td>
<td><img src="./projects/TensorFlowFlexUNet/Teeth/mini_test_output/distorted_0.02_rsigma0.5_sigma40_10476.png" width="320" height="auto"></td>
</tr>
</table>
<hr>
<br>

<br>
<h3>
References
</h3>
<b>1. Teeth segmentation from dental X-ray image by template matching</b><br>
Arisa Poonsri, Napapa Aimjirakul, Theekapun Charoenpong, Chamaiporn Sukjamsri<br>
<a href="https://ieeexplore.ieee.org/document/7859599">
https://ieeexplore.ieee.org/document/7859599</a>
<br><br>
<b>2. Tooth Segmentation</b><br>
<a href="https://www.sciencedirect.com/topics/medicine-and-dentistry/tooth-segmentation">
https://www.sciencedirect.com/topics/medicine-and-dentistry/tooth-segmentation</a>
<br><br>
<b>3. TensorFlow-FlexUNet-Tiled-Image-Segmentation-Teeth-X-Ray </b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Tiled-Image-Segmentation-Teeth-X-Ray">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Tiled-Image-Segmentation-Teeth-X-Ray
</a>
<br>
<br>
<b>4. TensorFlow-FlexUNet-Image-Segmentation-Model</b><br>
Toshiyuki Arai <br>
<a href="https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model">
https://github.com/sarah-antillia/TensorFlow-FlexUNet-Image-Segmentation-Model
</a>
<br>
<br>
