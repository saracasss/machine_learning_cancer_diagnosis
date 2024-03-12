# machine_learning_cancer_diagnosis
#### Group members: Sara Cass, Fae Matin, Susan Miyengi, and Naomi Baxter

### Introduction
Cancer, colloquially known as "The Big-C," has long been a negative, life-altering adversary that transends generations and predates modern medicine. This disease's prevalance has been on the rise since the 20th century due to several factors, such as changes in lifestyle and increased life expectancy. However, during the early 21st century, cancer treatment and diagnostic methods involving the use of AI and machine learning began to rapidly advance. These advances offered hope for an improved quality of life and health outcome for many afflicted by the detrimental ailment. Machine learning is a powerful tool that can be used - and is actively being implemented - in many different diagnostic applications; two of which will be explored in this project.


##### Purpose
In this final project for the Data Analytics Bootcamp by EdX, taught by Dr. M. Ali Lakhani, and hosted by The University of Oregon (2024), we aim to explore the uses and benefit of machine learning techniques used to build predictive models that have been trained for the purpose of distinguishing between "normal"/benign and cancerous tissue samples.<br/>
The primary focuses of this project: machine learning using gene expression analysis to predict cancer diagnoses in a binary output, and machine learning utilizing image recognition of sample tissue to predict breast cancer.

##### Data selection
Our group began this project knowing that the subject of Cancer would be a monumetal undertaking. With such a harrowing and all-encompassing subject faaing us, we decided to narrow our focus to breast cancer. <br/>
Regarding the gene expression analysis portion of this project, we selected a dataset consisting of 289 samples with a balanced distribution of normal to tumoral samples. 
The dataset was sourced from the Curated Microarray Database (CuMiDa) created by the Structural Bioinformatics and Computational Biology Lab (SBCB) [1]. SBCB initially encountered challenges conducting their own machine learning experiments on microarray datasets due to dispersion of sourced datasets spanning various platforms and repositories. In turn, SBCB sought to compile an easy-to-use, all-in-one database of cancer microarray datasets intended specifically for further research and education with machine learning methods and analyses.
<br/>
When considering appropriate datasets for training an image recognition model, our group found many promising leads, but were predominantly left attempting to navigate a labyrinth of copyright restrictions and licensing complexities. Due in large to the resources provided to us throughout our Data Analytics cousse, the ideal dataset for the purposes of this project was sourced from the Breast Cancer Histopathological Database (BreakHis)[6] provided by Kaggle user "ambarish (Bukun)" [7]. This dataset includes photographs - at varying magnification - of tissue samples taken from 82 patients, and includes slides of benign as well as malignant presenting tissue samples.  

### Method
##### Part I Gene Expression Analysis
The dataset was read into the main GoogleColab notebook using Pandas. General information about the dataset and preprocessing steps:
- shape of the dataset - 289 rows, 35,983 columns
- value_counts of the type of sample to check for a balanced distribution
- duplicate rows that needed to be dropped
- any null values that needed to be addressed
- general .info()
- "type" column was converted to numeric values: 0.0 for cancerous tissue, 1.0 for normal tissue
- The "samples" column was dropped as it was unnecessary and prevented the scaler from working.

Then, the dataset was divided into features (X) and output (y). Scaling was done using Standard Scaler. A Principle Component Analysis was conducted to reduce the very high number of features compared to samples. The number of components was reduced to 119 and the explained variance ratio per component was graphed, as well as the explained variance ratio total or Scree plot. The threshold was set to 85% of the total variance. Using the PCA data of shape (289, 119), the data was split into training and testing sets. Class distribution of the y-test set was assessed. Then, the initial neural network model was built, trained, and tested. Then, neural network optimization was completed using keras tuner. The best result from the keras tuner was then selected, trained, and tested.

>>>Predictive models method


>>>##### Part II Image Classification

### Results
##### Part I Gene Expression Analysis
The first neural network model showed a 100% accuracy from the training data and a 72% accuracy with the testing data. This implies the model is overfitted to the training data and is too complicated for the dataset. The nn model after optimization using keras tuner showed an 82% accuracy, an improvement but still did not meet the 85% accuracy goal. Because this dataset has so few samples, something as complex as a neural network has a high risk of being overfitted to the trained and not very accurate in practice.

>>>Predictive models method


>>>##### Part II Image Classification


### References
[1] Feltes, B.C.; Chandelier, E.B.; Grisci, B.I.; Dorn, M. CuMiDa: An Extensively Curated Microarray Database for Benchmarking and Testing of Machine Learning Approaches in Cancer Research. Journal of Computational Biology, 2019.<br/> https://sbcb.inf.ufrgs.br/cumida

[2] Bruno Iochins Grisci, Bruno César Feltes, Marcio Dorn, “Neuroevolution as a tool for microarray gene expression pattern identification in cancer research”, Journal of Biomedical Informatics, Volume 89, 2019, Pages 122-133, ISSN 1532-0464, 3/10/2024.<br/> https://doi.org/10.1016/j.jbi.2018.11.013.

[3] Mohit, "Breast Cancer Prediction - cancer gene expression", 2022, python language, [kaggle.com](https://www.kaggle.com/code/gomohit/breast-cancer-prediction-cancer-gene-expression)https://www.kaggle.com/code/gomohit/breast-cancer-prediction-cancer-gene-expression

[4] Sagar, Abhinav. VIT Vellor. "5 Techniques to Prevent Overfitting in Neural Networks", 2019. Neural Networks, Overfitting. 3/10/2024.<br/> https://www.kdnuggets.com/2019/12/5-techniques-prevent-overfitting-neural-networks.html

[5]





[6] Spanhol, F., Oliveira, L. S., Petitjean, C., Heutte, L., A Dataset for Breast Cancer Histopathological Image Classification, IEEE Transactions on Biomedical Engineering (TBME), 63(7):1455-1462, 2016<br/>
https://web.inf.ufpr.br/vri/databases/breast-cancer-histopathological-database-breakhis/

[7]https://www.kaggle.com/datasets/ambarish/breakhis
