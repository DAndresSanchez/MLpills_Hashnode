# Convolutional Neural Networks

Convolutional Neural Networks (CNN) are a kind of deep learning algorithms that can take multidimensional data such as images as input and detect and extract patterns or characteristics within it. CNNs have been proven to be very useful in Computer Vision. 
These networks apply different kinds of layers to extract information from the image. The most relevant ones are:

* Convolutional layers
* Activation layers
* Pooling layers
* Fully-Connected layers 



### Convolutional layers
These layers apply a series of filters to the input data (generally images) to create feature maps that summarise the presence of patterns. They do so by means of convolutions. This operation is performed between the input data and a matrix of weights called filter or kernel that is smaller than the input. 
This filter is multiplied (dot product) systematically across the dimensions of the input data, by being overlapped to the input from left to right and from top to bottom.



![CNN_01.gif](https://cdn.hashnode.com/res/hashnode/image/upload/v1662109801398/2lXPyNIW4.gif align="center")
<center>*Example for input size 5x5, filter size 3x3 and strides 1.*</center>


#### Parameters
* Multiple **filters** can be applied, which will determine the depth of the output feature map. In *Keras* and *TensorFlow*, it is controlled through the ```filters``` argument.
* The **size** of the filter can be controlled through the ```kernel_size``` parameter. It refers to the size of the overlapping patch or matrix. It will affect the dimensions of the output.
* The step with which the filter is applied is called the **stride**. It downsamples the data. In *Keras* and *TensorFlow* it can be specified through the ```strides``` argument, which is by default 1. This also affects the dimensions of the output feature map.
* When a stride is added, the overlapping could finish before reaching the end of the input dimensions. In this case, some rows and columns will be ignored. To prevent this scenario, zero **padding** could be evenly added around the input. In *Keras* and *TensorFlow*, this can be controlled through the ```padding``` argument. If the desired behavior is the first one, then this argument can be unspecified or set to ```“valid”```; otherwise, it must be set to ```“same”```.



#### Output dimensions
As seen before, the output feature map will have different dimensions depending on the selected parameters for the convolutional layer. 

If we consider ten color images with dimensions 16x8 pixels, the input data would have the following shape:

```input_shape = (10, 8, 16, 3)```

The first argument indicates the number of images, the second and third arguments refer to the height and width respectively, and finally, the last one indicates the number of channels or depth (three for color images because of the three RGB channels, and one for black and white images).


For this example, we will consider that the input data go through the following convolutional layer:

```tf.keras.layers.Conv2D(filters=5, kernel_size=3, strides=(2,2), padding='valid')```

* The output feature map would have a depth of 5, determined by the number of filters.
* The dimensions of the output will be determined by the kernel size, the stride and the padding. For example, the output width dimension can be calculated as: 

```output_width = (image_width - kernel_size + strides) / strides = (16 - 3 + 2) / 2 = 7.5```

Depending on the set padding the width will differ:
* ```"valid"```: it will be rounded down, so the result will be 7.
* ```"same"```: it will be rounded up, yielding 8.

This is done also for the height:

```output_height = (image_height - kernel_size + strides) / strides = (8 - 3 + 2) / 2 = 3.5```

Therefore, for this example, in which the padding is set to "valid" (no zero padding applied), the dimensions of the output feature maps will be:

```output_shape = (10, 3, 7, 5)```


Further information on the *Keras/TensorFlow* implementation of the convolutional layers can be found [here](https://www.tensorflow.org/api_docs/python/tf/keras/layers/Conv2D).



If you liked this content don't forget to follow me here and on Twitter!
[![followme.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1662393841754/RAbmmaiHK.png align="center")](https://twitter.com/daansan_ml)