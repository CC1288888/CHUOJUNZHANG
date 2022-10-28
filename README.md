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
The demo notebook uses PyTorch library
### Limitations
- The notebooks contained several transformer models, it will take some time to download the models at the first time 

- The Summarizer uses Pipeline Function of Hugging Face, the input length is set by the base model and cannot be changed.
If the input image dataset is too large, the model will disfunction.To solve this problem, you can manipulate parameter "length" under function "get_image_caption_summary" to adjust the input size. 

Note: "Length" controls the number of sentences used to extract the paraphrased summary.


