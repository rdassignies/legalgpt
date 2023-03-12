Je ne reprend ici que les papiers de recherche récents spécifiques au NLP et au droit.  La sélection n'est évidemment pas exhaustive et réflète mes centres d'intérêt (droit européen et continental, reasoning, graph, classification ...)

## Language Model (Juridique)
Pour une liste des modèles généralistes : [[LLM_Liste]]
****
### JuriBERT: A Masked-Language Model Adaptation for French Legal Text
https://arxiv.org/abs/2110.01485
**Abstract**
Language models have proven to be very useful when adapted to specific domains. Nonetheless, little research has been done on the adaptation of domain-specific BERT models in the French language. In this paper, we focus on creating a language model adapted to French legal text with the goal of helping law professionals. We conclude that some specific tasks do not benefit from generic language models pre-trained on large amounts of data. We explore the use of smaller architectures in domain-specific sub-languages and their benefits for French legal text. We prove that domain-specific pre-trained models can perform better than their equivalent generalised ones in the legal domain. Finally, we release JuriBERT, a new set of BERT models adapted to the French legal domain.

### LEGAL-BERT: The Muppets straight out of Law School
https://aclanthology.org/2020.findings-emnlp.261.pdf
**Abstract**
BERT has achieved impressive performance in several NLP tasks. However, there has been limited investigation on its adaptation guidelines in specialised domains. Here we focus on the legal domain, where we explore several approaches for applying BERT models to downstream legal tasks, evaluating on multiple datasets. Our findings indicate that the previous guidelines for pre-training and fine-tuning, often blindly followed, do not always generalize well in the legal domain. Thus we propose a systematic investigation of the available strategies when applying BERT in specialised domains. These are: (a) use the original BERT out of the box, (b) adapt BERT by additional pre-training on domain-specific corpora, and (c) pre-train BERT from scratch on domain-specific corpora. We also propose a broader hyper-parameter search space when fine-tuning for downstream tasks and we release LEGAL-BERT, a family of BERT models intended to assist legal NLP research, computational law, and legal technology applications.

### LegalDB: Long DistilBERT for Legal Document Classification
https://ieeexplore.ieee.org/document/9392558
**Abstract**
Transformers have caused a paradigm shift in tasks related to natural language. From text summarization to classification, these models have established new state-of-the-art results on various general and closed domain tasks. Having said that, most of the popular transformer based models (BERT - Bidirectional Encoder Representations from Transformers, DistilBERT, and RoBERTa) face a limitation in terms of the content length they can accept. This is because the self-attention used by these models scales quadratically with the context sequence length. While this works well for short passages and questions, for longer documents this method fails to effectively capture both the local and global contexts. This shortcoming is underscored further for closed domain tasks like Legal Document classification, where the length of the documents can extend up to a couple of pages and which differ in their vocabulary from general English substantially. In this paper, a new architecture is proposed, where the concept of "long" attention is applied to a distilled BERT and then the model is pre-trained on legal-domain specific corpora. This helps combine a local windowed attention with task-motivated global attention, making the model contextually-aware for longer sequences. The proposed model is also able to outperform fine-tuned BERT and other transformer-based models at the task of legal document classification while also being faster.

## Généralités
*****
### How Does NLP Benefit Legal System: A Summary of Legal Artificial Intelligence
https://arxiv.org/pdf/2004.12158.pdf
Abstract
Legal Artificial Intelligence (LegalAI) focuses
on applying the technology of artificial intelligence, especially natural language processing,to benefit tasks in the legal domain. In recent years, LegalAI has drawn increasing attention rapidly from both AI researchers and legal professionals, as LegalAI is beneficial to the legal system for liberating legal professionals from a maze of paperwork. Legal professionals often think about how to solve tasks from rulebased and symbol-based methods, while NLP
researchers concentrate more on data-driven and embedding methods. In this paper, we describe the history, the current state, and the future directions of research in LegalAI. We illustrate the tasks from the perspectives of legal
professionals and NLP researchers and show several representative applications in LegalAI. We conduct experiments and provide an indepth analysis of the advantages and disadvantages of existing works to explore possible future directions. You can find the implementation of our work from https://github.
com/thunlp/CLAIM.

## Prompting - Legal Prompting
*******
### Legal Prompting: Teaching a Language Model to Think Like a Lawyer
https://arxiv.org/abs/2212.01326

**Abstract** : 
Large language models that are capable of zero or few-shot prompting approaches have given rise to the new research area of prompt engineering. Recent advances showed that for example Chain-of-Thought (CoT) prompts can improve arithmetic or common sense tasks significantly. We explore how such approaches fare with legal reasoning tasks and take the COLIEE entailment task based on the Japanese Bar exam for testing zero-shot/few-shot and fine-tuning approaches. Our findings show that while CoT prompting and fine-tuning with explanations approaches show improvements, the best results are produced by prompts that are derived from specific legal reasoning techniques such as IRAC (Issue, Rule, Application, Conclusion). Based on our experiments we improve the 2021 best result from 0.7037 accuracy to 0.8148 accuracy and beat the 2022 best system of 0.6789 accuracy with an accuracy of 0.7431.

### Legal Prompt Engineering for Multilingual Legal Judgement Prediction
https://arxiv.org/pdf/2212.02199v1.pdf
Abstract (traduction FR auto)
Le Legal Prompt Engineering (LPE) ou Legal Prompting est un processus visant à guider et à assister un modèle de langage large (LLM) pour effectuer un traitement du langage juridique naturel (NLLP) compétence. Notre objectif est d'utiliser le LPE avec des LLM sur
documents juridiques longs pour le Legal Judgement prédiction (LJP). Nous étudions la performance du LPE pour des faits donnés dans des textes de cas provenant de la Cour Européenne de Justice dans des textes de cas de la Cour Européenne des Droits de l'Homme (en anglais) européenne des droits de l'homme (en anglais) et du Tribunal fédéral fédérale de Suisse (en allemand, français et italien). italien). Nos résultats montrent que le LPE est meilleur par rapport aux lignes de base, mais qu'il n'est toujours pas à la hauteur de l'état actuel de l'art rn 'état actuel de l'art des approches supervisées.
approches supervisées. Néanmoins, les résultats sont importants, car 1) aucune donnée explicite spécifique au domaine n'a été utilisée - nous montrons donc que le transfert au domaine juridique est possible pour les approches LL générales.
Nous montrons donc que le transfert vers le domaine juridique est possible pour les MLL à usage général. Les LLMs ont été directement appliqués sans aucune formation ou réglage fin supplémentaire - ce qui ce qui permet de réaliser des économies considérables en termes de coûts de calcul supplémentaires.

### Active Prompting with Chain-of-Thought for Large Language Models
https://arxiv.org/pdf/2302.12246
**Abstract**
The increasing scale of large language models (LLMs) brings emergent abilities to various complex tasks requiring reasoning, such as arithmetic and commonsense reasoning. It is known that the effective design of task-specific prompts is critical for LLMs' ability to produce high-quality answers. In particular, an effective approach for complex question-and-answer tasks is example-based prompting with chain-of-thought (CoT) reasoning, which significantly improves the performance of LLMs. However, current CoT methods rely on a fixed set of human-annotated exemplars, which are not necessarily the most effective examples for different tasks. This paper proposes a new method, Active-Prompt, to adapt LLMs to different tasks with task-specific example prompts (annotated with human-designed CoT reasoning). For this purpose, we propose a solution to the key problem of determining which questions are the most important and helpful ones to annotate from a pool of task-specific queries. By borrowing ideas from the related problem of uncertainty-based active learning, we introduce several metrics to characterize the uncertainty so as to select the most uncertain questions for annotation. Experimental results demonstrate the superiority of our proposed method, achieving state-of-the-art on eight complex reasoning tasks. Further analyses of different uncertainty metrics, pool sizes, zero-shot learning, and accuracy-uncertainty relationship demonstrate the effectiveness of our method. 

### More than you've asked for: A Comprehensive Analysis of Novel Prompt Injection Threats to Application-Integrated Large Language Models
https://arxiv.org/pdf/2302.12173
**Abstract**
We are currently witnessing dramatic advances in the capabilities of Large Language Models (LLMs). They are already being adopted in practice and integrated into many systems, including integrated development environments (IDEs) and search engines. The functionalities of current LLMs can be modulated via natural language prompts, while their exact internal functionality remains implicit and unassessable. This property, which makes them adaptable to even unseen tasks, might also make them susceptible to targeted adversarial prompting. Recently, several ways to misalign LLMs using Prompt Injection (PI) attacks have been introduced. In such attacks, an adversary can prompt the LLM to produce malicious content or override the original instructions and the employed filtering schemes. Recent work showed that these attacks are hard to mitigate, as state-of-the-art LLMs are instruction-following. So far, these attacks assumed that the adversary is directly prompting the LLM.
In this work, we show that augmenting LLMs with retrieval and API calling capabilities (so-called Application-Integrated LLMs) induces a whole new set of attack vectors. These LLMs might process poisoned content retrieved from the Web that contains malicious prompts pre-injected and selected by adversaries. We demonstrate that an attacker can indirectly perform such PI attacks. Based on this key insight, we systematically analyze the resulting threat landscape of Application-Integrated LLMs and discuss a variety of new attack vectors. To demonstrate the practical viability of our attacks, we implemented specific demonstrations of the proposed attacks within synthetic applications. In summary, our work calls for an urgent evaluation of current mitigation techniques and an investigation of whether new techniques are needed to defend LLMs against these threats.

## Questions/Réponses (Q&A)
******
### Question Answering for Privacy Policies: Combining Computational and Legal Perspectives

https://arxiv.org/pdf/1911.00841.pdf
**Abstract**
Privacy policies are long and complex documents that are difficult for users to read and understand, and yet, they have legal effects on how user data is collected, managed and used. Ideally, we would like to empower users to inform themselves about issues that matter to them, and enable them to selective explore those issues. We present PRIVACYQA, a corpus consisting of 1750 questions about the privacy policies of mobile applications, and over 3500 expert annotations of relevant answers. We observe that a strong neural baseline underperforms human performance by almost 0.3 F1 on PRIVACYQA, suggesting considerable room for improvement for future systems. Further, we use this dataset to shed light on challenges to question answerability, with domain-general implications for any question answering system. The PRIVACYQA corpus offers a challenging corpus for question answering, with genuine real-world utility


## Zero/Few Shots Learning
*******
### Billions of Parameters Are Worth More Than In-domain Training Data: A case study in the Legal Case Entailment Task
https://arxiv.org/pdf/2205.15172.pdf
**Abstract**
Recent work has shown that language models scaled to billions of parameters, such as GPT-3, perform remarkably well in zeroshot and few-shot scenarios. In this work, we experiment with zero-shot models in the legal case entailment task of the COLIEE 2022 competition. Our experiments show that scaling the number of parameters in a language model improves the F1 score of our previous zeroshot result by more than 6 points, suggesting that stronger zero-shot capability may be a characteristic of larger models, at least for this task. Our 3B-parameter zero-shot model outperforms all models, including ensembles, in the COLIEE 2021 test set and also achieves the best performance of a single model in the COLIEE 2022 competition, second only to the ensemble composed of the 3B model itself and a smaller version of the same model. Despite the challenges posed by large language models, mainly due to latency constraints in real-time applications, we provide a demonstration of our zero-shot monoT5-3b model being used in production as a search engine, including for legal documents. The code for our submission and the demo of our system are available at https://github.com/neuralmind-ai/coliee and https://neuralsearchx.neuralmind.ai, respectively.
 
## Clause generation (clausier)
*****
### Graph-based Keyword Planning for Legal Clause Generation from Topics
https://arxiv.org/pdf/2301.06901.pdf
**Abstract**
Generating domain-specific content such as legal clauses based on minimal user-provided information can be of significant benefit in automating legal contract generation. In this paper, we propose a controllable graph-based
mechanism that can generate legal clauses using only the topic or type of the legal clauses.
Our pipeline consists of two stages involving a graph-based planner followed by a clause generator. The planner outlines the content of a legal clause as a sequence of keywords in the order of generic to more specific clause information based on the input topic using a controllable graph-based mechanism. The generation stage takes in a given plan and generates a
clause. The pipeline consists of a graph-based planner followed by text generation. We illustrate the effectiveness of our proposed twostage approach on a broad set of clause topics in contracts.

## NLI (inférence)
****
### ContractNLI: A Dataset for Document-level Natural Language Inference for Contracts
https://aclanthology.org/2021.findings-emnlp.164.pdf
**Abstract**
Reviewing contracts is a time-consuming procedure that incurs large expenses to companies and social inequality to those who cannot afford it. In this work, we propose “document-level natural language inference (NLI) for contracts”, a novel, real-world application of NLI that addresses such problems. In this task, a system is given a set of hypotheses (such as “Some obligations of Agreement may survive termination.”) and a contract, and it is asked to classify whether each hypothesis is “entailed by”, “contradicting to” or “not mentioned by” (neutral to) the contract as well as identifying “evidence” for the decision as spans in the contract. We annotated and release the largest corpus to date consisting of 607 annotated contracts. We then show that existing models fail badly on our task and introduce a strong baseline, which (a) models evidence identification as multi-label classification over spans instead of trying to predict start and end tokens, and (b) employs more sophisticated context segmentation for dealing with long documents. We also show that linguistic characteristics of contracts, such as negations by exceptions, are contributing to the difficulty of this task and that there is much room for improvement.

### Validity Assessment of Legal Will Statements
as Natural Language Inference
https://arxiv.org/pdf/2210.16989.pdf
**Abstract**
This work introduces a natural language inference (NLI) dataset that focuses on the validity of statements in legal wills. This dataset
is unique because: (a) each entailment decision requires three inputs: the statement from the will, the law, and the conditions that hold
at the time of the testator’s death; and (b) the
included texts are longer than the ones in current NLI datasets. We trained eight neural NLI models in this dataset. All the models achieve
more than 80% macro F1 and accuracy, which indicates that neural approaches can handle this task reasonably well. However, group accuracy, a stricter evaluation measure that is calculated with a group of positive and negative
examples generated from the same statement as a unit, is in mid 80s at best, which suggests that the models’ understanding of the task remains superficial. Further ablative analyses and explanation experiments indicate that all
three text segments are used for prediction, but some decisions rely on semantically irrelevant tokens. This indicates that overfitting on these longer texts likely happens, and that additional research is required for this task to be solved.

## Résumé  automatique
******
### Incorporating Domain Knowledge for Extractive Summarization of Legal Case Documents
https://arxiv.org/pdf/2106.15876.pdf
Abstract
Automatic summarization of legal case documents is an important and practical challenge. Apart from many domain-independent text summarization algorithms that can be used for this purpose, several algorithms have been developed specifically for summarizing legal case documents. However, most of the existing algorithms do not systematically incorporate domain knowledge that specifies what information should ideally be present in a legal case document summary. To address this gap, we propose an unsupervised summarization algorithm DELSumm which is designed to systematically incorporate guidelines from legal experts into an optimization setup. We conduct detailed experiments over case documents from the Indian Supreme Court. The experiments show that our proposed unsupervised method outperforms several strong baselines in terms of ROUGE scores, including both general summarization algorithms and legal-specific ones. In fact, though our proposed algorithm is unsupervised, it outperforms several supervised summarization models that are trained over thousands of document-summary pairs.

### ArgLegalSumm: Improving Abstractive Summarization of Legal
*Documents with Argument Mining*
https://arxiv.org/pdf/2209.01650.pdf
**Abstract**
A challenging task when generating summaries of legal documents is the ability to address their argumentative nature. We introduce a simple technique to capture the argumentative structure of legal documents by integrating argument role labeling into the summarization process. Experiments with pretrained language models show that our proposed approach improves performance over strong baselines.

### EUR-Lex-Sum: A Multi- and Cross-lingual Dataset for Long-form Summarization in the Legal Domain
https://arxiv.org/pdf/2210.13448.pdf
**Abstract**
Existing summarization datasets come with two main drawbacks: (1) They tend to focus on overly exposed domains, such as news articles or wiki-like texts, and (2) are primarily monolingual, with few multilingual datasets. In this work, we propose a novel dataset, called EUR-Lex-Sum, based on manually curated document summaries of legal acts from the European Union law platform (EUR-Lex). Documents and their respective summaries exist as cross-lingual paragraph-aligned data in several of the 24 official European languages, enabling access to various cross-lingual and lower-resourced summarization setups. We obtain up to 1,500 document/summary pairs per language, including a subset of 375 crosslingually aligned legal acts with texts available in all 24 languages. In this work, the data acquisition process is detailed and key characteristics of the resource are compared to existing summarization resources. In particular, we illustrate challenging sub-problems and open questions on the dataset that could help the facilitation of future research in the direction of domain-specific cross-lingual summarization. Limited by the extreme length and language diversity of samples, we further conduct experiments with suitable extractive monolingual and cross-lingual baselines for future work. Code for the extraction as well as access to our data and baselines is available online at: https://github.com/ achouhan93/eur-lex-sum.

### An Evaluation Framework for Legal Document Summarization

https://arxiv.org/pdf/2205.08478.pdf
Abstract
A law practitioner has to go through numerous lengthy legal case proceedings for their practices of various categories, such as land dispute, corruption, etc. Hence, it is important to summarize these documents, and ensure that summaries contain phrases with intent matching the category of the case. To the best of our knowledge, there is no evaluation metric that evaluates a
summary based on its intent. We propose an automated intent-based summarization metric, which shows a better agreement with human evaluation as compared to other automated metrics like BLEU, ROUGE-L etc. in terms of human satisfaction. We also curate a dataset by annotating intent phrases in legal documents, and show a proof of concept as to how this system can be
automated. Additionally, all the code and data to generate reproducible results is available on Github.

### Legal Case Document Summarization: Extractive and Abstractive Methods and their Evaluation
https://arxiv.org/pdf/2210.07544.pdf
**Abstract**  
Summarization of legal case judgement documents is a challenging problem in Legal NLP. However, not much analyses exist on how different families of summarization models (e.g., extractive vs. abstractive) perform when applied to legal case documents. This question is particularly important since many recent transformer-based abstractive summarization models have restrictions on the number of input tokens, and legal documents are known to be very long. Also, it is an open question on how best to evaluate legal case document summarization systems. In this paper, we carry out extensive experiments with several extractive and abstractive summarization methods (both supervised and unsupervised) over three legal summarization datasets that we have developed. Our analyses, that includes evaluation by law practitioners, lead to several interesting insights on legal summarization in specific and long document summarization in general.

## Transfert learning
*******
### An Empirical Study on Cross-X Transfer for _Lega_l Judgment Prediction
https://arxiv.org/pdf/2209.12325.pdf 
Abstract
Cross-lingual transfer learning has proven useful in a variety of Natural Language Processing (NLP) tasks, but it is understudied in the context of legal NLP, and not at all in Legal Judgment Prediction (LJP). We explore transfer learning techniques on LJP using the trilingual Swiss-Judgment-Prediction dataset, including cases written in three languages. We find that cross-lingual transfer improves the overall results across languages, especially when we use adapter-based fine-tuning. Finally, we further improve the model’s performance by augmenting the training dataset with machine-translated versions of the original documents, using a 3× larger training corpus. Further on, we perform an analysis exploring the effect of cross-domain and crossregional transfer, i.e., train a model across domains (legal areas), or regions. We find that in both settings (legal areas, origin regions), models trained across all groups perform overall better, while they also have improved results in the worst-case scenarios. Finally, we report improved results when we ambitiously apply cross-jurisdiction transfer, where we further augment our dataset with Indian legal cases

## Recommender system 
*******

### Evaluating Document Representations for Content-based Legal Literature Recommendations
https://arxiv.org/pdf/2104.13841.pdf

**Abstract**
Recommender systems assist legal professionals in finding relevant literature for supporting their case. Despite its importance for the profession, legal applications do not reflect the latest advances in recommender systems and representation learning research. Simultaneously, legal recommender systems are typically evaluated in small-scale user study without any public available benchmark datasets. Thus, these studies have limited reproducibility. To address the gap between research and practice, we explore a set of state-ofthe-art document representation methods for the task of retrieving semantically related US case law. We evaluate text-based (e.g., fastText, Transformers), citation-based (e.g., DeepWalk, Poincaré), and hybrid methods. We compare in total 27 methods using two silver standards with annotations for 2,964 documents. The silver standards are newly created from Open Case Book and Wikisource and can be reused under an open license facilitating reproducibility. Our experiments show that document representations from averaged fastText word vectors (trained on legal corpora) yield the best results, closely followed by Poincaré citation embeddings. Combining fastText and Poincaré in a hybrid manner further improves the overall result. Besides the overall performance, we analyze the methods depending on document length, citation count, and the coverage of their recommendations. We make our source code, models, and datasets publicly available.


## Raisonnement juridique
******
### Finding the Law: Enhancing Statutory Article Retrieval via Graph Neural Networks
https://arxiv.org/pdf/2301.12847.pdf
**Abstract**
Statutory article retrieval (SAR), the task of retrieving statute law articles relevant to a legal question, is a promising application of legal text processing. In particular, high-quality SAR systems can improve the work efficiency of legal professionals and provide basic legal assistance to citizens in need at no cost. Unlike traditional ad-hoc information retrieval, where each document is considered a complete source of information, SAR deals with texts whose full sense depends on complementary information from the topological organization of statute law. While existing works ignore these domain-specific dependencies, we propose a novel graph-augmented dense statute retriever (G-DSR) model that incorporates the structure of legislation via a graph neural network to improve dense retrieval performance. Experimental results show that our approach outperforms strong retrieval baselines on a real-world expert-annotated SAR dataset.1

### Text-guided Legal Knowledge Graph Reasoning
https://arxiv.org/pdf/2104.02284.pdf
**Abstract**
Recent years have witnessed the prosperity of legal artificial intelligence with the development of technologies. In this paper, we propose a novel legal application of legal provision prediction (LPP), which aims to predict the related legal provisions of affairs. We formulate this task as a challenging knowledge graph completion problem, which requires not only text understanding but also graph reasoning. To this end, we propose a novel text-guided graph reasoning approach. We collect amounts of real-world legal provision data from the Guangdong government service website and construct a legal dataset called LegalLPP. Extensive experimental results on the dataset show that our approach achieves better performance compared with baselines. The code and dataset are available in https://github.com/zxlzr/LegalPP for reproducibility.

### Can GPT-3 Perform Statutory Reasoning?
https://arxiv.org/pdf/2302.06100.pdf
**Abstract**
Statutory reasoning is the task of reasoning with facts and statutes, which are rules written in natural language by a legislature. It is a basic legal skill. In this paper we explore the capabilities of the most capable GPT-3 model, text-davinci-003, on an established statutory-reasoning dataset called SARA. We consider a variety of approaches, including dynamic few-shot prompting, chain-ofthought prompting, and zero-shot prompting. While we achieve results with GPT-3 that are better than the previous best published results, we also identify several types of clear errors it makes. In investigating why these happen, we discover that GPT-3 has imperfect prior knowledge of the actual U.S. statutes on which SARA is based. More importantly, GPT-3 performs poorly at answering straightforward questions about simple synthetic statutes. By also posing the same questions when the synthetic statutes are written in sentence form, we find that some of GPT-3’s poor performance results from difficulty in parsing the typical structure of statutes, containing subsections and paragraphs.

## Similar Case Prediction

### Complex Labelling and Similarity Prediction in Legal Texts: Automatic Analysis of France’s Court of Cassation Rulings

https://hal.inria.fr/hal-03663110/file/LREC_2022___CCass_Inria-camera-ready.pdf
https://github.com/rbawden/Similarity-cour-de-cassation
**Abstract**
Detecting divergences in the applications of the law (where the same legal text is applied differently by two rulings) is an important task. It is the mission of the French Cour de Cassation. The first step in the detection of divergences is to detect similar cases, which is currently done manually by experts. They rely on summarised versions of the rulings (syntheses and keyword sequences), which are currently produced manually and are not available for all rulings. There is also a high degree of variability in the keyword choices and the level of granularity used. In this article, we therefore aim to provide automatic tools to facilitate the search for similar rulings. We do this by (i) providing automatic keyword sequence generation models, which can be used to improve the coverage of the analysis, and (ii) providing measures of similarity based on the available texts and augmented with predicted keyword sequences. Our experiments show that the predictions improve correlations of automatically obtained similarities against our specially colelcted human judgments of similarity

## Classification / NER
*****
### PyEuroVoc: A Tool for Multilingual Legal Document Classification with EuroVoc Descriptors
https://arxiv.org/pdf/2108.01139.pdf
**Abstract**
EuroVoc is a multilingual thesaurus that was built for organizing the legislative documentary of the European Union institutions. It contains thousands of categories at different levels of specificity and its descriptors are targeted by legal texts in almost thirty languages. In this work we propose a unified framework for EuroVoc classification on 22 languages by finetuning modern Transformer-based pretrained language models. We study extensively the performance of our trained models and show that they significantly improve the results obtained by a similar tool - JEX - on the same dataset. The code and the fine-tuned models were open sourced, together with a programmatic interface that eases the process of loading the weights of a trained model and of classifying a new document.

### Large-Scale Multi-Label Text Classification on EU Legislation
https://arxiv.org/pdf/1906.02192.pdf
Abstract 
We consider Large-Scale Multi-Label Text Classification (LMTC) in the legal domain. We release a new dataset of 57k legislative documents from EUR-LEX, annotated with ∼4.3k EUROVOC labels, which is suitable for LMTC, few- and zero-shot learning. Experimenting with several neural classifiers, we show that BIGRUs with label-wise attention perform better than other current state of the art methods. Domain-specific WORD2VEC and context-sensitive ELMO embeddings further improve performance. We also find that considering only particular zones of the documents is sufficient. This allows us to bypass BERT’s maximum text length limit and finetune BERT, obtaining the best results in all but zero-shot learning cases.

### The Unreasonable Effectiveness of the Baseline: Discussing SVMs in Legal Text Classification
https://arxiv.org/pdf/2109.07234.pdf
**Abstract**
We aim to highlight an interesting trend to contribute to the ongoing debate around advances within legal Natural Language Processing. Recently, the focus for most legal text classification tasks has shifted towards large pre-trained deep learning models such as BERT. In this paper, we show that a more traditional approach based on Support Vector Machine classifiers reaches surprisingly competitive performance with BERT-based models on the classification tasks in the LexGLUE benchmark. We also highlight that error reduction obtained by using specialised BERT-based models over baselines is noticeably smaller in the legal domain when compared to general language tasks. We present and discuss three hypotheses as potential explanations for these results to support future discussions.

### Effectively Leveraging BERT for Legal Document Classification
https://aclanthology.org/2021.nllp-1.22.pdf
**Abstract**
Bidirectional Encoder Representations from Transformers (BERT) has achieved state-of-the-art performances on several text classification tasks, such as GLUE and sentiment analysis. Recent work in the legal domain started touse BERT on tasks, such as legal judgementprediction and violation prediction. A common
practise in using BERT is to fine-tune apre-trained model on a target task and truncatethe input texts to the size of the BERT input (e.g. at most 512 tokens). However, due to the unique characteristics of legal documents, it is not clear how to effectively adapt BERT in the legal domain. In this work, we investigate how to deal with long documents, and how is the importance of pre-training on documents from the same domain as the target task. We conduct experiments on the two recent datasets: ECHR Violation Dataset and the Overruling Task Dataset, which are multi-label and binary classification tasks, respectively. Importantly, on average the number of tokens in a document from the ECHR Violation Dataset is more than 1,600. While the documents in the Overruling Task Dataset are shorter (the maximum number of tokens is 204). We thoroughly compare several techniques for adapting BERT on long documents and compare different models pretrained on the legal and other domains. Our experimental results show that we need to explicitly adapt BERT to handle long documents, as the truncation leads to less effective performance.
We also found that pre-training on the documents that are similar to the target task would result in more effective performance on several scenario.

### Predicting the Law Area and Decisions of French Supreme Court Cases
https://www.acl-bg.org/proceedings/2017/RANLP%202017/pdf/RANLP092.pdf
**Abstract**
In this paper, we investigate the application of text classification methods to predict the law area and the decision of cases judged by the French Supreme Court. We also investigate the influence of the time period in which a ruling was made over the textual form of the case description and the extent to which it is necessary to mask the judge’s motivation for a ruling to emulate a real-world test scenario. We report results of 96% f1 score in predicting a case ruling, 90% f1 score in predicting the law area of a case, and 75.9% f1 score in estimating
the time span when a ruling has been issued using a linear Support Vector
Machine (SVM) classifier trained on lexicalfeatures.

### Extracting Proceedings Information and Legal References from Court Decisions with Machine-Learning
https://papers.ssrn.com/sol3/Delivery.cfm/SSRN_ID3921634_code3536982.pdf?abstractid=3919849&mirid=1
**Abstract**
This research examines the level of quality of information extracted from court decisions thanks to supervised machine-learning. The perimeter of the experience encompasses French civil decisions of all three jurisdictional degrees. It covers proceedings data, such as judicial dates and jurisdictions, and legal citations. The experience involves multi-label named-entity recognition (NER) and compares different algorithms : CRF, Spacy, Flair and DeLFT. An overall quality score of 87.5% has been reached with Flair and a large number of annotations unevenly distributed among 27 labels. Individual legal references are extracted with a score of 90% through a specific two-step training combining CRF and Flair. The paper also proposes a methodology based on a model mix to save annotation time. 

## Information retrieval 
*****
### A Statutory Article Retrieval Dataset in French
https://arxiv.org/pdf/2108.11792.pdf

**Abstract**
Statutory article retrieval is the task of automatically retrieving law articles relevant to a legal question. While recent advances in natural language processing have sparked considerable interest in many legal tasks, statutory article retrieval remains primarily untouched due to the scarcity of large-scale and highquality annotated datasets. To address this bottleneck, we introduce the Belgian Statutory Article Retrieval Dataset (BSARD), which consists of 1,100+ French native legal questions labeled by experienced jurists with relevant articles from a corpus of 22,600+ Belgian law articles. Using BSARD, we benchmark several state-of-the-art retrieval approaches, including lexical and dense architectures, both in zero-shot and supervised setups. We find that fine-tuned dense retrieval models significantly outperform other systems. Our best performing baseline achieves 74.8% R@100, which is promising for the feasibility of the task and indicates there is still room for improvement. By the specificity of the domain and addressed task, BSARD presents a unique challenge problem for future research on legal information retrieval. Our dataset and source code are publicly available


## Dataset /Benchmark
******
### LexGLUE: A Benchmark Dataset for
Legal Language Understanding in English
https://arxiv.org/pdf/2110.00976.pdf
**Abstract**
Laws and their interpretations, legal arguments
and agreements are typically expressed in writing, leading to the production of vast corpora of legal text. Their analysis, which is at the center of legal practice, becomes increasingly elaborate as these collections grow in size.
Natural language understanding (NLU) technologies can be a valuable tool to support legal practitioners in these endeavors. Their usefulness, however, largely depends on whether current state-of-the-art models can generalize
across various tasks in the legal domain. To answer this currently open question, we introduce the Legal General Language Understanding Evaluation (LexGLUE) benchmark, a collection of datasets for evaluating model performance across a diverse set of legal NLU tasks in a standardized way. We also provide an
evaluation and analysis of several generic and legal-oriented models demonstrating that the latter consistently offer performance improvements across multiple tasks.
**********
### FairLex: A Multilingual Benchmark for Evaluating Fairness in Legal Text Processing
https://arxiv.org/pdf/2203.07228.pdf
**Abstract**
We present a benchmark suite of four datasets for evaluating the fairness of pre-trained language models and the techniques used to fine-tune them for downstream tasks. Our benchmarks cover four jurisdictions (European Council, USA, Switzerland, and China), five languages (English, German, French, Italian and Chinese) and fairness across five attributes (gender, age, region, language, and legal area). In our experiments, we evaluate pretrained language models using several grouprobust fine-tuning techniques and show that performance group disparities are vibrant in many cases, while none of these techniques guarantee fairness, nor consistently mitigate group disparities. Furthermore, we provide a quantitative and qualitative analysis of our results, highlighting open challenges in the development of robustness methods in legal NLP.

### CUAD: An Expert-Annotated NLP Dataset for  Legal Contract Review
https://arxiv.org/pdf/2103.06268.pdf
**Abstract**
Many specialized domains remain untouched by deep learning, as large labeled datasets require expensive expert annotators. We address this bottleneck within the legal domain by introducing the Contract Understanding Atticus Dataset (CUAD), a new dataset for legal contract review. CUAD was created with dozens of legal experts from The Atticus Project and consists of over 13,000 annotations. The task is to highlight salient portions of a contract that are important for a human to review. We find that Transformer models have nascent performance, but that this performance is strongly influenced by model design and training dataset size. Despite these promising results, there is still substantial room for improvement. As one of the only large, specialized NLP benchmarks annotated by experts, CUAD can serve as a challenging research benchmark for the broader NLP community.

## Justice prédictive / Jurimétrie
### Swiss-Judgment-Prediction: A Multilingual Legal
Judgment Prediction Benchmark
https://arxiv.org/pdf/2110.00806.pdf
**Abstract**
In many jurisdictions, the excessive workload of courts leads to high delays. Suitable predictive AI models can assist legal professionals in their work, and thus enhance and speed up the process. So far, Legal Judgment Prediction (LJP) datasets have been released in English, French, and Chinese. We publicly release a multilingual (German, French, and Italian), diachronic (2000-2020) corpus of 85K cases from the Federal Supreme Court of Switzerland (FSCS). We evaluate state-of-the-art BERT-based methods including two variants of BERT that overcome the BERT input (text) length limitation (up to 512 tokens). Hierarchical BERT has the best performance (approx. 68-70% Macro-F1-Score in German and French). Furthermore, we study how several factors (canton of origin, year of publication, text length, legal area) affect performance. We release both the benchmark dataset and our code to accelerate future research and ensure reproducibility

### Dependency Learning for Legal Judgment
Prediction with a Unified Text-to-Text
Transformer
https://arxiv.org/pdf/2112.06370.pdf
**Abstract**
Given the fact of a case, Legal Judgment Prediction (LJP) involves a series of sub-tasks such as predicting violated law articles, charges and term of penalty. We propose leveraging a unified text-to-text Transformer for LJP, where the dependencies among sub-tasks can be naturally established within the auto-regressive decoder. Compared with previous works, it has three advantages: (1) it fits in the pretraining pattern of masked language models, and thereby can benefit from the semantic prompts of each sub-task rather than treating them as atomic labels, (2) it utilizes a single unified architecture, enabling full parameter sharing across all sub-tasks, and (3) it can incorporate both classification and generative sub-tasks. We show that this unified transformer, albeit pretrained on general-domain text, outperforms pretrained models tailored specifically for the legal domain. Through an extensive set of experiments, we find that the best order to capture dependencies is different from human intuitions, and the most reasonable logical order for humans can be sub-optimal for the model. We further include two more auxiliary tasks: court view generation and article content prediction, showing they can not only improve the prediction accuracy, but also provide interpretable explanations for model outputs even when an error is made. With the best configuration, our model outperforms both previous SOTA and a single-tasked version of the unified transformer by a large margin. Code and dataset are available at https://github.com/oli-yun/Dependency-LJP.

### Deconfounding Legal Judgment Prediction for European Court of Human Rights Cases Towards Better Alignment with Experts
https://arxiv.org/pdf/2210.13836.pdf
**Abstract**
This work demonstrates that Legal Judgement Prediction systems without expert-informed adjustments can be vulnerable to shallow, distracting surface signals that arise from corpus construction, case distribution, and confounding factors. To mitigate this, we use domain expertise to strategically identify statistically predictive but legally irrelevant information. We adopt adversarial training to prevent the system from relying on it. We evaluate our deconfounded models by employing interpretability techniques and comparing to expert annotations. Quantitative experiments and qualitative analysis show that our deconfounded model consistently aligns better with expert rationales than baselines trained for prediction only. We further contribute a set of reference expert annotations to the validation and testing partitions of an existing benchmark dataset of European Court of Human Rights cases.