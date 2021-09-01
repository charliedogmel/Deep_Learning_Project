# Rainforest Species Audio Detection MVP

#### Melissa Cooper

Using one minute audio samples of rainforest sounds, the baseline convolutional neural network attempts to place each sample into twenty-four categories of birds. The following shows the best accuracy out of thirty epochs:

31/31 [==============================] - 23s 758ms/step
- loss: 38.2513
- accuracy: 0.0833
- val_loss: 3.1582
- val_accuracy: 0.0820

This may be the worst baseline possible, which means only improvements are expected from this point. 

There are many methods to use for improvement. One is to use transfer learning which should be straightforward to implement, though there are several to choose from. Another is far more complicated. The dataset includes timing labels of where in the audio track the species call is heard. In general, this is a short segment of time around ten seconds long. Breaking the audio training samples into ten second segments would help the neural network focus on that sound image. More improvements will be adding many hyperparameters.
