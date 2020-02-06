# Introduciton
**BERT** (Bidirectional Encoder Representations from Transformers) is a method of pretraining language representations that was used to create models that NLP practicioners can then download and use for free. You can either use these models to extract high quality language features from your text data, or you can fine-tune these models on a specific task (classification, entity recognition, question answering, etc.) with your own data to produce state of the art predictions.

In this repository, we will try to modify and fine-tune BERT to create a powerful NLP model for Question Answering, which means giving a text and a question, the model will be able to find the answer to the question in the text.

The dataset that we will be using is **SQuAD 2.0**. The dataset consist of questions posed by crowdworkers on a set of Wikipedia articles, where the answer to every question is a segment of text, or span, from the corresponding reading passage, or the question might be unanswerable.

# Using  the tranformers library by HuggingFace

We first attempted to run the scripts provided by the transformers library by HuggingFace that fine-tune the base model of BERT in order to train it for Question Answering. We have used a small portion of the SQuAD dataset because our environment's performance didn't allow us to run the training on the whole dataset.

The final fine-tuned model has a precision of ?? %

The script that fine-tune BERT using the library transformer is: ?????.py

# Implementing the fine-tuning of BERT

After getting an insight into the challenges that we have to face, we've tried to implement the training and evaluation loops to fine-tune BERT with the SQuAD 2.0 dataset. We've analyzed the script given by the library transformers, I we've attempted to recreate a fine-tuning more adapted to our needs. These are the steps that we've followed to fine-tune BERT.

    Download the SQuAD 2.0 dataset (json files)
    Transform our dataset into the format that BERT can be trained on by:
        Applying the BERT tokenizer to our data.
        Adding special tokens to the start and end of each sentence.
        Padding & truncating all sentences to a single constant length.
        Mapping the tokens to their IDs.
    Load the base model of BERT .
    Train the BERT model with our SQuAD dataset.
    Evaluate the model.
    
By using 20000 text-question-answer, the precision of our model was: **47%**

# Resources

HuggingFace/transformers: https://github.com/huggingface/transformers 
SQuAD 2.0: https://rajpurkar.github.io/SQuAD-explorer/

BERT Fine-Tuning Tutorial with PyTorch: http://mccormickml.com/2019/07/22/BERT-fine-tuning/
BERT for Question Answering on SQuAD 2.0: https://web.stanford.edu/class/cs224n/reports/default/15848021.pdf


# (à supprimer)

Sur ce projet, je vais vous faire travailler sur le dataset Squad V2.0. Il s'agit d'un dataset très largement exploré et dont vous verrez sur les leaderboards que les meilleurs modèles ont dépassé la performance humaine. L'objectif est de réaliser un système capable de prendre un texte et une question en input et de donner la position de la réponse dans le texte en output. Cela vous rappellera peut-être vos années de collèges et les longues séries de questions sur des textes littéraires. C'est un peu le même principe ainsi qu'une des raisons pour lesquelles ce dataset est autant étudié : il s'agit d'une compétence humaine de très haut niveau et également industrialisable dans d'assez nombreuses applications (chatbots, sites de question réponse, etc.).
Dans le jargon, on dit que la tâche effectuée est du Question Answering, et plus précisément de Close Domain Question Answering, car le texte à étudier est donné en entrée du système. A l'inverse, il existe des études sur des systèmes de Open Domain Question Answering dans lesquels l'objectif est d'abord de trouver dans un corpus de connaissances (Wikipédia par exemple), l'article le plus susceptible de répondre à la question posée, puis de trouver cette réponse dans le texte. Ce type de problématique soulève un grand nombre de défis techniques qui me semblent à la fois trop complexes et peu intéressants à gérer pour vous et c'est pour cela que j'ai préféré rester sur du CDQA.

L'objectif pour ce projet est de vous faire obtenir des résultats aussi satisfaisants que possibles sur le dataset, et notamment j'aimerais que vous utilisiez des méthodes de fine-tuning de modèles à base de transformers (BERT, RoBERTa, etc.) car il s'agit d'une des techniques les plus utilisées à l'heure actuelle dans l'industrie.
Pour le moment, j'aimerais que vous découvriez le dataset et les problématiques qu'il apporte, et que vous réfléchissiez aux potentiels moyens de gérer celles-ci, à la forme que devra avoir le modèle à entraîner (en termes d'entrée/sortie notamment), et à tout ce qui peut avoir besoin de se placer autour du modèle (traitement des données, preprocessing, etc.).
J'attire votre attention sur le fait que cette version du dataset présente des questions pour lesquelles il n'est pas possible de trouver une réponse dans le texte fourni. Il s'agit d'un problème critique que vous devrez prendre en compte.

https://medium.com/swlh/painless-fine-tuning-of-bert-in-pytorch-b91c14912caa
Voilà un exemple de fine tuning de BERT avec transformers.

Il y a également un exemple de fine tuning de Squad dans la documentation de transformers. Ca peut vous donner des idées.

https://github.com/huggingface/transformers/blob/master/examples/run_squad.py

autre example bert fine tuning
https://www.pragnakalp.com/nlp-tutorial-setup-question-answering-system-bert-squad-colab-tpu/

https://arxiv.org/pdf/1810.04805.pdf

https://mccormickml.com/2019/07/22/BERT-fine-tuning/#1-setup
