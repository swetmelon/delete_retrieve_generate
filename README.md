# Description

This is an implementation of the DeleteOnly and DeleteAndRetrieve models from [Delete, Retrieve, Generate:
A Simple Approach to Sentiment and Style Transfer](https://arxiv.org/pdf/1804.06437.pdf)

# Usage

### Training

`python train.py --config sample_config.json --bleu`

This will train a model using the parameters in `sample_config.json`. Checkpoints, logs, decodings, and TensorBoard summaries will go into config's `working_dir`. The model will perform inference after each epoch. 

See `sample_config.json` for all of the training options. The most important parameter is `model_type`, which can be `delete`, `delete_retrieve`, and `seq2seq` (which is a standard translation-style model).

### Vocab generation

Given two corpus files, use the scripts in `tools/` to generate a vocabulary and attribute vocabulary:

```
python tools/make_vocab.py [entire corpus file (src + tgt cat'd)] [vocab size] > vocab.txt
python tools/make_attribute_vocab.py vocab.txt [corpus src file] [corpus tgt file] [salience ratio] > attribute_vocab.txt
```

# Questions, feedback, bugs

rpryzant@stanford.edu

