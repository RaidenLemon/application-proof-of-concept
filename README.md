# application-proof-of-concept
This repository contains summaries of our generated tabular data results so far

# Kidney Cancer Dataset 
This dataset was obtained from the MMIST databse (https://github.com/Multi-Modal-IST/multi-modal-ist.github.io/tree/master?tab=readme-ov-file). It contains 618 people of varying age, gender, race, stage of cancer, clinical presentation and the biopsy mutation results. The dataset contains 14 variables, including continuous, binary and categorical variables. 
The kidney cancer dataset was first to deal with missing values, then it was split 80-20 into train-validation splits, then we trained our synthetic data generation model and the current open-source standard, CT-GAN. Here are some plots summarising the results of 1000 generated synthetic people in comparison to the validation split:

First, comparing the distributions in ajcc_clin_metastasis_cm, a categorical measurement of the spread to lymph nodes (-1 represents no measurement), across the population. Note that the slight differences between the real data distributions in these two plots is due to the random selection of the validation set. 
# Ours
![CTabGAN ajcc_clin_metastasis_cm_hist](https://github.com/user-attachments/assets/34446b54-fc9c-4660-be10-d5a443cea810)
# CT-GAN
![CTGAN ajcc_clin_metastasis_cm_hist](https://github.com/user-attachments/assets/17c32b42-03ec-4c72-a682-47154c03f3fd)

Second, comparing the distributions in ajcc_path_tumor_pt, a categorical measurement of tumor size and extent, across the population. 
# Ours
![CTabGAN ajcc_path_tumor_pt_hist](https://github.com/user-attachments/assets/a1a8d5b0-3e35-4282-83b9-c0f5aa0ad7b9)
# CT-GAN
![CTGAN ajcc_path_tumor_pt_hist](https://github.com/user-attachments/assets/534499c8-6089-469a-8b0c-4d1f5fd1594d)

Third, comparing the differences between the correlation matrices 
# Real 
![CTGAN clin_genom_corr](https://github.com/user-attachments/assets/da5efd9d-bb18-474f-b291-1405d2fd5d5b)
# Ours 
![CTabGAN clin_genom_corr_table_numbers](https://github.com/user-attachments/assets/0731c1ef-df96-4043-b07a-e42fed62e5b0)
# CT-GAN
![CTGAN clin_genom_corr - Copy](https://github.com/user-attachments/assets/689985e9-ca71-48de-8e93-4da52c754100)



