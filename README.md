# AutoLabels-PublicData-CXR-PA
Labels (with human experts' quality) for 5 categories on three public CXR datasets: CheXpert [1], MIMIC [2], and NIH [3]. 


## Purpose
CheXpert, MIMIC, and NIH are large open access CXR datasets for widespread AI development. Unfortunately, the accuracy of their provided labels is unknown and may vary between datasets. We built and tested an explainable model for automated CXR annotation which leverages atlas creation/prediction-basis retrieval modules for high-quality labeling at a user selected performance level.


## Method
We developed our model from 241,723 frontal CXR images (2015-2019) trained on 20 features, with 3-6 expert readers as ground truth. The model outputs a probability estimate of input-image similarity for each of 5 pooled-feature categories; cardiomegaly, atelectasis, edema, pneumonia, and pleural effusion. The system, which consists of an explainable AI model (Fig A) and an auto-annotation algorithm (Fig B), mimics human thinking as it associates degree of similarity between novel input-images and its “memory” of stored images (i.e., atlas of important patches from the training sets). We tested model performance for a random subset of images from the public datasets at two different probability thresholds, “TH=0” (nominal similarity but maximal image capture count) and “TH=best [4]”, applied to posteroanterior (PA) images in CheXpert (n=224,316), MIMIC (n=377,110), and NIH (n=108,948); majority vote of 7 expert readers was ground truth.


## Lebel Definition
* [Cardiomegaly] refers to an enlarged heart on chest x-ray, which is described as cardiomegaly and heart/cardiac enlargement.
* [Atelectasis] is a condition in which the airways and air sacs in the lung collapse or do not expand properly. We only use “atelectasis or atelectatic changes” as the keywords.
* [Pulmonary edema] is a condition caused by excess fluid in the lung, which is described as “pulmonary edema” and “Kerley B line” at CXR report.
* [Pneumonia] is an infection of the lungs that may be caused by various pathogen, which is described as “consolidation” and “pneumonia” at CXR report. We excluded indistinctive keywords such as opacity, infiltration, density, etc.  
* [Pleural effusion] is a buildup of fluid between the layers of tissue that line the lungs and chest cavity. We use “pleural effusion”, “costophrenic angle blunting”, “hemothorax”, “hydropneumothorax” and “empyema” as the keywords. 


## Results
Sharing automatic labels (at TH=BEST [4]) for three public datasets.
* Automatic labels for CheXpert: train_pa_chexpert_nature.csv
* Automatic labels for MIMIC   : train_pa_mimic_nature.csv
* Automatic labels for NIH     : train_pa_nih_nature.csv

* Platinum labels for test     : platinum_label_abnormal_feature.csv

Because the shared automatic labels for three public datasets include the 490 samples with platinum labels, you need to exclude them from the automatic labels if you want to use the platinum labels as your testset for developments [4].

[Counts for automatic labels]
  
![Alt text](./summary_table.png?raw=true "Summary about automatic labels")

[Performance for automatic labels, based on the 490 platinum labels]
  
![Alt text](./performance_table.png?raw=true "Performance of automatic labels")


## Reference
[1] Irvin, J., Rajpurkar, P., Ko, M., Yu, Y., Ciurea-Ilcus, S., Chute, C., Marklund, H., Haghgoo, B., Ball, R., Shpanskaya, K. and Seekins, J. Chexpert: A large chest radiograph dataset with uncertainty labels and expert comparison. In Proceedings of the AAAI Conference on Artificial Intelligence 33, 590-597 (2019). Available at: https://stanfordmlgroup.github.io/competitions/chexpert/

[2] Johnson, A.E., Pollard, T.J., Shen, L., Li-Wei, H.L., Feng, M., Ghassemi, M., Moody, B., Szolovits, P., Celi, L.A. and Mark, R.G. MIMIC-III, a freely accessible critical care database. Scientific data, 3(1), 1-9 (2016). DOI: 10.1038/sdata.2016.35. Available at: http://www.nature.com/articles/sdata201635

[3] Wang, X., Peng, Y., Lu, L., Lu, Z., Bagheri, M., & Summers, R. M. Chestx-ray8: Hospital-scale chest x-ray database and benchmarks on weakly-supervised classification and localization of common thorax diseases. In Proceedings of the IEEE conference on computer vision and pattern recognition, 2097-2106 (2017). Images are available via Box: https://nihcc.app.box.com/v/ChestXray-NIHCC

[4] Kim, D., Chung, J., Choi, J., Succi, M., Conklin, J., Longo, M.G.F., Ackman, J., Little, B., Petranovic, M., Kalra, M. and Lev, M., 2021. Automated Labeling of Chest X-ray Images using a Quantitative Explainable Atlas-Based AI Model.
