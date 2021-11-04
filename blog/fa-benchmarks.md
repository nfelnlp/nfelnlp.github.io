v0.1 (2021-11-04) : This is a work-in-progress document. Links and references will be added and the tables will be filled very soon.

# A Topography of Feature Attribution Benchmarks

My first blog post accompanies my EMNLP 2021-accepted paper "Thermostat: A Large Collection of NLP Model Explanations and Analysis Tools (Feldhus et al., 2021)" and dives deeper into **benchmarks of feature attribution methods for NLP**.


#### A few notes before we start

* Papers with no apparent experiments on NLP data are strictly excluded, because the extent of this survey would be too large.
* The ★ symbol marks papers that I have _not_ referenced in the version which is currently available to the public (v1: 2021-08-31).
* Instead of churning out too many updates of my paper via arXiv directly, I will instead use this and upcoming related blog posts as slightly more informal documents that can be updated much more often.

---

## Prerequisites

[Word Embeddings](https://lena-voita.github.io/nlp_course/word_embeddings.html) and [Text Classification with Neural Networks](https://lena-voita.github.io/nlp_course/text_classification.html)

## Motivation

### Opacity of deep neural networks in NLP
* Visualizing and Understanding Recurrent Networks (Karpathy et al., 2015)
* Understanding Neural Networks through Representation Erasure (Li et al., 2016)

### Growing importance of explainable NLP
* Analysis Methods in Neural Language Processing: A Survey (Belinkov & Glass, 2018)
* Interpreting Predictions of NLP Models (Wallace et al., 2020)
* Post-hoc Interpretability for Neural NLP: A Survey (Madsen et al., 2021) ★

---

## Analyzing different types of models
Papers with more than one type of model architecture.

Paper | CNN | LSTM/RNN | Transformers
--- | --- | --- | ---
<abbr title="Explaining Predictions of Non-Linear Classifiers in NLP (Arras et al., 2016); Explaining Recurrent Neural Network Predictions in Sentiment Analysis (Arras et al., 2017)">Arras et al. (2016; 2017)</abbr> | <abbr title="Convolutional Neural Networks for Sentence Classification (Kim, 2014)">Kim</abbr> | <abbr title="one hidden-layer bi-directional LSTM (Hochreiter & Schmidhuber, 1997)">LSTM</abbr>
<abbr title="Evaluating neural network explanation methods using hybrid documents and morphosyntactic agreement">LIMSSE (Pörner et al., 2018)</abbr> | CNN | GRU, <br> QGRU, <br> LSTM, <br> QLSTM
<abbr title="How Do Decisions Emerge across Layers in Neural Models? Interpretation with Differentiable Masking">DiffMask (De Cao et al., 2020)</abbr> | | GRU | BERT
<abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr> | <abbr title="Layers: GloVe embeddings (Pennington et al., 2014) + Conv + Max-Pool + Linear">GloVe</abbr> | <abbr title="Layers: GloVe embeddings (Pennington et al., 2014) + multiple bidirectional recurrent + 3x linear + Dropout">GloVe</abbr> | BERT
<abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★ | <abbr title="Convolutional Neural Networks for Sentence Classification (Kim, 2014)">Kim</abbr> | <abbr title="one hidden-layer bi-directional LSTM (Hochreiter & Schmidhuber, 1997)">LSTM</abbr> <br> + <abbr title="Word2Vec (Mikolov et al., 2013)">W2V</abbr> | BERT
<abbr title="Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks">GMASK (Chen et al., 2021)</abbr> | | <abbr title="A Decomposable Attention Model for Natural Language Inference (Parikh et al., 2016)">DAttn</abbr> | BERT
<abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr> | | BiLSTM | DistilBERT

---

## Comparing explainers with count-based or automated metrics
Paper | Analysis | <abbr title="Simple Gradient Saliency (Simonyan et al., 2013), sometimes referred to as Vanilla Gradient as well">Grad</abbr> | <abbr title="Integrated Gradients (Sundararajan et al., 2017)">IG</abbr> | <abbr title="Other gradient-based or propagation-based explainers">Grad/Prop</abbr> | <abbr title="Types of Shapley Value explainers">Shapley</abbr> | <abbr title="Why Should I Trust You?: Explaining the Predictions of Any Classifier (Ribeiro et al., 2016)">LIME</abbr> | <abbr title="Occlusion (Zeiler & Fergus, 2013)">Occl</abbr> | <abbr title="Information Bottleneck">IB</abbr> | <abbr title="Other NLP-specific explainers">NLP-spec.</abbr>
--- | --- | --- | --- | --- | --- | --- | --- | --- | ---
<abbr title="Explaining Predictions of Non-Linear Classifiers in NLP (Arras et al., 2016); Explaining Recurrent Neural Network Predictions in Sentiment Analysis (Arras et al., 2017)">Arras et al. (2016; 2017)</abbr> | Word Deletion | | | <abbr title="Layer-Wise Relevance Propagation for Neural Networks with Local Renormalization Layers (Binder et al., 2016)">LRP</abbr>
<abbr title="Evaluating neural network explanation methods using hybrid documents and morphosyntactic agreement">LIMSSE (Pörner et al., 2018)</abbr> | <abbr title="Hybrid document paradigm">Faithfulness</abbr>, <br> <abbr title="Morphosyntactic agreement paradigm">Agreement</abbr> | x | x | <abbr title="Layer-Wise Relevance Propagation for Neural Networks with Local Renormalization Layers (Binder et al., 2016)">LRP</abbr>, <br> DeepLIFT | | LIMSSE | Z&F, <br> <abbr title="Omission (Kádár et al., 2017)">Omiss</abbr>
<abbr title="Comparing Automatic and Human Evaluation of Local Explanations for Text Classification">Nguyen (2018)</abbr> | Human | x | | <abbr title="First derivate saliency (Aubakirova & Bansal, 2016; Li et al., 2016)">1st Deriv</abbr> | | x | <abbr title="Omission (Kádár et al., 2017)">Omiss</abbr>
<abbr title="How Do Decisions Emerge across Layers in Neural Models? Interpretation with Differentiable Masking">DiffMask (De Cao et al., 2020)</abbr> | | | x | | | | <abbr title="Erasure exact search optima">EESO</abbr> | <abbr title="Restricting the Flow: Information Bottlenecks for Attribution (Schulz et al., 2020)">IBA</abbr> | <abbr title="Towards a Deep and Unified Understanding of Deep Neural Models in NLP (Guan et al., 2019)">NLPEx</abbr>, <br> DiffMask
<abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr> | <abbr title="Confidence Indication via Mean Absolute Error (MAE)">Confidence</abbr>, <br> <abbr title="Rationale and dataset consistency via Spearman's ρ">Consistency</abbr>, <br> <abbr title="Human evaluation via Mean Average Precision">Human</abbr>, <br> <abbr title="FLOPs">Compute</abbr> | x | x | Input x Grad | <abbr title="Shapley Value Sampling (Castro et al., 2009)">SVS</abbr> | x | x
Tsang et al. (2020) |
Nguyen & Martínez (2020) |
<abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers (Chen & Ji, 2020) ★; Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks (Chen et al., 2021)">VMASK / GMASK</abbr> | <abbr title="Nguyen (2018)">AOPC</abbr>, <br> <abbr title="Post-hoc Accuracy (Chen et al., 2018)">Post-h Acc</abbr>, <br> <abbr title="Degradation test (Ancona et al., 2017; Schulz et al., 2020). Only used in Chen et al. (2021)">Degradation</abbr>* | | | | | <abbr title="Only used in Chen et al. (2021)">LIME</abbr> | | <abbr title="Restricting the Flow: Information Bottlenecks for Attribution (Schulz et al., 2020)">IBA</abbr> | L2X, <br> VMASK, <br> <abbr title="Only used in Chen et al. (2021)">IMASK</abbr>
<abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr> | <abbr title="Agreement via Kendall's τ">Correlation</abbr> | | x | DeepLIFT | Grad-SHAP, <br> Deep-SHAP | x
Bodria et al. (2021)
Ding & Koehn (2021)
Yin et al. (2021)
Hase et al. (2021)
Kokhlikyan et al. (2021)
Zafar et al. (2021)
Sinha et al. (2021)

---

## Human evaluation of explainers

Paper | Details
--- | ---
Crowdsourcing Evaluations of Classifier Interpretability (Hutton et al., 2012) ★ |
<abbr title="Explaining a black-box using Deep Variational Information Bottleneck Approach">VIBI (Bang et al., 2019)</abbr> ★ |
<abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr> | Used only datasets that already provide human annotations (rationales)
Lertvittayakumjorn & Toni (2019) |

### Human forward prediction and Simulatability

Paper | Details
--- | ---
<abbr title="Comparing Automatic and Human Evaluation of Local Explanations for Text Classification">Nguyen (2018)</abbr> |
Hase & Bansal (2020) |
<abbr title="On the Interaction of Belief Bias and Explanations">González et al. (2021)</abbr> | Grad, <br> IG

---

![](https://d3i71xaburhd42.cloudfront.net/9d4a144cc6b80d175164b1d2a969ad356743e1f7/6-Table3-1.png)
<p style="text-align: center;">from Chen & Ji (2020)</sup>

## Incorporating feature attributions into model training
* Zero-shot Sequence Labeling for Transformer-based Sentence Classifiers (Bujel et al., 2021) ★

### Improving the prediction performance
* Incorporating Priors with Feature Attribution on Text Classification (Liu & Avci, 2019)
* Evaluating Explanations: How much do explanations from the teacher aid students? (Pruthi et al., 2020)

### Improving the faithfulness
* <abbr title="Right for the Right Reasons: Training Differentiable Models by Constraining their Explanations">Right for the Right Reasons (Ross et al., 2017)</abbr>
* <abbr title="Enjoy the Salience: Towards Better Transformer-based Faithful Explanations with Word Salience">SALOSS (Chrysostomou & Aletras, 2021)</abbr> ★

### Improving the interpretability
* Improving the Interpretability of Neural Sentiment Classifiers via Data Augmentation (Chen & Ji, 2019) ★
    * aligning with human judgment
* Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers (Chen & Ji, 2020) ★

---

## Dataset coverage

Wiegreffe & Marasović (2021) compiled a great survey of human rationale datasets.
The following table accumulates the papers that I mentioned in this blog post in a previous section.

Dataset | Papers
--- | ---
<abbr title="IMDb Large Movie Review Dataset from 'Learning Word Vectors for Sentiment Analysis' (Maas et al., 2011)">IMDb</abbr> | <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★, <br> <abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr>, <br> <abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr>
20Newsgroups | <abbr title="Explaining Predictions of Non-Linear Classifiers in NLP">Arras et al. (2016)</abbr>, <br> <abbr title="Evaluating neural network explanation methods using hybrid documents and morphosyntactic agreement">LIMSSE (Pörner et al., 2018)</abbr>, <br> <abbr title="Comparing Automatic and Human Evaluation of Local Explanations for Text Classification">Nguyen (2018)</abbr>
<abbr title="Stanford Sentiment Treebank (Socher et al., 2013)">SST</abbr> | <abbr title="Explaining Recurrent Neural Network Predictions in Sentiment Analysis (Arras et al., 2017)">Arras et al. (2017)</abbr>, <br> <abbr title="How Do Decisions Emerge across Layers in Neural Models? Interpretation with Differentiable Masking">DiffMask (De Cao et al., 2020)</abbr>, <br> <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★
<abbr title="Zaidan et al. (2007)">Movie Reviews</abbr> | <abbr title="Comparing Automatic and Human Evaluation of Local Explanations for Text Classification">Nguyen (2018)</abbr>
SST-2 | <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★, <br> <abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr>
Yelp | <abbr title="Evaluating neural network explanation methods using hybrid documents and morphosyntactic agreement">LIMSSE (Pörner et al., 2018)</abbr>, <br> <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★
AG News | <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★
TREC | <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★
Subj | <abbr title="Learning Variational Word Masks to Improve the Interpretability of Neural Text Classifiers">VMASK (Chen & Ji, 2020)</abbr> ★
SNLI | <abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr>
e-SNLI | <abbr title="Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks">GMASK (Chen et al., 2021)</abbr>, <br> <abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr>
MNLI | <abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr>
Quora | <abbr title="Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks">GMASK (Chen et al., 2021)</abbr>
QQP | <abbr title="Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks">GMASK (Chen et al., 2021)</abbr>, <br> <abbr title="Order in the Court: Explainable AI Methods Prone to Disagreement">Court of XAI (Neely et al., 2021)</abbr>
MRPC | <abbr title="Explaining Neural Network Predictions on Sentence Pairs via Learning Word-Group Masks">GMASK (Chen et al., 2021)</abbr>
TSE | <abbr title="A Diagnostic Study of Explainability Techniques for Text Classification">XAI Benchmark (Atanasova et al., 2020)</abbr>
SQuAD | <abbr title="How Do Decisions Emerge across Layers in Neural Models? Interpretation with Differentiable Masking">DiffMask (De Cao et al., 2020)</abbr>
