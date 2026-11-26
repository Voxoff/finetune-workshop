# Fine-tuning from the ground up

A workshop notebook for the Kaggle competition [Name That LLM](https://www.kaggle.com/competitions/name-that-llm). Each passage is an answer to a prompt, written by one of 18 LLMs, and the task is to name the LLM. The notebook fine-tunes ModernBERT to do it, one idea at a time:

1. what fine-tuning is
2. train once, then test on prompts the model never saw
3. why one test isn't enough: cross-validation
4. learning rate × epochs
5. memorising vs generalising
6. more data

Section 2 trains live on a GPU (about a minute). Sections 3–6 load runs that were trained beforehand, saved in `oof/`.

## Run it

You need:
- a machine with an NVIDIA GPU and Python 3.12 or later;
- a Kaggle account that has joined the competition, with an API key in `~/.kaggle/kaggle.json`.

```bash
pip install -r requirements.txt
kaggle competitions download name-that-llm -p data
python -m zipfile -e data/name-that-llm.zip data
jupyter lab finetune_workshop.ipynb
```

The competition data isn't in this repo: the commands above download it into `data/`.
