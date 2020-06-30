[![Gitpod ready-to-code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/matteo1989it/TransferLearningAlexNET)

In this tutorial, you will learn how to classify images of cats and dogs by using transfer learning from a pre-trained network,
A pre-trained model is a saved network that was previously trained on a large dataset, typically on a large-scale image-classification task. You either use the pretrained model as is or use transfer learning to customize this model to a given task.
The intuition behind transfer learning for image classification is that if a model is trained on a large and general enough dataset, this model will effectively serve as a generic model of the visual world. You can then take advantage of these learned feature maps without having to start from scratch by training a large model on a large dataset.
In this notebook, you will try two ways to customize a pretrained model:
    	1. Feature Extraction: Use the representations learned by a previous network to extract meaningful features from new samples. You simply add a new classifier, which will be trained from scratch, on top of the pretrained model so that you can repurpose the feature maps learned previously for the dataset.
You do not need to (re)train the entire model. The base convolutional network already contains features that are generically useful for classifying pictures. However, the final, classification part of the pretrained model is specific to the original classification task, and subsequently specific to the set of classes on which the model was trained.\n",
 	1. Fine-Tuning: Unfreeze a few of the top layers of a frozen model base and jointly train both the newly-added classifier layers and the last layers of the base model. This allows us to \"fine-tune\" the higher-order feature representations in the base model in order to make them more relevant for the specific task.
You will follow the general machine learning workflow.
	1. Examine and understand the data
	1. Build an input pipeline, in this case using Keras ImageDataGenerator
	1. Compose the model
		* Load in the pretrained base model (and pretrained weights)
		* Stack the classification layers on top
	1. Train the model
	1. Evaluate model
