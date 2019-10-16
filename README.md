# MNIST_HandWrittenDigits_Challenge

## DESCRIPTION

The MNIST Hand-Written Digits Challenge involved getting a validation accuracy of close
to 99% in 10 epochs with parameters less than 10K.For that three cases were used that is
<5K, >5K and <10K parameters.

## MODEL ARCHITECTURE

* Idea of Inception Model was Conceptualized for getting a smaller number of
parameters.
* Three branches were added which contained 3 Convolution Layers+ 1 Max Pooling
Layer.
* The activation function used for Convolution Layers was ReLU.
* The number of filters were 2->4->6 in increasing order.
* Kernel sizes of 1 x 1 and 7 x 7 were used alternatively for Convolutions.
* Pool size of 7 x 7 was used in Max-Pooling Layer.
* The above three branches were concatenated into a fully connected layer.
* The fully connected layer was flattened out and the output of it was passed
through a Dense Layer with number of units as 10 and activation as ReLU.
* The output of the above layer was passed to another Dense Layer with number of
units as number of output classes and activation as SoftMax.
* The same architecture was used for <5K parameters,>5K parameters and <10K
parameters but with different approaches where in appropriate layers were
concatenated based on the requirement to make the model more extensible and
for ease of use.

## TRAINING AND TESTING

* The model was compiled with loss as categorical cross entropy and optimizer as
AdaDelta and metric as accuracy.
* Keras Early Stopping functionality from callbacks was used to stop training when
the validation loss had started to increase with patience set accordingly.
* The batch size used was 32 and number of epochs as 10 as mentioned in the
challenge.
