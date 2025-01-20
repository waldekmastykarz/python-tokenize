# Python Tokenize

This repo contains a Jupyter notebook to calculate the number of tokens in text, files, and folders using tokenizers from Hugging Face and OpenAI.

## Installation

```sh
uv sync
```

## Usage

Select the model to use for tokenization in the Jupyter notebook. You can choose either a model from the Hugging Face model hub or OpenAI. Set the model's name in the `model_name` variable.

- For Hugging Face models, use the `user/model name` from the Hugging Face model hub, eg. `mixedbread-ai/mxbai-embed-large-v1`
- For OpenAI models, use the model name from the OpenAI API, eg. `gpt-4o`. [Available models](https://github.com/openai/tiktoken/blob/63527649963def8c759b0f91f2eb69a40934e468/tiktoken/model.py#L22-L72).

### Calculate tokens in a text

1. Set the `text` variable to your text.
1. Run all cells.

### Calculate tokens in a file

1. Set the `file_path` variable to the path of your file.
1. Run all cells.

### Calculate tokens in files in a folder

1. Set the `folder_path` variable to the path of your folder.
1. Optionally, specify a filter for which files to include.
1. Run all cells.
