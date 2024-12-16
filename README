
# Seq2Seq Model - Final Project

This project implements a semantic parsing system using a Sequence-to-Sequence (Seq2Seq) architecture with attention mechanisms. It is designed to translate natural language queries into their logical forms, based on the Jobs dataset described in the [paper](https://aclanthology.org/P16-1004.pdf). In this model, the researchers wanted to create an LSTM model that has an attention aspect to it. Instead of the last encoder block outputting to the first decoder block, they wanted to have a mechanism of where the all the encoder blocks contributed to each decoder block for better performance. I implemented the Seq2Seq part of the paper in this project.


## Features

- __Seq2Seq Architecture:__ Encoder-decoder structure for sequence modeling.
- __Attention Mechanism:__ Improves accuracy by focusing on relevant input features.
- __Custom Data Preprocessing:__ Handles padding, vocabulary indexing, and tokenization for queries and logical forms.
- __Hyperparameter Search:__ Allows experimentation with embedding sizes, hidden units, learning rates, and batch sizes.
- __Evaluation Metrics:__ Reports both per-token and exact-match accuracy.


## Code Walk Through

### Pre-Processing and Data Loading
Initially, the preprocessing steps and data loading mechanisms are given to us. One to keep in mind is that the data is not passed in as the sequences themselves but rather, using a word to index map, their respective indices are passed into the embeddings.

### Encoder
A encoder block that takes in the input sequences and ouputs the hidden vectors was implemented. 

### Decoder (Attention)
The decoder was similar to the encoder but it had the functionality for the attention schema. This is where I went through the matrix multiplication and formatted the dimensions properly to ensure the code followed the paper. 

### Seq2Seq Model
In my model class, I also implemented the implementation of this attention scheme where each output of every encoder block contributes to a context vector and then is combined with each decoder block in the last layer to get to an output. I had to manually loop through the "decoder block" and pass in the output of the previous decoder block / or ground truth answer (for teacher forcing) to then go through the attention schema calculations that were mentioned in the decoder. 

### Model Training and Evaluation
I trained the model using an Adam optimizier and NLL loss. And I evaluated the model based on the per-token accuracy and exact sequence match accuracy for 5 epochs and 20 epochs.

### Hyperparameter Tuning/Selection
A hyperparameter search was generated to easily sift through the parameter space where each hyperparameter had several options and took the best performingh hyperpameter selection to run for my model. This was done because my model seemed very sensitive to the hyperparameters I chose.


## Results

After 20 epochs, the model typically achieves:

- Per-token Accuracy: 85-95%
- Exact-match Accuracy: 75-85%


## References

- Original paper: [Language to Logic Mapping for Semantic Parsing](https://aclanthology.org/P16-1004.pdf)
- Dataset: Jobs Semantic Parsing Dataset
