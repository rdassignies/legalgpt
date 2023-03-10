# L'art du prompting : un aperçu 

!!! abstract  "Ce qu'il faut retenir" 

	- le prompting est la manière de piloter les modèles de language comme GPT 3 pour obtenir des résultats précis : Questions/Réponses, raisonnement logique ou résumé
	- il s'agit de textes rédigés en language naturel dont les règles ne sont pas formellement énumérées
	- il existe différentes approches en fonction des objectifs à remplir : de la formulation standards aux instructions étape par étape sophistiquées (*Chain of Thought*)


L'objectif de ces quelques pages est de fournir une initiation au pilotage des nouveaux modèles de language comme ChatGPT. La force de ce type d'outil est de fournir une interface intuitive entre l'Homme et la machine. Il suffit de poser des questions en language naturelle pour avoir la réponse avec une fiabilité plus ou moins grande. 

En effet, ces modèles de langage sont dit génératifs, c'est à dire qu'il génére des mots appelés tokens à partir d'une séquence connue. Cette séquence est précisèment votre question. 

A partir de cette approche, on peut aller beaucoup plus loin dans la manière dont les humains peuvent intéragir avec ces modèles et leur faire faire des tâches précises comme un raisonnement logique, faire preuve de bon sens ou effectuer des opérations d'arithmétiques. C'est précisément cet ensemble de techniques que je vous propose de décrire. 

L'objectif est de fournir un aperçu de cette (toute) nouvelle discipline passionnante qui fait l'objet de recherches intenses notamment par les équipes de Google. Je reviendrai plus en détail dans des exemples concrets comment le prompting peut être utilisé en matière juridique. 


## Prompting  ?  

En réalité, le prompting n'est rien d'autre qu'un bout de texte qui vise à faire faire au modèle une tâche précise : rédiger un résumé, répondre à une question ou traduire un texte. 

C'est une interface entre l'homme et le modèle. Cette interface ne correspond pas à un language formalisé comme du code informatique ou ce que l'on utilise sous Excel. 

Comme ces modèles ont 'vu' pendant leur phase d'apprentissage un nombre considérable d'exemples, ils sont capables de se situer dans le contexte fourrni par la séquence -  le *prompt* - renseigné par l'utilisateur. Il utilise sa capacité à reconnaître les *patterns* appris pour les repliquer dans la phase de *completion* qui vise à générer les mots. Cette caractéristique très intéressante fait qu'ils peuvent être utilisé pour [remplir de nombreuses tâches ](https://arxiv.org/pdf/2005.14165.pdf)dans avoir besoin de les ré-entraîner sur des jeux de données spécifiques. 

Par exemple, le prompt très simple suivant commande au modèle de résumer un texte : 

!!! Note "Prompt standard pour résumer un texte"
	Résume moi en 100 mots le texte suivant : 
	
	Texte : 
	
	Résumé :

On peut également lui fournir une liste d'exemples comme des questions/réponses et lui dire de continuer à répondre selon ce schéma. Plus subtile, on peut introduire des instructions pour répondre à manière d'un mathématicien, d'une juriste, d'un enfant ... 

## Du prompting standard à la chaine de pensées

Cette manière de s'adresser au modèle à d'abord était d'être direct à l'instar de l'exemple précédent. ll suffit de lui demander directement quel résultat on souhaite comme on le fait en posant de demandant à chatGPT de répondre à une question. 

Rapidement, il est apparu que le prompting standard n'était pas efficace dans des opérations de raisonnement logique, faire preuve de bon sens ou effectuer des opérations d'arithmétiques. 

Fort de ce constat, un papier a proposé une approche plus ambitieuse en fournissant, toujours via le *prompt*, les étapes que le modèle doit accomplir pour aboutir au résultat final. C'est approche est appelée[ 'Chain of Thought Prompting'](https://arxiv.org/pdf/2201.11903.pdf)

![Chain of Tought](../assets/img/Chain_Of_Thought_Prompt.png)

Dans cette approche, on a toujours une structure générale de quelques exemples de Questions/Réponses mais on explicite dans la réponse le chemin à parcourir pour obtenir la solution. Cette stratégie obtient de très bons résultats mais elle n'est efficace que sur les modèles de language avec de nombreux paramètres (supérieur à 100 millards). 

Il existe plusieurs raffinement concernant cette stratégie : 

- [Zero Shot Chain of Thought](https://arxiv.org/pdf/2201.11903.pdf) : l'idée est de faire créer par le modèle lui même les étapes du raisonnement avec la commande ('Raisonne étape par étape') puis d'injecter la réponse fournie à la suite du problème pour atteindre le résultat. On ne fournit rien au modèle comme exemple ("zero shot") et il élabore lui même son raisonnement. Génial, non ? On verra que cette propriété est utilisée et systématisée dans certains frameworks comme  [Demonstrate Search Predict. ](https://github.com/stanfordnlp/dsp)
-  [Self-Consistency](https://arxiv.org/pdf/2203.11171.pdf)  ou auto-consistance: cette technique consiste à générer plusieurs chaines d'instruction pour un même problème puis à retenir la solution qui revient la plus fréquemment. 

## Quelques régles pour rédiger de bons prompts

Il ne faut pas perdre de vue que l'histoire du prompting n'a que quelques mois. Les progrès dans le domaine du traitement automatique du language ont été tellement rapide que ces quelques lignes sont sûrement déjà obsolètes. 

Toujours est-il qu'il existe quelques règles, parfois contre-intuitives, concernant l'efficacité de la rédaction d'un prompt : 

- Le fait de fournir une bonne réponse dans les exemples fournies n'est pas significatif sur la performance obtenue par le modèle. Autrement dit, il apprend du pattern et non de la véracité de ce qui lui est fourni. 
- Le format est très important. Il commande la manière dont le modèle va générer la réponse par exemple sous forme de liste séparée par des virgules ou en majuscule
- le nombre d'exemples optimales est souvent de 4 à 8

## Exemples de prompts courants 

### Prompts standards  : 

![Standard Prompt](../assets/img/standard_prompt.png)

### Chain of Thought 

Dans cet exemple, GPT (davinci 003) se trompe et n'arrive pas à "raisonner" pour trouver la bonne réponse. 

![Chain Of Thought](../assets/img/CoT_Prompt_1.png)

On raffine le prompt en ajoutant : 

- la manière de calculer les deux trajets; 
- un ou plusieurs exemples (*few shots CoT*) pour lui montrer le type de raisonnement. 

Dans ce cas, il arrive au bon résultat en explicitant les étapes de son raisonnement. 

![Chain Of Thought Magic Few Shots](../assets/img/CoT_Prompt_2.png)

Il est possible, pour se passer de lui décrire quelques exemples, d'introduire un prompt "magique" du type "Décris moi les étapes de ton raisonnement. ". On parlera de *zeroshot Chain Of Thought*. 

![Chain Of Thought Magic Prompt](../assets/img/CoT_MagicPrompt.png)


-------

Liens : 

- [Learning Prompt](https://learnprompting.org/docs/)
- [Prompting GPT-3 To Be Reliable](https://arxiv.org/abs/2210.09150)
- https://www.outilsfroids.net/2023/02/vous-dorkiez-jen-suis-fort-aise-et-bien-promptez-maintenant/
- [Language Models are Few-Shot Learners](https://arxiv.org/pdf/2005.14165.pdf)

