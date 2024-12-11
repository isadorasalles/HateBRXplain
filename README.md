# HateBRXplain

A Benchmark Dataset with Human-Annotated Rationales for Explainable Hate Speech Detection in Brazilian Portuguese

## Overview

Nowadays, hate speech technologies are surely relevant in Brazil. Nevertheless, the inability of these technologies to provide reasons (rationales) for their decisions is the limiting factor to their adoption since they comprise bias, which may perpetuate social inequalities when propagated at scale. This scenario highlights the urgency of proposing explainable technologies to address hate speech. However, explainable models heavily depend on data availability with human-annotated rationales, which are scarce, especially for low-resource languages. To fill this relevant gap, we introduce HateBRXplain, the first benchmark dataset for hate speech detection in Portuguese, with text span annotations capturing rationales. We evaluated our corpus using mBERT, BERTimbau, DistilBERTimbau, and PTT5 models, which outperformed the current baselines. We further assessed these models' explainability using model-agnostic explanation methods (LIME and SHAP). Results demonstrate plausible post-hoc explanations when compared to human annotations. However, the best-performing hate speech detection models failed to provide faithful rationales. 


## Annotation Process

 For annotating rationales, we focused exclusively on spans of text that indicate offensiveness. Annotators were instructed to highlight only the portions of text that supported the offensive label, resulting in rationales being provided exclusively for the 3,500 offensive comments. According to our guidelines, a rationale is defined as a set of text spans, with each span being the smallest text segment that conveys offensive meaning. Thus, a text span can be either a word or a phrase. Consequently, each comment may contain multiple text spans that constitute the rationale.

 ## Usage guide

* The data is available in the `./data` directory in both JSON and CSV formats. In each format, you will find the following information: the comment, its offensive label (0 for non-offensive and 1 for offensive), and, for offensive comments, two annotations providing rationales.

* To run the classifiers, you can find the required dependencies listed within each classifier notebook located in the `./classifiers` directory. 

* Experiments using SHAP and LIME are located in the `./explainability` directory, while the evaluation of explainability can be found in the `./metrics` directory.