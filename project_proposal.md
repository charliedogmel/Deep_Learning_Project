# Deep Learning Project - Audio Classification

# Question/need:

### What is the framing question of your analysis, or the purpose of the model/system you plan to build?

A rainforest is full of animals that may be heard before they are seen, if they are seen at all. Traditional methods of identifying animal sounds are tediously long and costly. Using audio files from the rainforest that contain sounds from numerous species, how well can a neural network be trained to classify each species that is audible in the clip?

### Who benefits from exploring this question or building this model/system?

The health of a rainforest ecosystem is a good indicator of climate change and habitat loss. Automatic acoustic monitoring will help monitor biodiversity and conservation efforts.

# Data Description:

### What dataset(s) do you plan to use, and how will you obtain the data?

The data comes from a kaggle competition sponsored by Rainforest Connection called Rainforest Connection Species Audio Detection. The data can be downloaded from kaggle.

https://www.kaggle.com/c/rfcx-species-audio-detection/data

### What is an individual sample/unit of analysis in this project? What characteristics/features do you expect to work with?

An individual unit of analysis is an audio flac file. There are about 4,700 training flac files and 2,000 test flac files in the dataset. There are also csv files with information associated to the audio files like recording ID, species ID, songtype ID, start and stop time of the species sound, min and max frequency of the sound, and whether the audio is a true or false positive detection.

### If modeling, what will you predict as your target?

Using a convolutional neural network, I will classify each species heard on each test audio file.

# Tools:

### How do you intend to meet the tools requirement of the project?

- Python neural network libraries/tools for the CNN.

- Processing tools could include Google Cloud or Amazon Web Services for cloud computing resources, or librosa for the audio.

- Visualization tools could include python libraries such as Bokeh and Plotly as well as matplotlib and seaborn.


### Are you planning in advance to need or use additional tools beyond those required?

Maybe

# MVP Goal:

### What would a minimum viable product (MVP) look like for this project?

An MVP will include a baseline model of the CNN.
