# Le découpage des mots : les tokens

Les modèles de langage consomment du texte en entrée pour produire des sorties adaptées aux tâches prescrites. 

Pour utiliser le modèle, il est nécessaire de transformer les mots ou de procéder à un découpage élémentaire des documents. Ces opérations, dites de tokenization, sont un classique du NLP et on trouve maints exemples en ligne. 

Toutefois, je reviens quelques instants sur la notion de *tokenization* car c'est un concept qui est utilisé par GPT ou d'autres LLM notamment pour piloter la fenêtre de tir - le nombre maximum de tokens en même temps - et la grille de prix payé par l'utilisateur. 

## Les tokens ne correspondent pas exactement aux mots 

Dans un modèle comme *word2vec*, on s'est contenté d'isoler les mots un par un et de bâtir un vocabulaire. En NLP, la notion de token est plus large que celle de mots. C'est une unité élémentaire qui est utilisé par un modèle - un réseau de neurones - pour apprendre une tâche. Il peut représenter un mot, une partie de mots, un caractère unique, un signe de ponctuation, un caractère spécial ou spécifique à un modèle, etc. D'ailleurs, dans la documentation d'openAI, il est indiqué qu'un token équivaut, en anglais, à 0,75 mots.


Un modèle comme GPT consomme des tokens en entrée. Cela signifie qu'il faut d'abord transformer vos données en tokens avant leur utilisation par le modèle. Les tokenizers modernes, comme ceux utilisés par la famille GPT, permettent de ne pas avoir de mots qui ne seraient pas dans la vocabulaire car ils utilisent des sous-parties leur permettant de recomposer les mots inconnus qu'il pourrait voir hors des données d'entraînement.

## Un nombre de tokens simultanés limité

Le nombre de tokens que le modèle peut consommer en entrée est limité. Cela est vrai de tous les transformers qui traitent des séquences de longueur fixe en entrée. L'interface d'OpenAI fournit d'ailleurs un compteur de tokens. C'est également l'unité de mesure du prix facturé qui est fondé sur le nombre de tokens consommés à chaque appel de l'API.

Une fois la phrase tokénisée, le modèle produit une donnée de sortie qui correspond à la probabilité qu'un mot soit le suivant de ceux déjà renseignés. En réalité, il s'agit des probabilités distribuées à travers tous les tokens qui composent le vocabulaire du modèle. On peut choisir la plus élevée mais également la plus rare. L'essentiel est que la génération reste cohérente. 

Cette phase de sortie peut être paramétrée via l'interface d'openAI ou de la plupart des librairies. On peut notamment choisir le dégré de créativité du modèle, c'est-à-dire sa capacité à choisir des tokens très fréquents ou plus rares vus pendant la phase d'entraînement.

## Un exemple de tokenisation 

Voici un exemple concret de tokénization d'une phrase. Nous allons utiliser la librairie transformers du [site Huggingface](https://huggingface.co/)



```py
from transformers import GPT2TokenizerFast
tokenizer = GPT2TokenizerFast.from_pretrained("gpt2")
tokens = tokenizer('Une phrase de test en français')
print("La phrase représenté sous forme de référence des tokens", tokens['input_ids'])
print("Voici le résulats de la phrase après tokenisation pour ingestion par le modèle GPT2 (ancêtre de GPT3) : ", [tokenizer.decode(tok) for tok in tokens['input_ids']])

La phrase représentée sous forme de référence des tokens : 
[52, 710, 9546, 390, 1332, 551, 1216, 272, 16175, 15152] 

Voici le résulat de la phrase après tokenisation pour ingestion par le modèle GPT2 (ancêtre de GPT3) : 
['U', 'ne', ' phrase', ' de', ' test', ' en', ' fr', 'an', 'ç', 'ais']

```