# Arabic Sentiment Analysis and Text Classification (Using CNN)
Sentiment Analysis is to build machine learning models that can determine the tone (positive, negative, neutral) of the texts (e.g., movie reviews, tweets...). It is one of the most important and standard tasks in NLP. However, Arabic sentiment analysis has not been studied at a level as high as other languages (e.g., English, Chinese, French...). One of the key factors is the lack of high-quality and large-scale training data.

- ### Word Embedidng:
  - **[fastText](https://fasttext.cc/)** 
    - Arabic word vectors.
    - Dimension 150.
    
- ### Datasets:
  - **[ArSAS](https://homepages.inf.ed.ac.uk/wmagdy/resources.htm)**
    - Arabic Speech-Act and Sentiment Corpus of Tweets Dataset.
    - 21K Tweets.
    - 4 Classes: Negative, Positive, Mixed and Neutral.
  - **[LABR](https://github.com/mohamedadaly/LABR)**
    - Large-Scale Arabic Book Reviews Dataset.
    - 63K Book Reviews.
    - Rating: 1 to 5.
  - **[HARD](https://github.com/elnagara/HARD-Arabic-Dataset)**
    - Hotel Arabic Reviews Dataset.
    - 94K Hotel Reviews.
    - Rating: 1 to 5.

- ### Data Pre-processing:
  - Removal of Noise, URLs, Hashtag and User-mentions, Emoticons and Emojis.
  - Removing Punctuations.
  - Letter normalization.
  - Removing elongation and Arabic diacritics.
  - Removing Stopwords, stemming, and lemmatization steps were ignored.

- ### Hyper parameters:
| Parameter        | Value |
| ---------------- | ----- |
| Batch Size       | 128   |
| Learning Rate    | 0.01  |
| Optimizer        | adam  |
| Number of Epochs | 20    |

- ### Model:
In the CNN model we’ve connected the output of the embedding layer to 1 dimension convolution layer with 64 filters and a kernel size of 2, RELU activation function, and 0.2 dropout rate then we applied to it 1 dimension Global max pooling to extract the most important features. The
architecture used is shown in the figure below.

![cnn architecture](https://user-images.githubusercontent.com/45196964/214358866-698372c4-0088-4ddb-984c-62ddddf7c01d.png)

- ### Results:
| Datasets  | Precision | Recall | F1-Score | **Accuracy** |
| --------- | --------- | ------ | -------- | ------------ |
| **ArSAS** | 77%       | 68%    | 72%      | `72.79%`     |
| **LABR**  | 89%       | 90%    | 89%      | `89.69%`     |
| **HARD**  | 94%       | 94%    | 94%      | `94.39%`     |
