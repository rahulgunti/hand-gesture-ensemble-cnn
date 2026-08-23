# hand-gesture-ensemble-cnn
Hand gesture classification using a weighted ensemble of EfficientNetB7, ResNet-50 and Xception
This repository presents the work "Weighted Average Ensembled Probability Pipeline of Pre-trained CNN Models for Hand Gesture Classification".

The project focuses on automatic hand gesture recognition using an ensemble of three pre-trained deep learning models:

EfficientNetB7

ResNet-50

Xception

The models are combined using a Weighted Average Ensembled Probability Pipeline to improve classification performance.

🎯 Objective

The main objective is to build a robust hand gesture classification system that can handle variations in:

Gesture orientation

Lighting conditions

Backgrounds

Gesture positions and occlusions

🗂️ Dataset

The study uses the Hand Gesture Recognition Database (HGRD).

The dataset contains 10 hand gesture classes:

Palm

L

Fist

Fist Moved

Thumb

Index

OK

Palm Moved

C

Down

The paper describes a 70:10:20 split for training, validation, and testing.

🧠 Models Used

EfficientNetB7

A deep CNN architecture designed to balance model size and accuracy using compound scaling.

ResNet-50

A 50-layer residual network that uses shortcut/residual connections to improve gradient flow and deep-network training.

Xception

A CNN architecture based on depth-wise separable convolutions, designed to reduce computational cost while maintaining strong feature extraction.

🔗 Ensemble Method

Each trained model produces a probability vector for the input image.

The final prediction is obtained using a weighted average:

E(X) = [w₁V₁(X) + w₂V₂(X) + w₃V₃(X)] / W

where the optimal weights obtained using Grid Search were:

Model

Weight

EfficientNetB7

0.5

ResNet-50

0.3

Xception

0.2

The weights sum to 1.

⚙️ Training Configuration

GPU: NVIDIA Tesla P100

Optimizer: Adam

Learning rate: 0.001

Loss function: Categorical Cross-Entropy

Batch size: 32

Training epochs: 75

Early stopping patience: 3

Final classification activation: Softmax

Learning-rate reduction factor: 0.2 after loss stagnation

📊 Results

Model

Accuracy

Precision

Recall

F1-Score

EfficientNetB7

96.498%

96.489%

96.371%

96.372%

ResNet-50

93.200%

93.458%

93.207%

93.159%

Xception

90.175%

90.971%

90.010%

90.257%

Ensemble Model

98.950%

98.980%

98.935%

98.949%

The weighted ensemble achieved the best overall performance with 98.950% accuracy.

🏗️ Pipeline

Input Hand Gesture Image
          ↓
     Pre-processing
          ↓
 ┌────────┼───────────┐
 ↓        ↓           ↓
ResNet50 EfficientNetB7 Xception
 ↓        ↓           ↓
P₁(X)     P₂(X)       P₃(X)
 └────────┼───────────┘
          ↓
 Weighted Average
          ↓
 Final Gesture Prediction

📈 Evaluation

The study evaluates the individual models and final ensemble using:

Accuracy

Precision

Recall

F1-Score

Confusion Matrix

The paper includes training/validation accuracy and loss plots and confusion matrices for all three models and the final ensemble.

📄 Publication

Title: Weighted Average Ensembled Probability Pipeline of Pre-trained CNN Models for Hand Gesture Classification

Conference: 15th International Conference on Computing Communication and Networking Technologies (ICCCNT), 2024

Venue: IIT Mandi, India

Authors: Rahul Gunti, Rohan Reddy B, Gunti Swathi, Sharath Kumar Reddy G

DOI: 10.1109/ICCCNT61001.2024.10725955

👨‍💻 Author

Rahul Gunti
Department of Computer Science and Engineering
Vardhaman College of Engineering, Hyderabad, India

🔮 Future Work

The paper identifies integration of object detection with the classification pipeline as a potential direction, particularly for extending the system to video streams.

⚠️ Note on the Published Paper

The published IEEE paper is included here only if its redistribution is permitted by the applicable copyright/license terms. Otherwise, keep the repository focused on your own source code, results, figures that you are allowed to share, and a citation/link to the official publication.

📚 Citation

If you reference this work, please cite:

R. Gunti, R. Reddy B, G. Swathi, and S. K. Reddy G, "Weighted Average Ensembled Probability Pipeline of Pre-trained CNN Models for Hand Gesture Classification," 2024 15th International Conference on Computing Communication and Networking Technologies (ICCCNT), IIT Mandi, India, 2024, doi: 10.1109/ICCCNT61001.2024.10725955.
