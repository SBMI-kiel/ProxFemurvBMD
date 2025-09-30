# ProxFemurvBMD

Dieses Repository bezieht sich auf die Arbeiten aus folgender Veröffentlichung [Link / DOI]. 
Wenn Sie Teile davon verwenden zitieren sie bitte das Paper, sowie [nnUNet](https://www.google.com/url?q=https://www.nature.com/articles/s41592-020-01008-z&sa=D&source=docs&ust=1677235958581755&usg=AOvVaw3dWL0SrITLhCJUBiNIHCQO) und [TotalSegmentator](https://pubs.rsna.org/doi/10.1148/ryai.230024).

Wir stellen hier KI Modell Weights für zwei nnUNets (v2) zur verfügung.

Mit diesen kann der (1) **proximale Femur** (beide Seiten, falls vorhanden) in einem CT Scan segmentiert werden, sowie ein mögliches vorhandens (2) **Kalibrierphantom** (Typ: Fa. Imaga Analysis, USA).
Zusammen mit der seitensepzifischen (links und rechts) gesamten Femur Maske, erzeugt mit dem TotalSegmentator Tool [Link], kann aus der proximal Femur Maske ebenfalls die seitenspezifischen (links und rechts) proximale Femora Masken erzeugt werden.

Falls ein Kalbrierphantom vorhanden ist, kann aus der Segmentierungsmaske die Kalibrierparameter (a*x+b=y) für die Knochenmineraldichte aus HU Werten berechnet werden. (Label 1: 0 mg/cm³, Label 2: 75 mg/cm³, Label 3: 150 mg/cm³)

Aus der proximalen Femur Maske kann die mittlere integrale volumetrische Knochendichte (integral vBMD) in HU (unkalibirert) oder ggf. in mg/cm³ (kalibriert) berechnet werden.

Es wird der vollständige proximale Femur segmentiert, also inklusive Femur Kopf.

## Installation & Usage
[Hier](https://github.com/MIC-DKFZ/nnUNet/tree/master?tab=readme-ov-file#how-to-get-started) ist erklärt wie man das nnUNet verwendet und speziell wie man vortrainiert Modelle [Link](https://github.com/MIC-DKFZ/nnUNet/blob/master/documentation/how_to_use_nnunet.md#how-to-deploy-and-run-inference-with-your-pretrained-models) verwendet.

Link zu Modell weights:

- [ProxFemur](link)
- [Phantom](link)
