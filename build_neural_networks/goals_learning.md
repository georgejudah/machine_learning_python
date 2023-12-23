# Build our own model

We're going to build our own image classification model which is going to classify 10 different things
dogs, ships, horses, frogs, deer, cats, trucks, car, planes

> Neural network will learn the features from the data by itself

## How does neural network learn to generate it's own features

1. With the cat example, the value of the activation function determine the output of a
   neuron, whether they are strong or not.

2. 2 layers - Input layer -> interconnected to Hidden Layer and finally the Output Layer
   The deeper the network, the more layer it has -> this is where it is called Deep Learning

3. In our example, in our input layer, it will combine each of the input features every which way,
   and it will try to learn the best way to combine these features.
   Each pixel in the image will be an input
   so if we have 30\*30 pixel, we will have 900 inputs with each matrix

4. Next, this is passed on to the hidden layer. Features are generated.
   The second hidden layer will work with the features which the first hidden layer generated.
   This will combine and start detecting something like edges, etc which is complex and passed on
   to the third layer.

5. Third hidden layer, will find the eyes, nose and more complex features.
   Output layer will take a weighted average of the layers.

_When the predictions are wrong, backpropagation is down, the error is passed down through the network from the output so that each node adjusts it's weights. Are they adjusted down or up? Slope or gradient determines this. The point I'm trying to make here is that through triai and error and lots of yelling from the higher ups, we don't know exactly what the features will be generated, we don't know exactly what's going on. This makes it like a black box. This model cannot be called a tractable model._

### Summary

**Each neuron in a neural network will be activated based on a mathematical formula called the activation function.The activation function determines how strong this neuron will fire, and then through trial and error, The neural network is able to generate its own features from the input data. This allows the neural network to solve both linear problems and nonlinear problems because it tries all these combinations. The deeper the network, the more complex and the more high level the features are that are generated at each layer. One piece of good news is that the pattern of learning for a neural network is very similar to our other machine learning algorithms. It makes a prediction. It figures out how far off the prediction was by looking at the loss. And then it adjusts its parameters. It adjusts its weights between the neurons in this case. And the process by which the error gets sent back down through the network so that each node can adjust its weights is called back propagation. So in summary, neural networks are very powerful. And a reasonable question is, well, if they're so powerful, can we use neural networks for everything? And the answer is yes, you can. You can solve almost every machine learning problem with a neural network. But would you want to use a neural network to solve every problem? In this case, the answer is no.**

## Disadvantages of a Neural network

We've already talked about their black box nature.
We don't really know why it is that a neural network might give a particular output.
And this is actually very important when we care about the rationale for a particular decision that is made by neural network. So imagine that a neural network is being used in the legal system and this computer programs job is to set the amount of bail or the amount of jail time for a particular person. Now, surely in this situation you'd want to be able to ask, Wait, well, why is this guy getting two years and this other guy getting ten years?This is just one example of a situation where an intransparent and intractable model is a real disadvantage. But in this lesson, I'm going to spend time talking about the other really big disadvantage of big, complex neural networks.
That second really big disadvantage is cost. And this is a really weird one to wrap your head around at first, because what kind of costs are we talking about here?
This cost actually comes in two forms.
_The first is the amount of data required, and the second kind of cost is the amount of compute required to train a neural network. And when I say compute, what I'm talking about is the amount of hours a model has to be trained on something like a GPU._
So what you're going to see is that these two costs are related in a minute and they all kind of go
back to the structure of a neural network. Now, with any kind of model, a pretty good proxy for the degree of complexity in the model are the number of parameters.

> The data requirements, training, time and the amount of computation it takes is why many people try to solve simple problems with simple methods. And even though neural networks can pretty much do anything, it's not always the best approach. When you factor in the amount of data required, the amount of compute required and the lack of transparency at the end. As a machine learning professional, what you really want to do is use the right tool for the job.

## Model we're using - Inception-ResNet and VGG19 are image classifiers

> every single model which we will be using expects data to be foramtted in a particular way, pre-processed

Take away - image classifiers, even with pre-trained weights are not going to be 100% accurate. What's the
state of the art classifiers. NASNET model - google, got about 82.5% accuracy after training a million pictures
and 60,000 hours. This is kind of the lay of the land.
