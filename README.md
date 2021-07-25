# language-detection
A neural network to detect the language of short sentences ( less than or equal to 50 characters). 
In this repository I have implemented three kinds of algorithms and compared them for __language identification__ using [tatoeba](https://tatoeba.org/) dataset.

## Included Languages

- English
- French
- Italian
- German
- Spanish

## Dataset

The tatoeba multi language dataset containing sentences from around 405 languages. Out of them, the sentences from the above languages are filtered out and are splitted to phrases with less than or equal to 50 characters. 50000 such phrases were randomly selected for each language and from all the sentences 25000 were used for testing and another 25000 for validation. After that, the performance was measured on the complete dataset of the above languages. 


## Models

- simple count based model based on [this blog](https://towardsdatascience.com/deep-neural-network-language-identification-ae1c158f6a7d). However, the blog did not discuss about using generators to do it in a memory efficient way. In this repository, I have implemented it. - 98.3 % accuracy
![Count based model](https://github.com/imdaredevil/language-detection/blob/master/outputs/count-based-model-shortened-sentences.png)
- Pre-trained [fasttext](https://fasttext.cc/) model - a continuous bag of words model with position-weights, in dimension 300, with character n-grams of length 5, a window of size 5 and 10 negatives. - 98.6% accuracy
![Fasttext model](https://github.com/imdaredevil/language-detection/blob/master/outputs/fasttext-model.png)
- Apple's Bi-LSTM model as proposed in this [research paper](https://aclanthology.org/2021.eacl-srw.6.pdf) - 99.35 % accuracy.

![Apple's Bi-LSTM](https://github.com/imdaredevil/language-detection/blob/master/outputs/apple-bi-lstm.png)

