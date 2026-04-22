This project is using the **CBIS-DDSM** mammography dataset. You can see that in [meta.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/csv/meta.csv), where the `Collection` field is `CBIS-DDSM`.

At a high level, the dataset has **two abnormality types**:
- `mass` cases in [mass_case_description_train_set.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/csv/mass_case_description_train_set.csv) and [mass_case_description_test_set.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/csv/mass_case_description_test_set.csv)
- `calcification` cases in [calc_case_description_train_set.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/csv/calc_case_description_train_set.csv) and [calc_case_description_test_set.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20with%20NN/dataset/csv/calc_case_description_test_set.csv)

Each CSV row is **not just one patient**. It is more like **one abnormality in one breast view**:
- `patient_id`: patient/case id
- `left or right breast`: side
- `image view`: usually `CC` or `MLO`
- `assessment`: BI-RADS-style suspicion score
- `pathology`: ground-truth label
- shape/margin fields for masses, or type/distribution fields for calcifications
- paths to the full image, cropped lesion image, and ROI mask

So for example, the same patient can appear more than once because they may have both `CC` and `MLO` views.

The image files are in [dataset/jpeg](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/jpeg), and [dicom_info.csv](C:/Users/taluk/OneDrive/Desktop/Breast%20Cancer%20Classification%20with%20NN/dataset/csv/dicom_info.csv) shows there are three main image types:
- `full mammogram images`
- `cropped images`
- `ROI mask images`

In your extracted folder there are about **10,237 JPEGs** total.

The training split looks like this:
- Mass train: **1,318 rows**, **691 unique patients**
- Calcification train: **1,546 rows**, **602 unique patients**

The test split looks like this:
- Mass test: **378 rows**, **201 unique patients**
- Calcification test: **326 rows**, **151 unique patients**

For labels, the key target is `pathology`:
- Mass train: `MALIGNANT` 637, `BENIGN` 577, `BENIGN_WITHOUT_CALLBACK` 104
- Calc train: `MALIGNANT` 544, `BENIGN` 528, `BENIGN_WITHOUT_CALLBACK` 474

One important detail: if your neural network is meant to do **binary cancer classification**, you’ll need to decide how to handle `BENIGN_WITHOUT_CALLBACK`. Common choices are:
- merge it with `BENIGN`
- drop it
- treat it as a third class

So in plain terms: this dataset contains **mammogram images plus lesion metadata and masks**, and the model’s job is usually to predict whether a lesion is **malignant or benign** from the image and/or associated crop. If you want, I can next explain **which columns should be inputs vs target for your NN**.
