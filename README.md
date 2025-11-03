## Data Exploration & Visualization

The gesture recognition dataset was analyzed through a series of exploratory visualizations,  
including distribution, normalization, and missing-value heatmaps.

---

### Label Distribution

<p align="center">
  <img src="plots/Histogram label train-final.png" width="600" alt="Train label distribution"/>
  <br>
  <em>Label histogram for train-final.csv</em>
</p>

<p align="center">
  <img src="plots/Histogram label test-final.png" width="600" alt="Test label distribution"/>
  <br>
  <em>Label histogram for test-final.csv</em>
</p>

The gesture labels are approximately balanced,  
ensuring fair training without dominant class bias.

---

### Missing Data Check

<p align="center">
  <img src="plots/MissingDatapoints1.png" width="700" alt="Missing data in train-final.csv"/>
</p>

<p align="center">
  <img src="plots/MissingDatapoints2.png" width="700" alt="Missing data in test-final.csv"/>
</p>

Both datasets show negligible missing values — confirming data integrity before preprocessing.

---

### Data Normalization

<p align="center">
  <img src="plots/Normalized_all_training_data.png" width="800"/>
</p>

<p align="center">
  <img src="plots/Normalized traing data.png" width="800"/>
</p>

<p align="center">
  <img src="plots/Normalized testing data.png" width="800"/>
</p>

Normalization aligns feature scales and eliminates skewness,  
creating a well-centered input distribution suitable for ML models.

---

### Boxplot Feature Analysis

<p align="center">
  <img src="plots/BoxPlot1-60.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot60-120.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot120-180.png" width="800"/>
</p>
<p align="center">
  <img src="plots/BoxPlot180-240.png" width="800"/>
</p>

Feature groups reveal the structural variability across joint position, cosine, and mean features.

---


### Model Comparison

<p align="center">
  <img src="plots/Model_Results_Summary.png" width="700"/>
</p>

Random Forest and Extra Trees outperform other classifiers  
with ~85% accuracy, while Gradient Boosting struggled due to limited tuning.

---

### Gesture Skeleton Reconstruction

<p align="center">
  <img src="plots/photo_2023-09-14_12-56-31.jpg" width="400"/>
  <br>
  <em>2D skeletal reconstruction from Kinect joint coordinates</em>
</p>

The skeleton graph represents the spatial relationship of 20 tracked joints,  
forming the raw basis for cosine and distance-based feature extraction.

---

### Summary

- **Data quality**: clean and balanced  
- **Normalization**: stable across both datasets  
- **Feature diversity**: visible structure clusters  
- **Top models**: Random Forest, Extra Trees  
- **Next step**: spiking neural network simulation for gesture sequences
