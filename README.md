# ProxFemur & Phantom – nnUNet v2 Models

This repository relates to the work presented in the following publication: [Link / DOI].  
If you use parts of this repository, please **cite the paper as well as [nnUNet](https://github.com/MIC-DKFZ/nnUNet) and [TotalSegmentator](https://pubs.rsna.org/doi/10.1148/ryai.230024)**.

---

## Provided Models
We provide pretrained **nnUNet v2** model weights for two tasks:

1. **Proximal Femur Segmentation**  
   - Segments the proximal femur (both sides, if present) in CT scans.  
   - The entire proximal femur is included, **including the femoral head**.  

2. **Calibration Phantom Segmentation**  
   - Detects a calibration phantom (Type: Imaga Analysis, USA), if present.

---

## Integration with TotalSegmentator
Using side-specific (left and right) whole-femur masks generated with the  
[**TotalSegmentator** tool](https://github.com/wasserth/TotalSegmentator),  
the proximal femur masks can be split into **side-specific proximal femur masks**.
We recommand to use the "-stats_include_incomplete" option. 
In the case that the femur is not completely included in the CT scan, the existing part is still segmented; without this option, the femur would not be segmented at all.

---

## Calibration
If a calibration phantom is present, calibration parameters for bone mineral density  
can be derived from the segmentation mask (linear model: *a × x + b = y*), based on HU values.

- **Label 1**: 0 mg/cm³  
- **Label 2**: 75 mg/cm³  
- **Label 3**: 150 mg/cm³  

---

## Output
From the proximal femur mask, the **mean integral volumetric bone mineral density (vBMD)** can be computed:

- in **HU** (uncalibrated), or  
- in **mg/cm³** (if calibration is available).

---

## Installation & Usage
See the [nnUNet documentation]([https://github.com/MIC-DKFZ/nnUNet](https://github.com/MIC-DKFZ/nnUNet/tree/master?tab=readme-ov-file#how-to-get-started)) for details on installation and usage.  
Instructions on how to apply pretrained models are provided here: [Link](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/how_to_use_nnunet.md#how-to-deploy-and-run-inference-with-your-pretrained-models).

---

## Model Weights
- [ProxFemur](https://cloud.rz.uni-kiel.de/index.php/s/3x5dbXamP6qw4TC)
- [Phantom](https://cloud.rz.uni-kiel.de/index.php/s/YBkDZ7JNreK66M5)

---
