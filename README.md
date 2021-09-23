# Question Answering TF
**Extract Sequence Features::**  WordSequences -> TokenizedSequences -> PretrainedAlbert -> ContextualizedFeatureSequences -> TransformerEncoder(FineTuning) -> Classifiers(Dense, Softmax)

Dataset :: [Squad 2](https://rajpurkar.github.io/SQuAD-explorer/ "Squad2") 

* Dataset :: 
  * This dataset contains context and there corresponding QA on diffrent topics.

* Inspiration::
  * We have to train a model for question answering.
  * (Question, Context) -> Model -> (Answer).

Tools :: Tensorflow, TFHub, tensorflow_text, sentencepiece, Keras \
Architecture :: Transformer

### Steps::
  1. Load dataset zip from zip Files(Google Drive).

  2. Get AlbertPreprocessor and AlbertBase3 from TFHub

  3. Load dataset -> DataExtraction -> DatasetCreation (TF Dataset with tokenization)

  4. Training Steps :: 
  
    1. Required Layers Creation (TransformerEncoder, TextContextualEmbedding with AlbertBase3)

    2. Convert token sequeces to sequece of features with the help of pretrained albert.
  
    3. AlbertBase3 Output will be than passed from transformer encoder for features extraction(Fine Tuning).

    4. Contextualized Sequence Features -> Dense Layers -> Softmax (Answer start index, end index prediction).
  
  5. Training (We failed for now!)
