
# FineTuning_GPT2

Aragpt2-Sheikh-Islam Fine-Tuned Models

### Description
Overview:
This project includes fine-tuned versions of the aragpt2-base and aragpt2-mega models, trained on excerpts from the works of Sheikh al-Islam Ibn Taymiyyah (may Allah have mercy on him). The aim is to enhance the models’ ability to generate text that reflects the style of Sheikh al-Islam. Both models are under active development.

Models:
- Base Model: aragpt2-base, which can be found on Hugging Face [here](https://huggingface.co/aubmindlab/aragpt2-base).
- Mega Model: aragpt2-mega, also available under the same model ID on Hugging Face. This model has been trained on approximately 50,000 rows of data for three epochs.

Modifications:
Both models were fine-tuned using texts from the Shamela library. Data was prepared by dividing texts into sentences of no more than 1000 words. The fine-tuning process for each model involved different training parameters.

### How to Use
You can use both models similarly to the aragpt2-base model. Here’s an example using the aragpt2-mega model:

from transformers import AutoModelWithLMHead, AutoTokenizer

tokenizer = AutoTokenizer.from_pretrained("ahmadAlrabghi/AraGPT2-IbnTaymiyyah")
model = AutoModelWithLMHead.from_pretrained("ahmadAlrabghi/AraGPT2-IbnTaymiyyah")

input_text = "قال شيخ الإسلام رحمه الله"
input_ids = tokenizer.encode(input_text, return_tensors="pt")
outputs = model.generate(input_ids, max_length=50)

print(tokenizer.decode(outputs[0], skip_special_tokens=True))
### Training and Datasets
Training Data:
The training data was sourced from the Shamela library, containing excerpts from the works of Sheikh al-Islam Ibn Taymiyyah. The data is continuously updated, and the exact dataset used may change as development progresses.

- A version of the training dataset has been uploaded to Hugging Face and is available on my account's dataset repository. You can access it [here](https://huggingface.co/datasets/your-dataset-id).

Training Settings:
- Base Model:
  - Batch Size: 16
  - Epochs: 5
  - Learning Rate: 2e-5
  - Weight Decay: 0.01

- Mega Model:
  - Batch Size: 16
  - Epochs: 3
  - Learning Rate: 2e-5
  - Weight Decay: 0.01

### Evaluation
The models have not undergone formal evaluation due to ongoing development. Performance metrics and accuracy measures are not yet available. Updates on development progress will be provided as they occur.

### Limitations and Warnings
- Warning: These models are not suitable for answering jurisprudential questions related to the opinions of Sheikh al-Islam on Islamic legal matters.
- Limitations: The models are still under development and should not be relied upon for deriving religious conclusions.

### Versioning and Contributors
Version:
This is the initial version of the fine-tuned models. Both models are still under active development. Regular updates and changes to parameters, names, and datasets are expected.

Contributors:
This project is currently maintained and developed by a single contributor. The ongoing development involves continuous updates to both the models and the datasets.

Note:
Due to GitHub’s file size limitations, not all data used in this project has been uploaded. For the complete dataset, you can access a version of it on my Hugging Face account [here](https://huggingface.co/datasets/your-dataset-id).
