
## Comparing explainers with count-based or automated metrics

<table>
<tr> <th>Paper</th> <th>Analysis</th> <th><abbr title="Simple Gradient Saliency (Simonyan et al., 2013), sometimes referred to as Vanilla Gradient">Grad</abbr></th> <th><abbr title="Integrated Gradients (Sundararajan et al., 2017)">IG</abbr></th> <th><abbr title="Other gradient-based or propagation-based explainers">Grad/Prop</abbr></th> <th><abbr title="Types of Shapley Value explainers">Shapley</abbr></th> <th><abbr title="Why Should I Trust You?: Explaining the Predictions of Any Classifier (Ribeiro et al., 2016)">LIME</abbr></th> <th><abbr title="Occlusion and Erasure-based explainers">Occl</abbr></th> <th><abbr title="Information Bottleneck">IB</abbr></th> <th><abbr title="Other NLP-specific explainers">NLP-spec.</abbr></th> </tr>

<tr>
    <td><b>Arras et al. (2016; 2017)</b> [8] [9]</td>
    <td>Word Deletion</td>
    <td></td>
    <td></td>
    <td><abbr title="Layer-Wise Relevance Propagation for Neural Networks with Local Renormalization Layers (Binder et al., 2016)">LRP</abbr></td>
</tr>

<tr>
    <td><b>LIMSSE (Pörner et al., 2018)</b> [16]</td>
    <td><abbr title="Hybrid document paradigm">Faithfulness</abbr>, <br> <abbr title="Morphosyntactic agreement paradigm">Agreement</abbr></td>
    <td>x</td>
    <td>x</td>
    <td><abbr title="Layer-Wise Relevance Propagation for Neural Networks with Local Renormalization Layers (Binder et al., 2016)">LRP</abbr>, <br> DeepLIFT</td>
    <td></td>
    <td>LIMSSE</td>
    <td><abbr title="Occlusion (Zeiler & Fergus, 2013)">Z&F</abbr>, <br> <abbr title="Omission (Kádár et al., 2017)">Omiss</abbr></td>
</tr>

<tr>
    <td><b>Nguyen (2018)</b></td>
    <td><abbr title="Switching point (inspired by Arras et al., 2016)">SwitchP</abbr>, <br> <abbr title="Area over the Perturbation Curve (Samek et al., 2017)">AOPC</abbr>, <br> <abbr title="Forward prediction / simulation (Doshi-Velez & Kim, 2017)">Forward pred.</abbr></td>
    <td>x</td>
    <td></td>
    <td><abbr title="First derivate saliency (Aubakirova & Bansal, 2016; Li et al., 2016)">1st Deriv</abbr></td>
    <td></td>
    <td>x</td>
    <td><abbr title="Omission (Kádár et al., 2017)">Omiss</abbr></td>
</tr>

<tr>
    <td><b>DiffMask (De Cao et al., 2020)</b></td>
    <td><abbr title="Kullback-Leibler and Jensen-Shannon divergences from gold-truth across test set">Divergence</abbr>, <br> Faithfulness, <br> Plausability, <br> Amortization</td>
    <td></td>
    <td>x</td>
    <td></td>
    <td></td>
    <td></td>
    <td><abbr title="Erasure exact search optima">EESO</abbr></td>
    <td><abbr title="Restricting the Flow: Information Bottlenecks for Attribution (Schulz et al., 2020)">IBA</abbr></td>
    <td><abbr title="Towards a Deep and Unified Understanding of Deep Neural Models in NLP (Guan et al., 2019)">NLPEx</abbr>, <br> DiffMask</td>
</tr>

<tr>
    <td><b>XAI Benchmark (Atanasova et al., 2020)</b></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>

<tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>

<tr>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
</tr>

</table>

**** | <abbr title="Confidence Indication via Mean Absolute Error (MAE)">Confidence</abbr>, <br> <abbr title="Rationale and dataset consistency via Spearman's ρ">Consistency</abbr>, <br> <abbr title="Human evaluation via Mean Average Precision">Human</abbr>, <br> <abbr title="FLOPs">Compute</abbr> | x | x | Input x Grad | <abbr title="Shapley Value Sampling (Castro et al., 2009)">SVS</abbr> | x | <abbr title="Occlusion (Zeiler & Fergus, 2013)">Z&F</abbr>
**Archipelago (Tsang et al., 2020)** | <abbr title="Pearson's correlation between estimated phrase attributions and labels from SST; Word correlation to coefficients of global BOW linear model (Section 5.3)">Correlation</abbr> | | x, <br> <abbr title="Integrated Hessians (Janizek et al., 2020)">IH</abbr> | | <abbr title="Shapley Interaction Index (Grabisch & Roubens, 1999)">SI</abbr>, <br> <abbr title="Shapley Taylor Interaction Index (Sundararajan et al., 2019)">STI</abbr> | <abbr title="Model-Agnostic Hierarchical Explanations (Tsang et al., 2018)">MAHE</abbr> | <abbr title="Sampling Occlusion (Jin et al., 2020)">SOC</abbr> | | <abbr title="Sampling Contextual Decomposition (Jin et al., 2020)">SCD</abbr>
**Nguyen & Rodriǵuez Martínez (2020)** | Complexity, <br> Monotonicity, <br> <abbr title="Effective Complexity">Eff. Complex.</abbr>, <br> <abbr title="Non-Sensitivity">Non-Sensitiv.</abbr>, <br> Perturbation | x | x | Input x Grad
**VMASK (Chen & Ji, 2020)** ★ / **GMASK (Chen et al., 2021)** | <abbr title="Nguyen (2018)">AOPC</abbr>, <br> <abbr title="Post-hoc Accuracy (Chen et al., 2018)">Post-h Acc</abbr>, <br> <abbr title="Degradation test (Ancona et al., 2017; Schulz et al., 2020). Only used in Chen et al. (2021)">Degradation</abbr>* | | | | | <abbr title="Only used in Chen et al. (2021)">LIME</abbr> | | <abbr title="Restricting the Flow: Information Bottlenecks for Attribution (Schulz et al., 2020)">IBA</abbr> | L2X, <br> VMASK, <br> <abbr title="Variation of GMASK only used in Chen et al. (2021)">IMASK</abbr>, <br> <abbr title="Only used in Chen et al. (2021)">GMASK</abbr>
**Court of XAI (Neely et al., 2021)** | <abbr title="Agreement via Kendall's τ">Correlation</abbr> | | x | DeepLIFT | <abbr title="Grad-SHAP, Deep-SHAP (both Lundberg & Lee, 2017)">SHAP</abbr> | x
**Bodria et al. (2021)** | Deletion, <br> Insertion | | x | Input x Grad, <br> DeepLIFT | | LIME
**Ding & Koehn (2021)** | <abbr title="Agreement test following Pörner et al. (2018)">Plausability</abbr>, <br> <abbr title="Model Consistency test & Input Consistency test (Jacovi & Goldberg, 2020)">Faithfulness</abbr>  | x | x | <abbr title="SmoothGrad (Smilkov et al., 2017)">SmoothGr</abbr>
Yin et al. (2021) |
Hase et al. (2021) |
Kokhlikyan et al. (2021) |
Zafar et al. (2021) |
Sinha et al. (2021) | | | | | | | | | -


### Benchmark papers
Nguyen, An-phi and María Rodríguez Martínez. “[On quantitative aspects of model interpretability.](https://api.semanticscholar.org/CorpusID:220525899)” ArXiv abs/2007.07584 (2020).  

Nguyen, Dong. “[Comparing Automatic and Human Evaluation of Local Explanations for Text Classification.](https://api.semanticscholar.org/CorpusID:44130060)” NAACL (2018).  

Tsang, Michael, Sirisha Rambhatla and Yan Liu. “[How does this interaction affect me? Interpretable attribution for feature interactions.](https://api.semanticscholar.org/CorpusID:219955933)” NeurIPS (2020).  


### Analysis methods

Ancona, Marco, Enea Ceolini, A. Cengiz Öztireli and Markus H. Gross. “[A unified view of gradient-based attribution methods for Deep Neural Networks.](https://api.semanticscholar.org/CorpusID:1809062)” ICLR (2018).  

Chen, Jianbo, Le Song, Martin J. Wainwright and Michael I. Jordan. “[Learning to Explain: An Information-Theoretic Perspective on Model Interpretation.](https://api.semanticscholar.org/CorpusID:3500834)” ICML (2018).  

Jacovi, Alon and Yoav Goldberg. “[Towards Faithfully Interpretable NLP Systems: How Should We Define and Evaluate Faithfulness?](https://api.semanticscholar.org/CorpusID:215416110)” ACL (2020).  

Samek, Wojciech, Alexander Binder, Grégoire Montavon, Sebastian Lapuschkin and Klaus-Robert Müller. “[Evaluating the Visualization of What a Deep Neural Network Has Learned.](https://api.semanticscholar.org/CorpusID:7689122)” IEEE Transactions on Neural Networks and Learning Systems 28 (2017): 2660-2673.  


### Explainability methods

Aubakirova, Malika and Mohit Bansal. “[Interpreting Neural Networks to Improve Politeness Comprehension.](https://api.semanticscholar.org/CorpusID:12245103)” EMNLP (2016).  

Binder, Alexander, Grégoire Montavon, Sebastian Lapuschkin, Klaus-Robert Müller and Wojciech Samek. “[Layer-Wise Relevance Propagation for Neural Networks with Local Renormalization Layers.](https://api.semanticscholar.org/CorpusID:15207861)” ICANN (2016).  

Castro, Javier, Daniel Gómez and Juan Tejada. “[Polynomial calculation of the Shapley value based on sampling.](https://api.semanticscholar.org/CorpusID:42828306)” Comput. Oper. Res. 36 (2009): 1726-1730.  

Grabisch, Michel and Marc Roubens. “[An axiomatic approach to the concept of interaction among players in cooperative games.](https://api.semanticscholar.org/CorpusID:18033890)” International Journal of Game Theory 28 (1999): 547-565.  

Guan, Chaoyu, Xiting Wang, Quanshi Zhang, Runjin Chen, Di He and Xing Xie. “[Towards a Deep and Unified Understanding of Deep Neural Models in NLP.](https://api.semanticscholar.org/CorpusID:174800317)” ICML (2019).  

Janizek, Joseph D., Pascal Sturmfels and Su-In Lee. “[Explaining Explanations: Axiomatic Feature Interactions for Deep Networks.](https://api.semanticscholar.org/CorpusID:211075890)” ArXiv abs/2002.04138 (2020).  

Jin, Xisen, Junyi Du, Zhongyu Wei, X. Xue and Xiang Ren. “[Towards Hierarchical Importance Attribution: Explaining Compositional Semantics for Neural Sequence Models.](https://api.semanticscholar.org/CorpusID:208006294)” ICLR (2020).  

Kádár, Ákos, Grzegorz Chrupała and A. Alishahi. “[Representation of Linguistic Form and Function in Recurrent Neural Networks.](https://api.semanticscholar.org/CorpusID:611341)” Computational Linguistics 43 (2017): 761-780.  

Lundberg, Scott M. and Su-In Lee. “[A Unified Approach to Interpreting Model Predictions.](https://api.semanticscholar.org/CorpusID:21889700)” NIPS (2017).  

Ribeiro, Marco Tulio, Sameer Singh and Carlos Guestrin. “["Why Should I Trust You?": Explaining the Predictions of Any Classifier.](https://api.semanticscholar.org/CorpusID:13029170)” Proceedings of the 22nd ACM SIGKDD International Conference on Knowledge Discovery and Data Mining (2016).  

Schulz, Karl, Leon Sixt, Federico Tombari and Tim Landgraf. “[Restricting the Flow: Information Bottlenecks for Attribution.](https://api.semanticscholar.org/CorpusID:209532057)” ICLR (2020).

Simonyan, Karen, Andrea Vedaldi and Andrew Zisserman. “[Deep Inside Convolutional Networks: Visualising Image Classification Models and Saliency Maps.](https://api.semanticscholar.org/CorpusID:1450294)” ICLR (2014).  

Smilkov, Daniel, Nikhil Thorat, Been Kim, Fernanda B. Viégas and Martin Wattenberg. “[SmoothGrad: removing noise by adding noise.](https://api.semanticscholar.org/CorpusID:11695878)” CoRR, abs/1706.03825 (2017).  

Sundararajan, Mukund, Ankur Taly and Qiqi Yan. “[Axiomatic Attribution for Deep Networks.](https://api.semanticscholar.org/CorpusID:16747630)” ICML (2017).  

Sundararajan, Mukund, Kedar Dhamdhere and Ashish Agarwal. “[The Shapley Taylor Interaction Index.](https://api.semanticscholar.org/CorpusID:211069271)” ICML (2020).

Tsang, Michael, Youbang Sun, Dongxu Ren and Yan Liu. “[Can I trust you more? Model-Agnostic Hierarchical Explanations.](https://api.semanticscholar.org/CorpusID:54477728)” ArXiv abs/1812.04801 (2018).

Zeiler, Matthew D. and Rob Fergus. “[Visualizing and Understanding Convolutional Networks.](https://api.semanticscholar.org/CorpusID:3960646)” ECCV (2014).  

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
<abbr title="Comparing Automatic and Human Evaluation of Local Explanations for Text Classification">Nguyen (2018)</abbr> | Confidence, Accuracy
Hase & Bansal (2020) |  
<abbr title="On the Interaction of Belief Bias and Explanations">González et al. (2021)</abbr> | Grad, <br> IG  

---

## Incorporating feature attributions into model training

![](https://d3i71xaburhd42.cloudfront.net/9d4a144cc6b80d175164b1d2a969ad356743e1f7/6-Table3-1.png)
<p style="text-align: center;">from Chen & Ji (2020)</p>  

* Zero-shot Sequence Labeling for Transformer-based Sentence Classifiers (Bujel et al., 2021) ★  

### Improving the prediction performance
* Incorporating Priors with Feature Attribution on Text Classification (Liu & Avci, 2019)  
* Evaluating Explanations: How much do explanations from the teacher aid students? (Pruthi et al., 2020)  
* DiffMask (De Cao et al., 2020) : Erasure search as learning masks (Section 3.2)

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
**IMDb** | VMASK (Chen & Ji, 2020) ★, <br> XAI Benchmark (Atanasova et al., 2020), <br> Court of XAI (Neely et al., 2021), <br> Bodria et al. (2021)
**20Newsgroups** | Arras et al. (2016), <br> LIMSSE (Pörner et al., 2018), <br> Nguyen (2018)
**SST** | Arras et al. (2017), <br> DiffMask (De Cao et al., 2020), <br> VMASK (Chen & Ji, 2020) ★, <br> Tsang et al. (2020), <br> Bodria et al. (2021)
**Yelp** | LIMSSE (Pörner et al., 2018), <br> VMASK (Chen & Ji, 2020) ★, <br> Bodria et al. (2021)
**SST-2** | VMASK (Chen & Ji, 2020) ★, <br> Court of XAI (Neely et al., 2021)
**e-SNLI** | GMASK (Chen et al., 2021), <br> XAI Benchmark (Atanasova et al., 2020)
**QQP** | GMASK (Chen et al., 2021), <br> Court of XAI (Neely et al., 2021)
**Movie Reviews** | Nguyen (2018)
**AG News** | VMASK (Chen & Ji, 2020) ★
**TREC** | VMASK (Chen & Ji, 2020) ★
**Subj** | VMASK (Chen & Ji, 2020) ★
**SNLI** | Court of XAI (Neely et al., 2021)
**MNLI** | Court of XAI (Neely et al., 2021)
**Quora** | GMASK (Chen et al., 2021)
**MRPC** | GMASK (Chen et al., 2021)
**TSE** | XAI Benchmark (Atanasova et al., 2020)
**SQuAD** | DiffMask (De Cao et al., 2020
**PTB** | Ding & Koehn (2021)
**Syneval** | Ding & Koehn (2021)
**CoNLL** | Ding & Koehn (2021)
**Winobias** | Ding & Koehn (2021)
