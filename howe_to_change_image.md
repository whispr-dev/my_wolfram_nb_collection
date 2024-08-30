**fren i'm still getting this output (that's he initialisation) but it looks grey no matter what? should i expecc that?**


**ChatGPT** _said:_

The output appears to be primarily grey because the initialized weights and biases are producing outputs that are relatively uniform across the image, which likely means that the network has not yet been trained or tuned to produce varied results that would reflect the input image's features.

When you initialize the weights randomly within a small range (like {-0.1, 0.1}), the neural network often produces very similar outputs across different regions of the input, especially before any training has occurred. This uniform output could appear as grey when you map it back to an image format.


If you're looking to see more variation in the output image, you could try initializing the weights with a larger range or using a different initialization method to see if that produces more variation. However, keep in mind that without training, the network is not expected to produce meaningful transformations of the input image—it’s essentially just performing a random transformation.

Here are a few steps you could try:


- Increase the Range of Initialization: You can experiment with a wider range for the weights, such as {-0.5, 0.5} or even {-1, 1}, to see if that produces more varied output.

```wolfram
net = NetChain[{LinearLayer[10, 
     "Input" -> 10,(*Specify input size here*)
     "Weights" -> RandomReal[{-0.5, 0.5}, {10, 10}], 
     "Biases" -> RandomReal[{-0.5, 0.5}, {10}]], LogisticSigmoid}];
```

- Training the Network: To see the network produce meaningful outputs, it would need to be trained on a set of images. The training process adjusts the weights and biases in a way that the network can recognize and process patterns in the input data.

- Use Pre-trained Models: If your goal is to transform images in a meaningful way without training from scratch, consider using a pre-trained model available in Wolfram Language that has been trained on similar tasks.

- Normalization and Preprocessing: Make sure that the input image data is properly normalized and preprocessed before feeding it into the network. This ensures that the input values are within a range that the network expects, which can influence the output.


If you're simply experimenting with how different initializations affect the output, increasing the range as mentioned might produce more visually interesting results. However, for a fully functional image processing pipeline, training or using pre-trained models is key.