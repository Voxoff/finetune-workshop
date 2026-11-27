# Fine-tuning from the ground up

A workshop notebook for the Kaggle competition [Name That LLM](https://www.kaggle.com/competitions/name-that-llm). Each passage is an answer to a prompt, written by one of 18 LLMs, and the task is to name the LLM. 

## Run from the repository

Clone the workshop on an NVIDIA GPU machine [Founders and Coders GPU machines](https://learn.foundersandcoders.com/machines/)

```bash
git clone https://github.com/Voxoff/finetune-workshop.git
cd finetune-workshop
python -m pip install -r requirements.txt
jupyter lab finetune_workshop.ipynb
```

## Use Kaggle as the data source (optional)

To refresh the files from Kaggle, join the competition and configure your Kaggle CLI credentials. Run these commands from the root of the cloned repo.

```bash
kaggle competitions download name-that-llm -p data
python -m zipfile -e data/name-that-llm.zip data
```

If you run the notebook on Kaggle, enable a GPU and add **Name That LLM** as a competition input. Set `DATA` to the mounted competition directory and `RESULTS` to the repo’s `oof/` directory.

## Optional CPU 

On a laptop, use the [CPU notebook](finetune_workshop_cpu.ipynb) to explore the data and plot saved training results.

```bash
python -m pip install jupyterlab numpy pandas pyarrow scikit-learn matplotlib tokenizers huggingface_hub
jupyter lab finetune_workshop_cpu.ipynb
```
