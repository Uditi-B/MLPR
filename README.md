# MLPR
## Aim
The objective of this lab is to:
1. Detect faces in a group image using Haar Cascade. (![Plaksha_Faculty](https://github.com/user-attachments/assets/8b71a546-37c5-4946-95fe-ba65b7417c65))
2. Extract color-based features (Hue and Saturation) from detected faces.
3. Perform K-Means clustering on extracted features.
4. Classify a new template image into one of the discovered clusters. (![Dr_Shashi_Tharoor](https://github.com/user-attachments/assets/38558e93-42e0-4091-be91-889e27df9958))
5. Visualize clustering results and interpret findings.

## Methodology
### 1. Face Detection
Used OpenCV’s Haar Cascade classifier.
Converted image to grayscale for detection.
Detected bounding boxes around faces.
Total faces detected: 30/30 (100% detection rate).
<img width="1601" height="1017" alt="Screenshot 2026-02-15 201954" src="https://github.com/user-attachments/assets/63ed4c2d-7edf-4635-accc-a0be52b22b11" />

### 2. Feature Extraction (HSV Color Space)
Converted detected face regions from BGR → HSV.
Extracted:
  Mean Hue
  Mean Saturation
Each face represented as a 2D feature vector: Mean hue and mean saturation, this transforms the problem into a feature space clustering task.

### 3. K-Means Clustering
Applied KMeans with n_clusters = 2.
Faces were grouped based on similarity in color distribution.
Cluster labels assigned as:
  Cluster 0
  Cluster 1
Scatter plot of faces in HSV feature space: <img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/0842b881-8693-46ff-89ec-91c1fa53c6c4" />

### 4. Cluster Centroid Visualization
Computed centroids for both clusters.
Plotted centroids as ‘X’ markers.
Observed separation based on color similarity (likely lighting/skin tone variations).
Scatter plot showing clusters with centroid markers: <img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/57c6d0df-95e6-476f-89c0-4d14bb86cdd5" />

### 5. Template Face Classification
Loaded template image (Dr_Shashi_Tharoor.jpg).
Extracted HSV features. (<img width="501" height="529" alt="Screenshot 2026-02-15 203827" src="https://github.com/user-attachments/assets/ace1487b-da32-4654-b760-e28b938d205b" />)
Predicted cluster using: kmeans.predict()
Plotted template point in HSV space.
<img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/e676d442-88d6-418c-97b3-ba66e936b811" />
Final clustering plot showing template face as a violet point with predicted cluster: <img width="1005" height="547" alt="image" src="https://github.com/user-attachments/assets/b6a236ce-58f1-4df6-9eee-1a19a9ad50b7" />

## Key Findings

Haar Cascade successfully detected all faces in the image.
HSV feature extraction enabled compact representation using mean Hue and Saturation.
K-Means effectively clustered faces based on color similarity.
The template image was correctly assigned to a cluster using distance-based prediction.

## Conclusion

This lab demonstrated a complete pipeline of face detection, feature extraction, clustering, and prediction. The results show how distance based algorithms like
K-Means group data based on feature similarity, highlighting the importance of proper feature selection in machine learning tasks.





