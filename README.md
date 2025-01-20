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

```python
text = 'Your text here'
num_tokens = tokenizer_fn(text)
print(f'Number of tokens in text: {num_tokens}')
```

### Calculate tokens in a file

1. Set the `file_path` variable to the path of your file.
1. Run all cells.

```python
file_path = 'path/to/your/file.txt'
num_tokens = get_num_tokens_from_file(file_path)
print(f'{file_path}: {num_tokens}')
```

### Calculate tokens in files in a folder

1. Set the `folder_path` variable to the path of your folder.
1. Optionally, specify a filter for which files to include.
1. Run all cells.

```python
folder_path = 'path/to/your/folder'
file_filter = ['.md']  # Include only files with the .md extension
tokens_info = get_num_tokens_from_folder(folder_path, file_filter)

tokens_info_df = pd.DataFrame(tokens_info, columns=['file', 'tokens'])
tokens_info_df = tokens_info_df.sort_values(by='file')

print(f'Tokens in files in folder {folder_path} using model {model_name}:\n')
print(tokens_info_df.to_string(index=False))
```
