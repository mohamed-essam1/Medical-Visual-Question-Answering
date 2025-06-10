# Medical-Visual-Question-Answering
A combination of medical artificial intelligence and popular VQA challenges. Given a medical image and a clinically relevant question in natural language, the medical VQA system is expected to predict a convincing answer.

## Dataset
PMC-VQA is a large-scale medical visual question-answering dataset, which contains 227k VQA pairs of 149k images that cover various modalities or diseases.

## Architecture

In this project, we introduced a new visual multimodal Architecture that is described below 
### Visual Encoder 
That aims to map images into vectors most of the recent models depend on `inception v3` as the image encoder.
In this model, we used a vision transformer called **Facebook DinoV2 base** as the image encoder

### projection layer
that aims to map image vectors into a closer space to model embedding space by applying a linear transformation 

### Text generator
Most of the VQA models depend on **BERT** to process the text part of the inputs which is Encoder-Only. 
We used **GPT2-xl** which is a decoder only to generate the answers because most of `PMC-VQA` dataset answers are sentences.

### LoRA
We used the **LoRA** technique to reduce the number of trainable params 

## Training results

|Epoch| Training loss| Validation Loss|
|:---|:----|:----|
|1| 1.713700| 1.522783|
|2| 1.579200| 1.476643|
|3| 1.531500| 1.453559|
|4| 1.497700| 1.437069|
|5| 1.455100| 1.426782|
|6| 1.407700| 1.423500|
|7| 1.372000| 1.422881|

## Evaluation

|Accuracy| BLEU|
|:---|:----|
|0.73 |0.488|
## Model Checkpoints

[Model Checkpoints](https://huggingface.co/ahmedabdelrashied/MedVQA)

