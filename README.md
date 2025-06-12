## Membership Inference Attack on Hyperdimensional Computing for Circuits

Membership Inference Attacks (MIAs) pose a significant threat to the privacy of machine learning models by allowing adversaries to determine whether a specific data sample was part of a model’s training dataset. While extensive literature has explored MIAs in traditional machine learning models such as neural networks and decision trees, little attention has been given to their applicability in the emerging paradigm of Hyperdimensional Computing (HDC). This work pioneers the systematic exploration of MIAs in HDC models, which are increasingly being deployed in domains ranging from image classification to hardware security. We evaluate the susceptibility of HDC to MIAs using two diverse datasets: the MNIST image dataset and digital circuit netlists from ISCAS85 and ITC-99 benchmarks. We leverage multiple similarity-based metrics—Cosine, Euclidean, and Hamming distance—to distinguish training members from non-members. Our results demonstrate that the direct aggregation and transparent structure of HDC models make them more vulnerable to MIA compared to traditional ML models, which often abstract and obscure individual training contributions. 

#### The code structure is as follows:
- The baseline HDC architecure for the `MNIST` dataset is given in `HDC_Membership_Inference_Attack_MNIST.ipynb`.
- Then the seven variants of the HDC architecture follows it. The details of those variants are given in the bottom of this document.
- The baseline HDC architecure for the `ISCAS and EPFL Combinational benchmark` dataset is given in `HDC_Membership_Inference_Attack_Circuits.ipynb`.
- Then the seven variants of the HDC architecture follows it.
- Membership Inference Attack for the MNIST using fully connected neural network (FCN) and decision tree is given in `MNIST_Membership_Inference_Attack_Other_MLs`.
- Membership Inference Attack for the ISCAS85+EPFL circuit using graph convolution neural network (GCN) is given in `GNN_ISCAS85+EPFL_Membership_Inference_Attack.ipynb`. Similarly, that using decision tree is given in `Membership_Inference_DT_Circuits.ipynb`. 

To reproduce the outcomes given for ISCAS85+EPFL benchmark, please run the parser script given in `GNN_ISCAS85+EPFL_Membership_Inference_Attack.ipynb`. This will create the csv file. Once the csv file is created then the scripts in `HDC_Membership_Inference_Attack_Circuits.ipynb` and `Membership_Inference_DT_Circuits.ipynb` could run. 

#### Dependencies:
- DGL
- Keras
- Pytorch
- Sklearn
- ISCAS85+EPFL Benchmark Suite from `https://github.com/jpsety/verilog_benchmark_circuits`
- MNIST dataset

### For reading only: Prior-arts Comparision

| Study | Target Model(s) | Key Contributions |
|-------|-----------------|-------------------|
| [Shokri et al. (2017)](#shokri2017membership) | NNs | Pioneered the shadow model approach for MIAs in deep learning systems |
| [Hu et al. (2021)](#hu2021membership) | NNs, DTs, SVMs | Established a taxonomy of MIA techniques and defensive countermeasures |
| [Nasr et al. (2018)](#nasr2018machine) | NNs | Developed adversarial regularization methods for MIA mitigation |
| [Wu et al. (2025)](#wu2025membership) | Large Language Models | Characterized privacy risks in transformer-based architectures |
| [Zhang et al. (2024)](#zhang2024survey) | DTs, SVMs | Analyzed vulnerability patterns in classical ML algorithms |
| **Ours** | **Hyperdimensional Computing** | First comprehensive MIA analysis of HDC models with architectural defenses |

MIAs have been thoroughly investigated across conventional ML paradigms, including NNs, DTs, and SVMs. As evidenced in the table above, existing literature has focused mainly on parametric models, leaving emerging computing paradigms such as HDC unexplored. To the best of our knowledge, our work bridges this critical gap by presenting the first systematic study of MIAs on HDC models, while simultaneously analyzing architectural variants and proposing targeted defenses.

### References

<a id="shokri2017membership"></a>
**Shokri, R., Stronati, M., Song, C., & Shmatikov, V. (2017)**  
"Membership inference attacks against machine learning models"  
*2017 IEEE Symposium on Security and Privacy (SP)*, 3-18. IEEE.

<a id="hu2021membership"></a>
**Hu, H., Salcic, Z., Sun, L., et al. (2021)**  
"Membership inference attacks on machine learning: A survey"  
*ACM Computing Surveys (CSUR)*, 54(11s), 1-37.

<a id="nasr2018machine"></a>
**Nasr, M., Shokri, R., & Houmansadr, A. (2018)**  
"Machine learning with membership privacy using adversarial regularization"  
*Proceedings of the 2018 ACM SIGSAC Conference on Computer and Communications Security*, 634-646.

<a id="wu2025membership"></a>
**Wu, H., & Cao, Y. (2025)**  
"Membership Inference Attacks on Large-Scale Models: A Survey"  
*arXiv preprint arXiv:2503.19338*

<a id="zhang2024survey"></a>
**Zhang, M., Ren, Z., Wang, Z., et al. (2024)**  
"A Survey on Membership Inference Attacks and Defenses in Machine Learning"  
*Journal of Information and Intelligence*, 2(5), 404-454. Elsevier.



