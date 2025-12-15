# Predicting Emergency Department Triage Acuity and Feature Importance Using Machine Learning

_Erin Cameron_

---

### Purpose:
Emergency Departments (ED) play a vital role in providing acute medical care to the public, yet they continue to experience increasing strain due to rising patient volumes, staff shortages, and delays in access to inpatient beds. The triage process of classifying patients based on urgency is a fundamental concept to ensure that critically ill patients are treated promptly. However, triage accuracy can vary depending on clinical judgment, workload, and patient presentation, often leading to mistriage. Mistriage refers to instances where patient acuity is under- or over-estimated. Within this project, mistriage was defined as any discrepancy between initial KTAS nurse assignment and the final reference triage level, encompassing both under-triage and over-triage.   

This project addresses the health informatics problem of predicting ED triage acuity using machine learning to mitigate these occurrences. The importance of this work is underscored by severe consequences associated with triage failure: under-triaged patients face dangerous delays, and over-triaged patients contribute to resource bottlenecks and crowding. Studies have directly linked prolonged ED waits and crowding to increased short-term mortality and adverse patient outcomes. Therefore, improving triage accuracy through predictive models that analyze patient demographics, vital signs, and chief complaints has the potential to enhance patient outcomes, optimize resource allocation, and reduce system strain within emergency care delivery.


### Notebooks:
* `1_data_cleaning_exploration` - This notebook is primarily responsible for loading, subsetting and examining the dataset.
* `2_classification` - This notebook is responsible for implementing supervised and unsupervised machine learning models. Includes Random Forest, Random Forest with SMOTE, Random Forest with SMOTE and Pruning, Logistic Regression, Bernoulli Naive Bayes, and t-SNE & K-means clustering.
* `3_model_evaluation` - This notebook is responsible for evaluating the performance of the machine learning models.

### Dataset Overview:
| Feature | Description | Data Values / Type |
| :--- | :--- | :--- |
| **Group** | Type of ED | 1 = Local ED 3rd Degree, 2 = Regional ED 4th Degree |
| **Sex** | Sex of the patient | 1 = Female, 2 = Male |
| **Age** | Age of the patient | Continuous variable |
| **Patients number per hour** | The total number of patients who arrived at the ED within that same hour window | Continuous variable |
| **Arrival mode** | Type of transportation to the hospital | 1 = Walking, 2 = Public Ambulance, 3 = Private Vehicle, 4 = Private Ambulance, 5,6,7 = Other |
| **Injury** | Whether the patient is injured or not | 1 = No, 2 = Yes |
| **Chief\_complain** | Describes the reason for visit as reported by the patient and recorded by the triage nurse | Text-based variable |
| **Mental** | The mental state of the patient | 1 = Alert, 2 = Verbal Response, 3 = Pain Response, 4 = Unresponse |
| **Pain** | Whether the patient has pain | 1 = Yes, 0 = No |
| **NRS\_pain** | Numeric rating scales of pain – recorded once at the time of admission | Discrete ordinal variable pain scale from 1–10 |
| **SBP** | Systolic blood pressure – recorded once at the time of admission | Continuous variable |
| **DBP** | Diastolic blood pressure – recorded once at the time of admission | Continuous variable |
| **HR** | Heart rate – recorded once at the time of admission | Continuous variable |
| **RR** | Respiratory rate – recorded once at the time of admission | Continuous variable |
| **BT** | Body temperature – recorded once at the time of admission | Continuous variable |
| **Saturation** | Oxygen saturation reading – recorded once at the time of admission | Continuous variable |
| **KTAS\_RN** | KTAS assigned by nurse | 1, 2, 3 = Emergency, 4, 5 = Non-Emergency |
| **Diagnosis in ED** | The final diagnosis assigned by the clinician after evaluation | Text-based variable |
| **Disposition** | Where the patient ended up | 1 = Discharge, 2 = Admission to ward, 3 = Admission to ICU, 4 = Discharge, 5 = Transfer, 6 = Death, 7 = Surgery |
| **KTAS\_expert** | KTAS assigned by an expert | 1, 2, 3 = Emergency, 4, 5 = Non-Emergency |
| **Error\_group** | The reason for triage error or mismatch. | 1 = Vital sign, 2 = Physical exam, 3 = Psychiatric, 4 = Pain, 5 = Mental, 6 = Underlying disease, 7 = Medical records of other ED, 8 = On set, 9 = Others, 0 = N/A |
| **Length of stay\_min** | The patient's length of stay measured in minutes | Continuous variable |
| **KTAS duration\_min** | Number of minutes before the patient has a KTAS score assigned to them | Continuous variable |
| **Mistriage** | Classification of whether the KTAS\_RN and KTAS\_expert values match | 0 = Correct, 1 = Over triage, 2 = Under triage |