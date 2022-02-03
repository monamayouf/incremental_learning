# incremental_learning
This repository is a first version about the source code used to implement the algoriths of the rotocols presented in the article "Formalizing Data Preparation in
Curriculum Incremental Deep Learning on BreakHis DataSet" submitted to "Neurocomputiong journal".
This code is working on BreakHis dataset images and aims at automatically classify these images into benign and malignant tumors for the binary classification and into eight  tumors subclasses for the multiclass classification.
## BreakHis dataset
The Breast Cancer Histopathological Image Classification (BreakHis) is  composed of 9,109 microscopic images of breast tumor tissue collected from 82 patients using different magnifying factors (40X, 100X, 200X, and 400X).  To date, it contains 2,480  benign and 5,429 malignant samples (700X460 pixels, 3-channel RGB, 8-bit depth in each channel, PNG format). This database has been built in collaboration with the P&D Laboratory  – Pathological Anatomy and Cytopathology, Parana, Brazil (http://www.prevencaoediagnose.com.br). We believe that researchers will find this database a useful tool since it makes future benchmarking and evaluation possible.

### Characteristics
The dataset BreaKHis is divided into two main groups: benign tumors and malignant tumors. Histologically benign is a term referring to a lesion that does not match any criteria of malignancy – e.g., marked cellular atypia, mitosis, disruption of basement membranes, metastasize, etc. Normally, benign tumors are relatively “innocents”, presents slow growing and remains localized. Malignant tumor is a synonym for cancer: lesion can invade and destroy adjacent structures (locally invasive) and spread to distant sites (metastasize) to cause death.

In current version, samples present in dataset were collected by SOB method, also named partial mastectomy or excisional biopsy. This type of procedure, compared to any methods of needle biopsy, removes the larger size of tissue sample and is done in a hospital with general anesthetic.

The BreaKHis 1.0 is structured as follows:
![image](https://user-images.githubusercontent.com/78418034/150153807-7bb6eb73-2882-495a-be0e-a2c9f401c96e.png)


Both breast tumors benign and malignant can be sorted into different types based on the way the tumoral cells look under the microscope. Various types/subtypes of breast tumors can have different prognoses and treatment implications. The dataset currently contains four histological distinct types of benign breast tumors: adenosis (A), fibroadenoma (F), phyllodes tumor (PT), and tubular adenona (TA);  and four malignant tumors (breast cancer): carcinoma (DC), lobular carcinoma (LC), mucinous carcinoma (MC) and papillary carcinoma (PC).
![image](https://user-images.githubusercontent.com/78418034/150153579-1c32d9c9-02a4-4d4d-9aa2-0f48134e54de.png)

Each image filename stores information about the image itself: method of procedure biopsy, tumor class, tumor type, patient identification, and magnification factor. For example, SOB_B_TA-14-4659-40-001.png is the image 1, at magnification factor 40X, of a benign tumor of type tubular adenoma, original from the slide 14-4659, which was collected by procedure SOB. More formally, the format of image file name is given by the following BNF notation:

<BIOPSY_PROCEDURE>_<TUMOR_CLASS>_<TUMOR_TYPE>-<YEAR>-<SLIDE_ID>-<MAG>-<SEQ>
<BIOPSY_PROCEDURE>::=SOB
<TUMOR_CLASS>::=M|B
<TUMOR_TYPE>::=<BENIGN_TYPE>|<MALIGNANT_TYPE>
<BENIGN_TYPE>::=A|F|PT|TA
<MALIGNANT_TYPE>::=DC|LC|MC|PC
<YEAR>::=<DIGIT><DIGIT>
<PATIENT_ID>::=<NUMBER><SEC>
<SEQ>::=<NUMBER>
<MAG>::=40|100|200|400
<NUMBER>::=<NUMBER><DIGIT>|<DIGIT>
<SEC>::=<SEC>::<LETTER>|<LETTER>
<DIGIT>::=0|1|…|9
<LETTER>::=A|B|…|Z
  
## How to obtain access to the images
The BreakHis Database may be used for non-commercial research provided you acknowledge the source of the image by citing the following paper in publications about your research:

[1] Spanhol, F., Oliveira, L. S., Petitjean, C., Heutte, L., A Dataset for Breast Cancer Histopathological Image Classification, IEEE Transactions on Biomedical Engineering (TBME), 63(7):1455-1462, 2016. [pdf]
In order to receive the link to download the database we ask you to register using this link: https://web.inf.ufpr.br/vri/databases/breast-cancer-histopathological-database-breakhis/
 # Requirements
  Python >3.5
  PyImage/numpy/ panda and matplotlib libraries
  Keras library
  
  # Explanaition of the code:
  This code translates the different protocols presented in the article. There is a first step of data loading, data preparation, data balancing and data augmenatation. Once the data are ready to be fed to our model, we explore the different feeding protocols.
  The file binary classification contains all the protocols concerning the binary classification and the file multi-class classification contains the protocols for the multi-class classification.
#How to run ?
  

  #How to run
  
