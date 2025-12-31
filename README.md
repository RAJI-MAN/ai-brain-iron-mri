AI-Assisted Identification of Brain Iron-Rich Regions from MRI
Overview

This project explores the use of machine learning to identify iron-rich regions in the human brain from magnetic resonance imaging (MRI), with a focus on transparency, uncertainty, and clinical relevance. Brain iron accumulation is strongly associated with normal ageing and neurodegenerative conditions, yet direct measurement of iron concentration in vivo remains challenging. MRI-based proxies, particularly using T2* or multi-echo GRE sequences, provide an opportunity to investigate spatial patterns of iron deposition in a non-invasive manner.

The aim of this project is not to produce a clinically deployable tool, but to develop and demonstrate a reproducible, interpretable AI pipeline for exploratory research into iron-related MRI biomarkers.

Data

The project uses publicly available, consented neuroimaging data from OpenNeuro, specifically multi-echo GRE magnitude images suitable for iron-sensitive analysis. Only a small subset of data is used for methodological development.

Data characteristics:

3D brain MRI (GRE / T2*-weighted)

Single-subject demonstration pipeline

NIfTI format (.nii.gz)

No patient-identifiable information is used.

Methods and Pipeline

The workflow follows a standard, research-grade MRI–AI pipeline:

1. MRI Loading and Visualisation

Loading of NIfTI MRI volumes

Inspection of image dimensions, voxel size, and intensity distribution

Visualisation of representative brain slices

2. Brain Masking and Intensity Normalisation

Removal of background and non-brain voxels using simple intensity-based masking

Z-score normalisation of brain intensities to reduce scanner-dependent effects

Preparation of data suitable for machine learning

3. AI-Ready Slice Generation

Selection of axial slices containing sufficient brain tissue

Conversion of 3D MRI volumes into 2D slices

Rescaling to 8-bit format for compatibility with standard ML frameworks

4. Proxy Labelling of Iron-Rich Regions

Creation of pseudo-labels based on low-signal intensity in deep brain regions

Anatomically motivated focus on central axial slices containing basal ganglia

Explicit acknowledgement that labels are approximate and not ground truth

5. Supervised Machine Learning Baseline

Training of an interpretable logistic regression model

Single-feature input (normalised MRI intensity)

Class-imbalance handling using balanced class weights

Generation of voxel-wise iron probability maps

6. Uncertainty Analysis

Estimation of prediction uncertainty from model probabilities

Identification of regions where predictions are less reliable

Emphasis on uncertainty as a requirement for safe clinical translation

Ethical Considerations and Limitations

This work uses proxy labels derived from MRI signal characteristics and anatomical assumptions, not histological ground truth. As such, predicted iron-rich regions should be interpreted as approximate indicators rather than definitive measures of iron concentration.

A central ethical consideration is avoiding overconfidence in automated outputs. To address this, uncertainty maps are generated alongside predictions, highlighting areas where model outputs should be interpreted cautiously. This aligns with responsible AI principles, where models are intended to support — not replace — expert judgement.

Potential biases include scanner-specific intensity differences, limited subject diversity, and the use of a small dataset for methodological demonstration. Any future extension of this work would require multi-site data, harmonisation strategies, and validation against clinical outcomes or biological reference standards.

This project is intended strictly for research and educational purposes.

Tools and Libraries

Python

NumPy, SciPy

NiBabel

Matplotlib

scikit-learn

All tools used are open-source.

Project Structure
AI_Brain_Iron_MRI/
├── data/
│   ├── raw/              # Original MRI files
│   └── processed/        # Derived slices and label maps
├── notebooks/
│   └── 01_load_and_visualise_MRI.ipynb
├── figures/              # Visual outputs
├── environment.yml
└── README.md

Motivation and Future Work

This project was developed to build practical, PhD-relevant experience at the intersection of MRI physics, medical image analysis, and responsible AI. Future extensions could include:

Multi-subject and multi-site analysis

Atlas-based anatomical labelling

CNN-based segmentation with uncertainty modelling

Validation against cognitive, clinical, or histological measures

Author

Rajeev
Background: Physics & Medical Physics
Interests: MRI, quantitative imaging, AI for brain health, precision medicine
