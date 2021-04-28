# AutoLabels-PublicData-CXR-PA
Labels (with human experts' quality) for 5 categories on three public CXR datasets: CheXpert [1], MIMIC [2], and NIH [3]. 


## Purpose
Chest radiography (CXR) is one of the most widely used medical imaging modalities for screening and diagnosis. CheXpert (images, n=224,316), MIMIC (n=377,110) and NIH (n=108,948) are well-known as large, labeled, public datasets which can help develop deep learning methods to achieve expert-level performance. Unfortunately, because there does not exist a common labeler that can extract observations from radiology reports of various institutions, each label can have slightly different definitions between two datasets. This can be a critical issue in researchers' attempts to develop more generalized AI models by combining datasets as much as possible. For three public datasets, therefore, we share five labels that contain both human experts' quality and the same definitions, extracted by our image-based automatic annotation methods.


## Method
We trained the explainable AI model on CXR (PA view) to predict a probability and to estimate the harmonic similarity index (by combining a patch-similarity and a confidence) based on our institution’s train set for each category. The Image-based automatic annotation method consisted of two steps: (1) the explainable AI model and (2) mode selection. The mode selection was developed to mimic the process by which humans (~ AI model) recall and revise their experiences and memories (~ train sets) upon receipt of additional information (~ public dataset); that is, the process by which humans learn. High-quality labels including positive (Pos), negative (Neg), and unlabeled (UL) can be decided systematically and automatically by a single threshold (TH) which can control the tradeoff between label quality and capturing rate.


## Lebels
(Our 5 labels' definition)


## Results
Insert the final table!

* CheXpert: CSV filename in this repository
* MIMIC: CSV filename in this repository
* NIH: CSV filename in this repository


## Reference
[1] Irvin, J., Rajpurkar, P., Ko, M., Yu, Y., Ciurea-Ilcus, S., Chute, C., Marklund, H., Haghgoo, B., Ball, R., Shpanskaya, K. and Seekins, J. Chexpert: A large chest radiograph dataset with uncertainty labels and expert comparison. In Proceedings of the AAAI Conference on Artificial Intelligence 33, 590-597 (2019).

[2] Johnson, A.E., Pollard, T.J., Greenbaum, N.R., Lungren, M.P., Deng, C.Y., Peng, Y., Lu, Z., Mark, R.G., Berkowitz, S.J. and Horng, S. MIMIC-CXR-JPG, a large publicly available database of labeled chest radiographs. Preprint at http://arXiv:1901.07042 (2019).

[3] Wang, X., Peng, Y., Lu, L., Lu, Z., Bagheri, M., & Summers, R. M. Chestx-ray8: Hospital-scale chest x-ray database and benchmarks on weakly-supervised classification and localization of common thorax diseases. In Proceedings of the IEEE conference on computer vision and pattern recognition, 2097-2106 (2017).
