# RunYeNet

A more friendly implementation of YeNet ([Deep Learning Hierarchical Representation for Image Steganalysis](https://ieeexplore.ieee.org/document/7937836/;jsessionid=7A552BE288B2A7C2BE750FFF124243A6)). 

Please note that users should only modify the parameters at the beginning of the script when conducting experiments. 

## Parameters

The meanings of parameters defined at the beginning of the script for users should be obvious except ``trainingSize``,  ``validationSize``, ``testingSize``, and ``preProcessingTuple``. Here are the explanations. 

### The three sizes

When these three parameters are set to ``None``, the script will use all the images in the specified image folders. 

When these three parameters are set to a list or a tuple with a length of 2 namely ``t``, the script will only use the part cropped from ``t\[0\]`` to ``t\[1\] - 1``. 

When these three parameters are set to an integer ``s``, the script will randomly select ``s`` unrepeated samples from the specified image folders. 

### ``preProcessingTuple``

The parameter ``preProcessingTuple`` should be a tuple with a length of 4. It is used to handle color images and images with a wrong shape that the original YeNet does not support. 

- ``preProcessingTuple\[0\]``: The method ID used for resizing.
- ``preProcessingTuple\[1\]``: The method ID used for converting color images into greyscale images.
- ``preProcessingTuple\[2\]`` and ``preProcessingTuple\[3\]``: The shape of the image after cropping to fit the original YeNet model (256 x 256). 
