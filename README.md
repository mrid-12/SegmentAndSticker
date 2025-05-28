# ZeroShot Segment-And-Sticker
This repository involves research regarding a proposed combination of an OwlViT model and a MetaSAM model to take an image and natural language (text) input, and segment out the requested aspect. This research has been detailed in a first-draft CVPR format research paper contributed to by Jai Bobal, Mridul Purkayastha and Vedant Gawande for UMD's Computer Vision (CMSC426) final project. We utilize HuggingFace transformers to access the OwlVit model and github to access the MetaSAM model. This README is a summary of our research paper and code.

## The hyperparameter of focus
This project is primarily one of research, and not a fully developed application. Our test set is a few (~20) varying images of people or objects that may be singular or many in number, and can be placed on simple or complex/natural backgrounds. Our research focus involves tweaking the threshold hyperparameter of the OwlViT model to research an ideal confidence threshold for the model to output an appropriate part of the image while also being mindful of cases where the prompt is meaningless/noisy. Our limited tests do succumb to the latter issue, but provide an innovative solution to extract specific parts of images with lesser effort nonetheless. 

## What does the project code contribute?
Albeit this project being a fairly low-code proposition, we drew inspiration from creating whatsapp stickers- something that we often do with friends in funny images/poses. We soon expanded the initial idea of being able to create stickers to a plethora of new ones, such as
  - segmenting any part of an image, not just the principal object of focus
      - an example from our project was a disability sign on a parking spot despite the object of focus being a vehicle parked there
  - not requiring a touch input involves extending the capabilities of accessible and efficient technology
      - what if I prioritize recall while highlighting any kind of disability sign on smart glasses without having to train the model on tons of data?
      - what if someone is presenting a slideshow of images and wants to higlight something in an image just by a microphone and natural language?
  - what if I want to photoshop a particular object and place it on a different background, all without training the model and only using a simple prompt?

## Concluded Limitations
Our proposed project's main flaw was the inability to detect multiple principal objects, or if two different parts of the image were mentioned by prompt, the segmentation must include the pixels between them. We also did notice that the low threshold caused some noisy/nonsensical predictions _(it thought a doorstopper was a TV?)_.

## What we'd like to see for the future
The microphone input and summarizing that input to pass to the OwlVit model can make a good end to end result. Another is to use the new segmented image and use an img2img diffusion model with a low strength parameter to make a fake location (not only with a person, but with anything in the image)- a fast alternative to crop and paste, yet a far lower quality than photoshop.
