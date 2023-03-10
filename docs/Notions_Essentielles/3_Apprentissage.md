# L'apprentissage

Une réseau de neurone apprend, c'est à dire qu'il ajuste par itération ses paramètres pour aboutir au résultat souhaité : prédir un mot, identifier des entités dans un texte, classifier une clause dans un contrat ... 

L'opérateur doit ajuster les hyperparamètres comme le nombre d'itérations ou la vitesse d'apprentissage pour optimiser cette phase. En cela, un réseau de neurones n'apprend pas "tout seul", il est nécessairement piloté par un humain. Il doit donc être possible d'identifier et de tracer les éléments clés de ce pilotage. 

!!! note 
	Les hyperparamètres ne doivent pas être confondus avec les paramètres. Ces derniers - également appelé poids - sont les valeurs que le modèle acquiert pendant la phase d'apprentissage. Ce sont ces valeurs qui vont permettre au modèle de prédir le mot suivant à partir d'une séquence dans GPT. 

Ce pilotage vise à optimiser l'apprentissage en fonction des objectifs et des contraintes du projets. Il existe une boucle de rétroaction entre le réglage des hyperparamètres d'apprentissage et les métriques d'évaluation. Cet interaction doit aboutir un modèle dont l'entraînement est jugé satisfaisant pour être mise en production, c'est à dire utilisé concrétement seul ou au sein d'un applicatif plus vaste.  

``` mermaid
graph LR
  A[Analyse] --> B{Apprentissage};
  B --> C{Evaluation};
  C --> |Ok !|D[Déploiement];
  C -->|Nok| A;
  E[Données] -->B;
```



## L'ajustement des hyperparamètres 

Les hyperparamètres sont de deux natures : 

- les premiers ont trait à l'architecture du réseau de neurones : le nombre de couches, la taille, etc ... 
- les seconds sont ceux qui vont être ajustés pendant la phase d'apprentissage comme la vitesse, le nombre d'itérations, la taille des données à traiter en parallèle ... 


### Illustration : journal de sortie d'entraînement d'un modèle

Les lignes suivantes correspondent aux informations qui sont produites par l'entraînement d'un réseau de neurones visant à classifier des bouts de textes en plusieurs catégories (classes). Voici les informations qu'elles contiennent : 

- l'epoch est un hyperparamètre qui correspond à un cycle d'apprentissage sur les données (un passage entier); 
- les données ne sont pas injectées en une fois dans le modèle mais sous forme de lots (batches); la taille de ces lots est un hyperparamètre. 
- la métrique utilisée ici est l'exactitude (accuracy). On voit qu'elle augmente au fur et à mesure de l'apprentissage. Elle est également appliquée au jeu de données de validation (non vue pendant l'entraînement) pour évaluer le modèle à chaque cycle (epoch). 


```py
| epoch   1 |   500/ 1782 batches | accuracy    0.714
| epoch   1 |  1000/ 1782 batches | accuracy    0.867
| epoch   1 |  1500/ 1782 batches | accuracy    0.884
-----------------------------------------------------------
| end of epoch   1 | time: 10.58s | valid accuracy    0.883
-----------------------------------------------------------
| epoch   2 |   500/ 1782 batches | accuracy    0.906
| epoch   2 |  1000/ 1782 batches | accuracy    0.903
| epoch   2 |  1500/ 1782 batches | accuracy    0.905
-----------------------------------------------------------
| end of epoch   2 | time:  8.74s | valid accuracy    0.903
-----------------------------------------------------------
| epoch   3 |   500/ 1782 batches | accuracy    0.918
| epoch   3 |  1000/ 1782 batches | accuracy    0.919
| epoch   3 |  1500/ 1782 batches | accuracy    0.918
-----------------------------------------------------------
| end of epoch   3 | time:  8.80s | valid accuracy    0.822
-----------------------------------------------------------
| epoch   4 |   500/ 1782 batches | accuracy    0.935
| epoch   4 |  1000/ 1782 batches | accuracy    0.939
| epoch   4 |  1500/ 1782 batches | accuracy    0.938
-----------------------------------------------------------
| end of epoch   4 | time:  8.82s | valid accuracy    0.910


```
*source : https://pytorch.org/tutorials/beginner/text_sentiment_ngrams_tutorial.html?highlight=classification *

Les choix opérés pendant cette phase, comme la sélection des métriques d'évaluation, va avoir des conséquences sur le rendu final, c'est à dire la capacité à prédir du modèle. 

Une fois entraînés, le modèle est figé totalement ou partiellement. On peut alors l'utiliser pour faire le spécialiser sur certaines tâches moyennant un entraînement complémentaire ou tel quel. 





---