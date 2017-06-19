# Right for the Right Reasons: Training Differentiable Models by Constraining their Explanations
## Andrew Ross, Michael C. Hughes, and Finale Doshi-Velez
## Harvard
### arXiv

#### interpretability, neural networks

### Abstract

Neural networks are among the most accurate supervised
learning methods in use today. However,
their opacity makes them difficult to trust in critical
applications, especially if conditions in training may
differ from those in test. Recent work on explanations
for black-box models has produced tools (e.g.
LIME) to show the implicit rules behind predictions.
These tools can help us identify when models are
right for the wrong reasons. However, these methods
do not scale to explaining entire datasets and cannot
correct the problems they reveal. We introduce a
method for efficiently explaining and regularizing
differentiable models by examining and selectively
penalizing their input gradients. We apply these
penalties both based on expert annotation and in an
unsupervised fashion that produces multiple classi-
fiers with qualitatively different decision boundaries.
On multiple datasets, we show our approach generates
faithful explanations and models that generalize
much better when conditions differ between training
and test.

### Contributions

• We confirm empirically on several datasets that input
gradient explanations match state of the art sample-based
explanations (e.g. LIME [Ribeiro, 2016]).
• Given annotations about incorrect explanations for particular
inputs, we efficiently optimize the classifier to learn
alternate explanations (to be right for better reasons).
• When annotations are not available, we sequentially discover
classifiers with similar accuracies but qualitatively
different decision boundaries for domain experts to inspect
for validity.

### Datasets

• 20 Newsgroups
• Iris-Cancer
• Decoy MNIST