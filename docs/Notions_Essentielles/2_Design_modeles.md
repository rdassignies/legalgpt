# Sélection et hyperparamétrage des modèles 

Les données collectées et préparées doivent être injectées dans un ou plusieurs types de modèles d'apprentissage choisis généralement par le maître d'œuvre.

Ce ou ces modèle(s) sont sélectionnés par le maître d'œuvre en fonction des objectifs et du problème traité. Il existe pléthore d'algorithmes dans le domaine du Machine Learning qui peuvent répondre à différents objectifs. 

A ce stade, il faut distinguer deux types d'hyperparamètres :

- ceux qui définissent l'architecture du modèle ; 
- ceux qui sont utilisés pendant la phase d'entraînement. 

!!! note "Paramètres et hyperparamètres"
	Les hyperparamètres ne doivent pas être confondus avec les paramètres. Ces derniers - également appelé poids - sont les valeurs que le modèle acquiert pendant la phase d'apprentissage. Ce sont ces valeurs qui vont permettre au modèle de prédir le mot suivant à partir d'une séquence dans GPT. 


## Les hyperparamètres du modèle

La premier série d'**hyperparamètres** est relative à l'architecture du modèle. Lorsqu'il s'agit d'un réseau de neurones (*Deep Learning*), ils sont constitués du type de couche, de leur nombre, des fonctions d'activation utilisées, etc. 

Le plus souvent, le maître d'œuvre ne part pas d'une feuille blanche. Il va sélectionner des modèles sur étagère souvent issus du monde de la recherche comme les *Transformers*.

Ces modèles peuvent être recréés à partir de librairies logicielles qui fournissent les briques élémentaires comme l'illustre l'exemple ci-après ou utilsés directement via des services en ligne comme AWS ou GCP. 

Parfois, il s'agit de mixer un modèle figé (pré-entraîné) et de lui ajouter une couche entraînable pour accomplir une tâche particulière ou l'adapter à un domaine spécifique. 

Voici un bout de code utilisant la librairie *pytorch* qui met en œuvre un classifieur de texte simple avec une couche linéaire. 


``` { .python title="Classifieur de texte" .annotate }
class TextClassificationModel(nn.Module):

    def __init__(self, vocab_size, embed_dim, num_class):
        super(TextClassificationModel, self).__init__()
        self.embedding = nn.EmbeddingBag(vocab_size, embed_dim, sparse=True)  # (1)
        self.fc = nn.Linear(embed_dim, num_class # (2)
        self.init_weights()

    def init_weights(self): # (3)
        initrange = 0.5
        self.embedding.weight.data.uniform_(-initrange, initrange)
        self.fc.weight.data.uniform_(-initrange, initrange)
        self.fc.bias.data.zero_()

```

1.      :Cette ligne fournit le type d'embeddings et la taille. On peut modifier la taille ou le type de représentation des mots 
2.      :Cette ligne ajoute une couche linéaire à notre modèle (ax+b). On pourra en ajouter d'autres avec un autre type, etc.
3.      :Cette fonction initialise les paramètres (poids-*weights*) qui seront appris par le  modèle. 


## Les hyperparamétres d'apprentissage

La deuxième série d'hyperparamètres sont ceux qui permettent [d'entraîner effectivement ](3_Apprentissage.md)le modèle comme la vitesse, le nombre d'itérations, la taille des données à traiter en parallèle...  



