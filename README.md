🧠 AI-Based Brain Iron Estimation from MRI
🔍 Overview

This project develops a machine learning framework to estimate brain iron levels from T2*-weighted MRI data. Iron accumulation in the brain is associated with neurodegenerative disorders such as Alzheimer’s disease and Parkinson’s disease. The aim of this work is to explore non-invasive, imaging-based biomarkers using quantitative MRI and artificial intelligence.

🏥 Clinical Motivation

Brain iron plays a critical role in several neurological conditions, where abnormal accumulation is linked to disease progression. Traditional measurement methods are invasive or limited in accessibility. MRI, particularly T2*-weighted imaging, provides a non-invasive approach to assess iron-sensitive contrast. This project investigates how machine learning can enhance the extraction and interpretation of such biomarkers for potential clinical use.

⚙️ Methodology
Data Processing
MRI data loading using NiBabel
Intensity normalisation
Brain masking and preprocessing
Region of Interest (ROI) Analysis
Extraction of iron-rich regions (e.g. hippocampus, thalamus)
ROI-based signal quantification
Feature Extraction
Statistical features derived from T2* signal intensities
ROI-level and voxel-level representations
Machine Learning
Supervised learning models for prediction
Model evaluation using standard performance metrics
Uncertainty Estimation
Analysis of prediction confidence
Exploration of model reliability in a clinical context
🔄 Pipeline

MRI Data → Preprocessing → ROI Extraction → Feature Engineering → Machine Learning Model → Prediction + Uncertainty Analysis

📊 Results
Demonstrated feasibility of predicting iron-sensitive MRI features using machine learning
Observed meaningful variation across different brain regions
Model performance evaluated using quantitative metrics
⚠️ Limitations
Limited dataset size
Use of proxy labels rather than direct biochemical measurements
Lack of external validation on independent datasets
🔐 Ethical and Clinical Considerations
Ensuring patient data privacy and anonymisation
Awareness of bias in training datasets
This model is for research purposes only and not intended for direct clinical decision-making without validation
🔮 Future Work
Integration with Quantitative Susceptibility Mapping (QSM)
Expansion to larger, multi-centre datasets
Development of deep learning models for voxel-wise prediction
Clinical validation in neurodegenerative disease cohorts
🧾 Technical Stack
Python
NumPy, Pandas
NiBabel, SimpleITK
Scikit-learn
Matplotlib
