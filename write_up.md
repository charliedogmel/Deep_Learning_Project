# Developing an Automated Eco-Acoustic Monitoring System 
## Detecting Bird and Frog Species in Tropical Soundscape Recordings 

Melissa Cooper

## Abstract

High-accuracy species detection with limited training data using CNNs is a challenging but highly useful application. First, the detection of rare species is central to conservation efforts and there are few audio samples available. In a rainforest or other dense ecosystem, it is easier to hear these species than to see them. The level of presence and diversity of various species is a good indication of the impact of climate change and habitat loss. Also, CNNs will enable real-time information processing in order to detect human impacts on the environment much earlier. Finally, machine learning provides time- and cost-efficiency compared to traditional audio sampling/detection methods.

## Design

The Deep Learning pipeline for this project involved many steps. First, the one minute long audio wave files were divided into shorter ten second segments, focused on the target sound. Those shorter wave files were passed  through FFT, Mel scaling, and a high pass filter to create Mel spectrogram images. The images were fed into the Convolutional neural network to predict which one or more species can be heard in the sample.

## Data

On kaggle, the Rainforest Connection had posted a dataset of rainforest soundscapes for a competition to accurately detect 24 species from those sounds. The dataset itself was very clean, with train and test folders containing one minute audio soundscapes and csv's containing metadata for the files. The metadata included recording id, species id heard, the min/max time the species is heard, and the min/max frequency of the audio. The training and validation datasets came from these Mel spectrograms.

One challenge to this data was the unknown test audio files. These files also needed to be split into ten second segments and converted to images. The difficulty lay in combining the predictions for the six segments into one multi-label prediction for the entire minute long audio. 

## Algorithms

*Preprocessing*

Preprocessing used librosa to create Mel spectrograms and ImageData Generator for image augmentation and creating batches.

*NN Modeling*
  
For this data, a baseline regression model was not possible in the scope of the project. A simple baseline neural network architecture with several layers yielded very poor results. I ran several models from related kaggle notebooks with success, but the notebooks were relatively complex and I wanted to understand the models more fully. Ultimately, after finding a project on birdsong classification using a CNN by WiMLDS in Poland, I adapted their simpler method and suggested architecture of EfficientNetB3.

Overfitting was a big problem and it was interesting that most of the tools to address this did not work. (Or other parameters needed to be adjusted at the same time. With more time, this would be a perfect application of GridSearchCV.) Weight regularization with L2 did not work, more Conv2D layers and filters did not work, and even Dropout level was fussy. In the end, I achieved decent results with no overfitting adding only Conv2D, Flatten, Dropout, and a Dense output layer using sigmoid activation, adam optimizer, binary_crossentropy loss, and EfficientNet pre-weighted with imagenet.

## Tools

- Numpy and Pandas for data manipulation
- Librosa and Audio and ipywidgets for audio manipulation
- ImageDataGenerator and Scikit-learn for image manipulation
- Tensorflow, Keras, and EfficientNet for modeling
- VisualKeras, Matplotlib, and Seaborn for plotting

## Communication

Presentation, slides, and write-up
