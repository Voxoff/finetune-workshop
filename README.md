# Fine-tuning from the ground up

A workshop notebook for the Kaggle competition [Name That LLM](https://www.kaggle.com/competitions/name-that-llm). Each passage is an answer to a prompt, written by one of 18 LLMs, and the task is to name the LLM. The notebook fine-tunes ModernBERT to do it, one idea at a time:

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
