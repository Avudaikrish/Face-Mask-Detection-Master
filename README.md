
The purpose of this project is develop a real-time face mask detection software that can be used in a wide variety of places such as, corporate offices, shopping malls, theatres and other places with dense crowds. To develop this application we have used [YOLOv4](https://arxiv.org/abs/2004.10934) a real-time object detection model. We used the publicly available [face mask detection](https://www.kaggle.com/alexandralorenzo/maskdetection) dataset from Kaggle and trained it using darknet's pre-trained yolov4 weights. We trained on an initial network resolution of 608x608. Higher resolution can lead to better detection.

Each of the trained weights was converted to an .h5 model which was used for detection. 

------

### Usage

To run the detection on a single image :

``` python
python image.py --weights <path_to_the_weights> --size <size_to_scale> --image_path <path_to_image>
```

Detection on video and to save the results to a separate file :

``` python
python video.py --weights <path_to_the_weights> --video_path <path_to_the_video> --size <size_to_scale> --save_path <detected_video_save_path>
```

Detection using a webcam : 

``` python
python webcam.py --weights <path_to_the_weights> --size <size_to_scale> 
```

`size` parameter is used to scale the image to get a padded image for the detection. Since the input_layer uses a `tf.keras.layers.Input` with the `size ` as the shape of this layer, each image / video frame sent to this model for detection will be scaled accordingly.






