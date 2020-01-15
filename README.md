# NlpSquad

Sur ce projet, je vais vous faire travailler sur le dataset Squad V2.0. Il s'agit d'un dataset très largement exploré et dont vous verrez sur les leaderboards que les meilleurs modèles ont dépassé la performance humaine. L'objectif est de réaliser un système capable de prendre un texte et une question en input et de donner la position de la réponse dans le texte en output. Cela vous rappellera peut-être vos années de collèges et les longues séries de questions sur des textes littéraires. C'est un peu le même principe ainsi qu'une des raisons pour lesquelles ce dataset est autant étudié : il s'agit d'une compétence humaine de très haut niveau et également industrialisable dans d'assez nombreuses applications (chatbots, sites de question réponse, etc.).
Dans le jargon, on dit que la tâche effectuée est du Question Answering, et plus précisément de Close Domain Question Answering, car le texte à étudier est donné en entrée du système. A l'inverse, il existe des études sur des systèmes de Open Domain Question Answering dans lesquels l'objectif est d'abord de trouver dans un corpus de connaissances (Wikipédia par exemple), l'article le plus susceptible de répondre à la question posée, puis de trouver cette réponse dans le texte. Ce type de problématique soulève un grand nombre de défis techniques qui me semblent à la fois trop complexes et peu intéressants à gérer pour vous et c'est pour cela que j'ai préféré rester sur du CDQA.

L'objectif pour ce projet est de vous faire obtenir des résultats aussi satisfaisants que possibles sur le dataset, et notamment j'aimerais que vous utilisiez des méthodes de fine-tuning de modèles à base de transformers (BERT, RoBERTa, etc.) car il s'agit d'une des techniques les plus utilisées à l'heure actuelle dans l'industrie.
Pour le moment, j'aimerais que vous découvriez le dataset et les problématiques qu'il apporte, et que vous réfléchissiez aux potentiels moyens de gérer celles-ci, à la forme que devra avoir le modèle à entraîner (en termes d'entrée/sortie notamment), et à tout ce qui peut avoir besoin de se placer autour du modèle (traitement des données, preprocessing, etc.).
J'attire votre attention sur le fait que cette version du dataset présente des questions pour lesquelles il n'est pas possible de trouver une réponse dans le texte fourni. Il s'agit d'un problème critique que vous devrez prendre en compte.

https://medium.com/swlh/painless-fine-tuning-of-bert-in-pytorch-b91c14912caa
Voilà un exemple de fine tuning de BERT avec transformers.

Il y a également un exemple de fine tuning de Squad dans la documentation de transformers. Ca peut vous donner des idées.

https://github.com/huggingface/transformers/blob/master/examples/run_squad.py
