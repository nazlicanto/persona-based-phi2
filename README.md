# Phi 2 Persona Based Chat Model
This repository contains the Phi 2 Persona Based Chat Model, a LoRA fine-tuned version of the base Phi 2 model. The model is  trained on [nazlicanto/persona-based-chat dataset](https://huggingface.co/datasets/nazlicanto/persona-based-chat) currently hosted on Hugging Face, which includes over 64,000 conversations designed to enhance personalized conversational text generation.

## Dataset Overview
The dataset is crafted for training conversational models that reflect detailed persona characteristics. Each dialogue in the dataset is structured to reflect a back-and-forth exchange between two personas, offering a window into how individual characteristics, backgrounds, and personal narratives can influence conversational flow and response generation. 

####  Training Data Fields
-**conv_id**:  Unique identifier for each conversation.  
-**persona_b**:  List of persona facts, describing attributes or experiences of Persona B.  
-**dialogue**:  Conversational turns starting and ending with Persona A’s responses.  
-**reference**:  Reference response reflecting Persona B's perspective based on the dialogue.  


## Model Description
We apply the LoRA method for parameter-efficient fine-tuning (PEFT), allows us to make task-specific adjustments to the Phi 2 model with minimal computational overhead. We also incorporate 4-bit quantization to optimize the model’s efficiency.  

We apply LoRA for parameter-efficient fine-tuning (PEFT) allows us to make task-specific adjustments to the Phi 2 model with minimal computational overhead. We also incorporate 4-bit quantization to optimize the model's efficiency (i.e., reduce model size for faster deployment).[Hugging Face Link](https://huggingface.co/nazlicanto/phi-2-persona-chat)


## Usage

### Clone, Setup, and Install:

- Clone the repository and navigate to the project directory.  
- Create a conda environment with Python 3.9.  
- Activate the environment and install dependencies

### Fine-tune the Model:

**Choose your dataset:**  
Use the provided nazlicanto/persona-based-chat dataset (ideal for persona-grounded chat).
Fine-tune on your own dataset with similar persona information (i.e., persona descriptions and conversation examples).



```python
# Replace placeholders with your details

python finetune_phi.py --dataset=<HF_DATASET_ID_OR_PATH> --base_model="microsoft/phi-2" --model_name=<YOUR_MODEL_NAME> --auth_token=<HF_AUTH_TOKEN> --push_to_hub
```


### Test the Model:

Run python test.py to test the fine-tuned model with a random sample from the dataset.

