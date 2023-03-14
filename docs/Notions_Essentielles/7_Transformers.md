# Les Transformers 

## L'Attention est tout ce qu'il vous faut


Les architectures de type [transformers](https://arxiv.org/abs/1706.03762) ont constitué une avancée très importante en résolvant notamment les problèmes de mémoire. Cette architecture et ces nombreuses variantes dont le [nom rappelle un jouet célèbre des années 80](https://www.google.com/search?q=80%27s+transformers+toys&oq=80%27s+transfo&aqs=chrome.1.0i19i512l2j69i57j0i19i512l7.4930j0j15&sourceid=chrome&ie=UTF-8) sont à l'origine de GPT et de progrès fulgurants dans le domaine.

L'architecture des transformers utilise plusieurs mécanismes, parmi lesquels :

- Un mécanisme d'attention, qui avait déjà été [conceptualisé auparavant](https://arxiv.org/pdf/1409.0473.pdf), permet aux mots d'une phrase d'apprendre l'importance des autres dans la même phrase (self attention) ou dans une autre séquence (attention) comme une phrase à traduire. Comme indiqué dans l'article sur la représentation des mots, ce mécanisme permet d'affiner les relations de pondération entre les mots donc de raffiner les contextes appris. 

- Deux blocs :

	- encoder : il prend en entrée une phrase d'une longueur variable et l'encode sous forme d'un vecteur de longueur fixe qui varie en fonction du contexte (principe du plongement lexical). Dans cette phase, le mécanisme d'attention se fait sur tous les mots de la phrase à la fois : chaque mot peut 'regarder' tous les autres avant ou après lui. Cette caractéristique se retrouve dans le nom des encoder qui on comme prefix B pour Bidirectionnel. 

	- decoder : dans cette phase, chaque mot ne peut 'regarder' qu'en arrière, les mots qui le suivent sont exclus du mécanisme d'attention. 

Ces blocs peuvent être utiilisés séparement ou ensemble (encoder-decoder ou sequence to sequence model). L'utilisation de ces différentes parties obéit à des traitements particuliers : 

|Type | Tâches | Models |
| -------- | ------ | ------|
| Encoder | Classification, reconnaissance d'entités nommées, analyse de sentiment, questions-réponses (extractive) | BERT |
| Decoder | Génération de séquences de mots | GPT x |
| Sequence to sequence | Résumé, traduction, questions-réponses (génération) | T5 

## L'entraînement

Comme on l'a vu pour *word2vec*, les Transformers sont entraînés avec plusieurs approches : 
- BERT : un mot (token) est masqué aléatoirement au milieu d'une phrase, il doit être découvert. Le modèle regarde avant et après le token masqué (Encoder Bidirectionnel) ;
- GPT : le mot(token) suivant une séquence doit être découvert. Le modèle ne regarde que la séquence d'avant (Decoder Unidirectionnel).

Cet entraînement de base, dont le principal objectif est d'apprendre la représentation des mots,  peut être poursuivi partiellement à partir d'une couche supplémentaire comme indiqué dans l'article consacré à l'entraînement des modèles. 