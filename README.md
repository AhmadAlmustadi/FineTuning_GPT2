# FineTuning_GPT2

**Aragpt2-Sheikh-Islam Fine-Tuned Model**

### **Description**
**Overview:**
This model is a fine-tuned version of the aragpt2-base model, trained using excerpts from the works of Sheikh al-Islam Ibn Taymiyyah, may Allah have mercy on him. The goal of this model is to improve its ability to generate text similar to that of Sheikh al-Islam. The model is still under development and is intended to assist users in generating text that resembles the style of Sheikh al-Islam.

**Original Model:**
The original model is aragpt2-base, which can be found on Hugging Face at this link: [aragpt2-base](https://huggingface.co/aubmindlab/aragpt2-base).

**Modifications:**
The model was fine-tuned using texts sourced from the Shamela library, where the data was prepared by dividing the texts into sentences of no more than 1000 words before being input into the model. The fine-tuning process involved 5 epochs of training.

### **How to Use**
This model can be used in the same way as the aragpt2-base model. 
Here is a simple example of how to use the model:

python (
from transformers import AutoModelWithLMHead, AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained(ahmadAlrabghi/AraGPT2-IbnTaymiyyah")
model = AutoModelWithLMHead.from_pretrained(ahmadAlrabghi/AraGPT2-IbnTaymiyyah")

input_text = "قال شيخ الإسلام رحمه الله"
input_ids = tokenizer.encode(input_text, return_tensors="pt")
outputs = model.generate(input_ids, max_length=50)

print(tokenizer.decode(outputs[0], skip_special_tokens=True))
)

### **Training and Datasets**
**Training Data:**
The training data was sourced from the Shamela library, containing excerpts from the works of Sheikh al-Islam Ibn Taymiyyah. The data was processed and divided into sentences with no more than 1000 words before being input into the model.

**Training Settings:**
- Batch Size: 16
- Epochs: 5
- Learning Rate: 2e-5
- Weight Decay: 0.01

### **Evaluation**
This model has not been evaluated to minimize computational costs and processing. Therefore, there are no available metrics regarding its performance accuracy or other evaluation measures.

### **Limitations and Warnings**
- **Warning:** This model is not ready to be used for answering any jurisprudential questions related to the opinions of Sheikh al-Islam on Islamic legal matters.
- **Limitations:** The model is still under development and should not be relied upon for deriving religious conclusions.

### **Versioning and Contributors**
**Version:**
This is the first version of the fine-tuned model and it is still under development.
