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
- ISCAS85+EPFL Benchmark Suite from `https://github.com/jpsety/verilog_benchmark_circuits`
- MNIST dataset

### For reading only: Variants of HDC (Hyperdimensional Computing (HDC) Optimization Techniques)

##### 1. Iterative Retraining and Regenerative Training
**Concept**: Iteratively refine the class hypervectors by retraining the model on misclassified samples or regenerating the hypervectors to better represent the data.

**Implementation**:
- After the initial training, identify misclassified samples
- Update the class hypervectors by incorporating these samples with higher weights
- Helps the model adapt to challenging cases

##### 2. Adaptive Encoding
**Concept**: Use adaptive encoding techniques to better capture the structure of the data (e.g., data-driven projections instead of random projections).

**Implementation**:
- Apply Principal Component Analysis (PCA) or other dimensionality reduction techniques
- Preprocess the data before encoding into hypervectors
- Ensures most informative features are emphasized

##### 3. Hybrid Models
**Concept**: Combine HDC with other machine learning models to leverage their strengths.

**Implementation**:
- Train a lightweight neural network for feature extraction
- Use the neural network's output as input to HDC model
- Retains HDC efficiency while boosting accuracy

##### 4. Higher-Order Representations
**Concept**: Incorporate higher-order interactions between features.

**Implementation**:
- Bind groups of features together before encoding
- Use element-wise multiplication or XOR operations
- Captures feature interactions for better classification

##### 5. Dimensionality Optimization
**Concept**: Optimize hypervector dimensionality for accuracy/efficiency trade-off.

**Implementation**:
- Experiment with different dimensions (10K, 20K, etc.)
- Higher dimensions improve accuracy but increase compute cost
- Find optimal balance for specific dataset

##### 6. Error-Correcting Codes
**Concept**: Improve robustness to noise and misclassifications.

**Implementation**:
- Encode class labels using error-correcting codes
- Train model to predict these codes instead of raw labels
- Adds redundancy for better fault tolerance

##### 7. MicroHD Optimization
**Concept**: Systematic hyperparameter tuning for accuracy.

**Implementation**:
- Apply MicroHD to explore hyperparameter space
- Optimize dimensionality, encoding functions etc.
- Maintain efficiency while maximizing accuracy


