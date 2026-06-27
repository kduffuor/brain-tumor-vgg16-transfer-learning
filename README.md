# Brain Tumor VGG16 Transfer Learning
Deep learning brain tumor classification using fine-tuned VGG16 with transfer learning. Achieves 97.3% accuracy in classifying MRI scans into 4 categories: glioma, meningioma, pituitary tumor, and no tumor.

## About the Project
This system analyzes MRI brain scans to classify them into four categories:
- **Glioma**: A type of brain tumor that occurs in the brain and spinal cord
- **Meningioma**: Tumor that arises from the meninges surrounding the brain
- **Pituitary**: Tumor in the pituitary gland
- **No Tumor**: Normal brain scan without tumor

The model uses transfer learning with a pre-trained VGG16 architecture, fine-tuned on brain MRI data to achieve medical-grade classification accuracy.

## Dataset
- **Training samples**: 5712 images with augmentation
- **Testing samples**: 1311 images
- **Image size**: 224x224 pixels
- **Classes**: 4 balanced categories
- **Format**: RGB MRI scan images
- **Source**: [Brain-Tumor-MRI-Dataset](https://www.kaggle.com/datasets/masoudnickparvar/brain-tumor-mri-dataset)

## Tools and Technologies Used
- **Python**: Core programming language
- **TensorFlow/Keras**: Deep learning framework
- **VGG16**: Pre-trained CNN architecture for transfer learning
- **NumPy**: Numerical computing and array operations
- **PIL (Pillow)**: Image processing and augmentation
- **Matplotlib**: Visualization and plotting
- **Scikit-learn**: Model evaluation metrics
- **Seaborn**: Statistical data visualization
- **Jupyter Notebook**: Development environment

## Model Architecture
- **Base Model**: VGG16 pre-trained on ImageNet
- **Transfer Learning**: Frozen early layers, fine-tuned last 3 layers
- **Custom Layers**:
  - Flatten layer
  - Dense layer (128 neurons, ReLU activation)
  - Dropout layers (0.3, 0.2) for regularization
  - Output layer (4 neurons, Softmax activation)

## Key Results
The model achieved **97.3% overall accuracy** with the following performance:

- **Glioma**: 96% precision, 96% recall
- **Meningioma**: 95% precision, 94% recall  
- **No Tumor**: 99% precision, 100% recall
- **Pituitary**: 98% precision, 99% recall

### Confidence Analysis
- Average confidence for correct predictions: 99.2%
- Average confidence for wrong predictions: 85.7%
- High confidence predictions (>90%) achieve 98.6% accuracy

## Features
- **Data Augmentation**: Brightness and contrast variations during training
- **Transfer Learning**: Leverages pre-trained VGG16 features
- **Early Stopping**: Prevents overfitting with patience mechanism
- **Model Checkpointing**: Saves best performing model automatically
- **Grad-CAM Visualization**: Shows which brain regions influence predictions
- **Confidence Scoring**: Provides prediction certainty for each classification

## How to Use
1. Clone the repository
2. Install required packages: `pip install tensorflow numpy pillow matplotlib scikit-learn seaborn`
3. Prepare your MRI dataset in the specified folder structure
4. Open `BrainTumorMRI.ipynb` in Jupyter Notebook
5. Run all cells to train and evaluate the model

## Model Training Details
- **Epochs**: 15 (with early stopping)
- **Batch Size**: 32
- **Optimizer**: Adam (learning rate: 0.0001)
- **Loss Function**: Sparse categorical crossentropy
- **Validation Split**: 20% of training data
- **Early Stopping**: Patience of 5 epochs monitoring validation loss

## Clinical Applications
The model demonstrates potential for:
- Automated initial screening of brain MRIs
- Assisting radiologists in tumor classification
- Reducing diagnostic time and workload
- Supporting medical education and training
- Standardizing tumor classification across facilities

## Grad-CAM Explainability
The project includes Grad-CAM (Gradient-weighted Class Activation Mapping) visualization to show:
- Which brain regions the model focuses on for predictions
- Visual explanation of decision-making process
- Verification that model attention aligns with medical knowledge
- Building trust and interpretability for clinical use

## Performance Visualization
The model includes comprehensive analysis tools:
- Training history plots
- Confusion matrix visualization
- ROC curves for each class
- Confidence distribution analysis
- Sample prediction visualization with confidence scores
## Disclaimer
This model is designed for research and educational purposes. It should not be used as the sole basis for medical decisions without proper clinical validation and oversight by qualified healthcare professionals. Always consult with medical experts for actual diagnostic and treatment decisions.
