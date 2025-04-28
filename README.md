## Membership Inference Attack on Hyperdimensional Computing

Membership Inference Attacks (MIAs) pose a significant threat to the privacy of machine learning models by allowing adversaries to determine whether a specific data sample was part of a model’s training dataset. While extensive literature has explored MIAs in traditional machine learning models such as neural networks and decision trees, little attention has been given to their applicability in the emerging paradigm of Hyperdimensional Computing (HDC). This work pioneers the systematic exploration of MIAs in HDC models, which are increasingly being deployed in domains ranging from image classification to hardware security. We evaluate the susceptibility of HDC to MIAs using two diverse datasets: the MNIST image dataset and digital circuit netlists from ISCAS85 and ITC-99 benchmarks. We leverage multiple similarity-based metrics—Cosine, Euclidean, and Hamming distance—to distinguish training members from non-members. Our results demonstrate that the direct aggregation and transparent structure of HDC models make them more vulnerable to MIA compared to traditional ML models, which often abstract and obscure individual training contributions. 

#### The code structure is as follows:
- The baseline HDC architecure for the `MNIST` dataset is given in `HDC_Membership_Inference_Attack_MNIST.ipynb`.
- Then the seven variants of the HDC architecture follows it. The details of those variants are given in the bottom of this document.
- The baseline HDC architecure for the `ISCAS and EPFL Combinational benchmark` dataset is given in `HDC_Membership_Inference_Attack_Circuits.ipynb`.
- Then the seven variants of the HDC architecture follows it.
- Membership Inference Attack for the MNIST using fully connected neural network (FCN) and decision tree is given in `MNIST_Membership_Inference_Attack_Other_MLs`.
- Membership Inference Attack for the ISCAS85+EPFL circuit using graph convolution neural network (GCN) is given in `GNN_ISCAS85+EPFL_Membership_Inference_Attack.ipynb`. Similarly, that using decision tree is given in `Membership_Inference_DT_Circuits.ipynb`. 

To reproduce the outcomes given for ISCAS85+EPFL benchmark, please run the parser script given in `GNN_ISCAS85+EPFL_Membership_Inference_Attack.ipynb`. This will create the csv file. Once the csv file is created then the scripts in `HDC_Membership_Inference_Attack_Circuits.ipynb` and `Membership_Inference_DT_Circuits.ipynb` could run. 

#### Dependency:
- DGL
- Keras
- Pytorch
- Sklearn

#### Variants of HDC
1. Iterative Retraining and Regenerative Training
Concept: Iteratively refine the class hypervectors by retraining the model on misclassified samples or regenerating the hypervectors to better represent the data.

Implementation: After the initial training, identify misclassified samples and update the class hypervectors by incorporating these samples with higher weights. This can help the model adapt to challenging cases.

2. Adaptive Encoding
Concept: Use adaptive encoding techniques to better capture the structure of the data. For example, instead of random projections, use data-driven projections that preserve important features.

Implementation: Apply Principal Component Analysis (PCA) or other dimensionality reduction techniques to preprocess the data before encoding it into hypervectors. This ensures that the most informative features are emphasized.

3. Hybrid Models
Concept: Combine HDC with other machine learning models to leverage their strengths. For instance, use a neural network to preprocess the data and then encode the output into hypervectors.

Implementation: Train a lightweight neural network to extract features from the data, and then use these features as input to the HDC model. This hybrid approach can significantly boost accuracy while retaining the efficiency of HDC.

4. Higher-Order Representations
Concept: Incorporate higher-order interactions between features by binding multiple features together before encoding.

Implementation: Instead of encoding each feature independently, bind groups of features together using element-wise multiplication or XOR operations. This captures interactions between features and can improve classification performance.

5. Dimensionality Optimization
Concept: Optimize the dimensionality of the hypervectors to balance accuracy and computational efficiency.

Implementation: Experiment with different dimensionalities (e.g., 10,000, 20,000, or higher) to find the optimal trade-off for your dataset. Higher dimensions often improve accuracy but increase computational cost.

6. Error-Correcting Codes
Concept: Use error-correcting codes to make the model more robust to noise and misclassifications.

Implementation: Encode the class labels using error-correcting codes and train the model to predict these codes instead of the raw labels. This adds redundancy and improves robustness.

7. MicroHD Optimization
Concept: Use accuracy-driven optimization techniques like MicroHD to iteratively tune hyperparameters and encoding functions.

Implementation: Apply MicroHD to systematically explore the hyperparameter space (e.g., dimensionality, encoding functions) and optimize the model for accuracy while maintaining efficiency.


