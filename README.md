# Image Caption Summarizer 
        
	Models ustilize Transformers from Hugging Face
	Deliverable of UTS 32933 Research Project Autumn 2022
	Supervisor: Dr. Wei Liu
	Author: CHUOJUN ZHANG

## What is it
       This prototype can generate abstractive summary for an image set.
       The summary can compose one or several sentences according to model applied.
       It is designed for two scenarios while people posting images online:
       1. People post a story on social media with similar type of image e.g., image of the same scene
          but don't know what to write
       2. People browse other social media accounts which contains various images, but want a quick understanding
          of what inside their albums. 
	It works like this（￣︶￣）↓↓
![2](https://user-images.githubusercontent.com/104782412/198533437-02741833-a6e7-4fa2-bc57-e15243b0b3d8.jpg)
## Prerequisites
The model is coded using Hugging Face transformer and python.
You can set up your environment following the instructions from this link:
https://huggingface.co/docs/transformers/installation. 

What you can find from the link:
1. Steps to instal virtual enviroment 
2. Paths to instal transformer using different library: Tensorflow, Pytorch, Flax
3. Steps to set up with Conda
4. Steps to use models offline

The demo notebook uses PyTorch library and run on Colab
### Limitations
- The notebook contains several transformer models, it will take some time to download the models at the first time 
- The Summarizer uses Pipeline Function of Hugging Face, the input length is set by the base model and cannot be changed.
If the input image dataset is too large, the model will disfunction.To solve this problem, you can manipulate parameter "length" under function "get_image_caption_summary" to adjust the input size. 

# How to use
- No interface was set up for the model. You can simply test it on Colab or Jupyter with your own dataset.
- Note: if you use it on Jupyter, please refer to "Install with conda" from the above link to set up the transformer
## About the Model
- The model uses CLIP + GPT2 for image captioning and Bart for the text summarization. 
- The CLIP and GPT2 is weighted on COCO dataset or Conceptual dataset. You can choose the weight by inputting "COCO" or "CO" into "ICM", 
  a parameter under function "get_image_caption_summary" to change the model weighting. 
- The default model of text summarization is set as "facebook/bart-large-xsum". You can change it to "facebook/bart-large-cnn" or other text    summarization models under this link: https://huggingface.co/models?pipeline_tag=summarization&sort=downloads
- Experiement results showed that "facebook/bart-large-xsum" and "facebook/bart-large-cnn" can get the summary that meet the scenarios' needs
- [get_image_caption_summary (path,ICM,TSM,length)] is the function that convert image set into summary.
   - path: directory of your image dataset
   
   - ICM: image caption model weight: "COCO","CO"
   
   - TSM: Text summarization model:"facebook/bart-large-xsum" or "facebook/bart-large-cnn"
   
   - length:the paramenter that controls the number of sentences used to extract the paraphrased summary.
Note: Point 2--"COCO"-Coco dataset; "CO"-Conceptual dataset.

## Experiment Results

## Demo
### Testing Dataset
It contains 30 images of raining day, sample select from Dataset:Rain 
![3](https://user-images.githubusercontent.com/104782412/198552028-754be5d4-c224-4d81-a47e-623572fd5180.jpg)
### Implementation


