# application-proof-of-concept
This repository contains summaries of our generated tabular data results so far

# Kidney Cancer Dataset 
This dataset was obtained from the MMIST databse (https://github.com/Multi-Modal-IST/multi-modal-ist.github.io/tree/master?tab=readme-ov-file). It contains 618 people of varying years since diagnosis, gender, race, stage of cancer, clinical presentation and the biopsy mutation results. The dataset contains 14 variables, including continuous, binary and categorical variables. 
The kidney cancer dataset was first processed to deal with missing values, then it was split into 80-20 train-validation splits, then we trained our synthetic data generation model and the current open-source standard, CT-GAN. Here are some plots summarising the results of 1000 generated synthetic people in comparison to the validation split:

First, comparing the categorical distributions in ajcc_clin_metastasis_cm, a categorical measurement of the spread to lymph nodes (-1 represents no measurement), across the population. Note that the slight differences between the real data distributions in these two plots is due to the random selection of the validation set. 
# Ours
![CTabGAN ajcc_clin_metastasis_cm_hist](https://github.com/user-attachments/assets/34446b54-fc9c-4660-be10-d5a443cea810)
# CT-GAN
![CTGAN ajcc_clin_metastasis_cm_hist](https://github.com/user-attachments/assets/17c32b42-03ec-4c72-a682-47154c03f3fd)

Second, comparing the categorical distributions in ajcc_path_tumor_pt, a categorical measurement of tumor size and extent, across the population:
# Ours
![CTabGAN ajcc_path_tumor_pt_hist](https://github.com/user-attachments/assets/a1a8d5b0-3e35-4282-83b9-c0f5aa0ad7b9)
# CT-GAN
![CTGAN ajcc_path_tumor_pt_hist](https://github.com/user-attachments/assets/534499c8-6089-469a-8b0c-4d1f5fd1594d)

Third, comparing the differences between the correlation matrices:
# Real 
![CTGAN clin_genom_corr](https://github.com/user-attachments/assets/da5efd9d-bb18-474f-b291-1405d2fd5d5b)
# Ours 
![CTabGAN clin_genom_corr_table_numbers](https://github.com/user-attachments/assets/0731c1ef-df96-4043-b07a-e42fed62e5b0)
# CT-GAN
![CTGAN clin_genom_corr - Copy](https://github.com/user-attachments/assets/689985e9-ca71-48de-8e93-4da52c754100)

# Breast Cancer Dataset 
This dataset was obtained from the SEER program of the NCI (https://www.kaggle.com/datasets/reihanenamdari/breast-cancer). It contains 4024 women with breast cancer with varying age, race, stage of cancer, marital status, survival status, examined lymph nodes, biopsy staining results and cancer staging from pathology results. The dataset contains 16 variables, including continuous, binary and categorical variables. 
The breast cancer dataset was first processed to remove age, survival months, status and marital status as these variables had little correlation with other variables and could be considered independant distributions. Then, the remaining data was split into 80-20 train-validation splits, then we trained our synthetic data generation model. Here are some plots summarising the results of 1000 generated synthetic people in comparison to the validation split. 

First, comparing the continuous distributions in tumor size across the population:
![CTabGAN tumor size bc hist](https://github.com/user-attachments/assets/916902da-a724-400b-869a-5abab45c5abe)

Second, comparing the continuous distributions in regional node positive, the number of regional lymph nodes extracted and examined by the pathologist and were found to contain metastases, across the population:
![CTabGAN regional node positive bc hist](https://github.com/user-attachments/assets/e48300f0-eec5-4e87-bc2a-ffeca487b86e)

Third, comparing the differences between the correlation matrices:
![CTabGAN bc corr table less col](https://github.com/user-attachments/assets/61dd66fa-6cd3-4f48-86d6-7883e4d0263f)

Finally, as a proof of concept of the ability to sample our synthetic data generation model to produce data on specific groups within a population, we conditionally generated 1000 samples of people with race "other", who represented 8% of the total population. These 1000 samples are compared to all the people in the dataset who had race "other". 

First, comparing the continuous distributions in tumor size with the "other: race population
![race other conditional sample tumor size bc hist](https://github.com/user-attachments/assets/5cb857b5-f1fe-40c6-8a1e-00fe3674ec9d)

Second, comparing the continuous distributions in regional node positive with the "other" race population
![race other conditional sample regional node positive bc hist](https://github.com/user-attachments/assets/dec867ca-f431-4270-b38e-d8e0030b8396)

