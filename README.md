# Neural-Machine-Translation-using-Tranformers (English - German)

Reference Paper: [Neural Machine Translation Using Transformers](https://arxiv.org/pdf/1706.03762.pdf)

### Problem Definition:
The problem we are trying to implement over the course of this project is based on the Neural Machine Translation.One of the earliest goals for computers was the automatic translation of text from one language to another. Machine translation is the process of automatically translating content from one language (the source) to another (the target) without any human interference. Machine Translation has been a revelation right from the beginning, but it has become more powerful.With the advancement of different architectures such as Transformers we are able to translate a sentence from one language to another language by retaining the context and meaning of the sentence more efficiently. Real Time Machine Translation applications we use on a day to day basis offer Text to Text , Text to Speech , Speech to Text , Speech to Speech , Image of words to Text translations.Some of its applications would be Google Translate, Facebook Translate. Machine translation is impacting the world by providing the users a tool to communicate,express their ideas and share with those around them with any person around the world without any hassle and also the users with disabilities by impacting the way they communicate rely on this assistive technology to express their ideas with their emotion.

### Project Objectives: 
The main objective of this project is to build a Neural Machine Translation application, so that the machine can translate the English text to German text without any human interference.

* Preprocess the text and create tokens and build vocabulary and create word embeddings.
* Design and implement the Transformer architecture model for the NMT task according to this paper. For this project, I have used this repo as a reference. 
* Finally, built web-app using StreamLit for this Neural Machine Translation System.


### Setting up project environment:
* Create new enviroment using annaconda or miniconda
```
Setup

Environment
Using Miniconda/Anaconda:
1. `cd path_to_repo`
2. `conda env create`
3. `conda activate attention-is-all-you-need-paper`
```

## Pretrained Models
To download the pretrained model and tokenizer run:
```
python scripts/download_pretrained.py
```
* Install dependencies using environment.yml


# Data 

Same WMT 2014 data is used for the English-to-German translation task. Dataset contains about 4,500,000 sentence pairs but you can manually specify the dataset size if you want to lower it and see some results faster. **When training is initiated the dataset is automatically downloaded, preprocessed, tokenized and dataloaders are created.** Also, a custom batch sampler is used for dynamic batching and padding of sentences of similar lengths which speeds up training. HuggingFace 🤗 datasets and tokenizers are used to achieve this very fast.


# Architecture 
The original transformer architecture presented in this paper consists of an encoder and decoder part purposely included to match the seq2seq problem type of machine translation. There are also encoder-only (e.g. BERT) and decoder-only (e.g. GPT) transformer architectures, those won't be covered here. One of the main features of transformers , in general, is parallelized sequence processing which RNN's lack. Main ingredient here is the [attention mechanism](https://arxiv.org/abs/1409.0473) which enables creating modified word representations (attention representations) that take into account the word's meaning in relation to other words in a sequence (e.g. the word "bank" can represent a financial institution or land along the edge of a river as in "river bank"). Depending on how we think about a word we may choose to represent it differently. This transcends the limits of traditional word embeddings.


**For a detailed walkthrough of the architecture check the `notebooks/tutorial.ipynb`**

## Inference
For inference I created a simple app with [Streamlit](https://streamlit.io/) which runs in your browser. Make sure to train or download the pretrained models beforehand. The app looks at the `model` directory for model and tokenizer checkpoints.
```
$ streamlit run app/inference_app.py
```
### Results:
* Generated Machine Translations :-
Text 1:- I have a dream  and its german translation (https://ibb.co/FhbYn81)

 Text 2:- I am a good boy and its german translation (https://ibb.co/7JdXkp2)

