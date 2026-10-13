Computer Vision Case Study: CIFAR-100 Image Classification

A comparative study of deep learning architectures for multi-class image classification using a custom Convolutional Neural Network (CNN) and transfer learning with VGG16.

Overview

This project explores image classification using the CIFAR-100 dataset, which contains 60,000 color images across 100 distinct classes. The objective is to develop, train, and evaluate deep learning models and compare their performance on an image classification task.

Two approaches are implemented and evaluated:

Custom CNN: A convolutional neural network designed from scratch to learn visual features directly from the dataset.
VGG16 Transfer Learning: A pretrained VGG16 model initialized with ImageNet weights and adapted for 100-class classification.

The project includes data exploration, preprocessing, model development, training, evaluation, and performance comparison.

Objectives
Explore and preprocess the CIFAR-100 dataset.
Develop a custom CNN architecture for image classification.
Apply transfer learning using the pretrained VGG16 architecture.
Evaluate model performance using classification metrics.
Compare the results of both approaches and identify opportunities for improvement.
Dataset

This project uses the CIFAR-100 dataset, loaded through TensorFlow/Keras.

Attribute	Description
Total images	60,000
Training images	50,000
Test images	10,000
Image dimensions	32 × 32 pixels
Image channels	3 (RGB)
Number of classes	100
Label format	Integer class labels

The images are normalized by scaling pixel values from the range of 0–255 to 0–1. For the VGG16 pipeline, images are resized to 64 × 64 pixels to match the model's configured input dimensions.

Technologies Used
Python — Core programming language
TensorFlow / Keras — Deep learning and model development
NumPy — Numerical operations
Pandas — Data handling and result comparison
Matplotlib — Visualization
Seaborn — Statistical visualization
Scikit-learn — Classification metrics and model evaluation
Jupyter Notebook / Google Colab — Interactive development and experimentation
Project Workflow
1. Data Loading and Exploratory Data Analysis
Load the CIFAR-100 training and test datasets.
Examine dataset dimensions, labels, and image samples.
Visualize sample images.
Normalize image pixel values for model training.
2. Custom CNN Development

A CNN is built from scratch using TensorFlow/Keras. Its architecture includes:

Convolutional layers for visual feature extraction.
ReLU activation functions.
Batch normalization to support stable training.
Max-pooling layers for spatial downsampling.
Dropout and L2 regularization to help reduce overfitting.
Fully connected layers for classification.
A 100-unit softmax output layer.
3. Transfer Learning with VGG16

The second approach uses VGG16 pretrained on ImageNet.

The implementation:

Loads VGG16 without its original classification head.
Freezes the pretrained convolutional base.
Resizes images to 64 × 64 × 3.
Adds global average pooling and a dense classification head.
Uses dropout as a regularization technique.
Configures the model for 100-class classification.
4. Model Evaluation

Both approaches are evaluated using the test dataset. The notebook includes:

Test accuracy and loss.
Training and validation performance plots.
Classification reports with precision, recall, and F1-score.
Confusion matrix visualizations.
A comparison of the final test accuracies.
Results

The recorded test results from the notebook are shown below.

Model	Test Accuracy
Custom CNN	13.06%
VGG16 Transfer Learning	28.41%

Key observation: VGG16 achieves a higher test accuracy than the custom CNN in this experiment, improving performance by 15.35 percentage points.

These results provide a baseline for comparing a CNN trained from scratch against a model that leverages pretrained visual features. Both models have room for improvement, and the results should be interpreted in the context of the implemented architectures, training configuration, and preprocessing pipeline.

Installation and Setup
Prerequisites
Python 3.10 or a compatible Python version.
pip package manager.
Jupyter Notebook or JupyterLab.

Google Colab is also suitable for running the notebook without a local environment setup.

1. Clone the Repository
git clone https://github.com/Rini892/Computer_Vision_Case_Study.git
cd Computer_Vision_Case_Study

2. Create a Virtual Environment (Recommended)
python -m venv .venv


Activate the environment.

Windows:

.venv\Scripts\activate


macOS / Linux:

source .venv/bin/activate

3. Install Dependencies
python -m pip install --upgrade pip
pip install tensorflow numpy pandas matplotlib seaborn scikit-learn jupyter pydot graphviz


Graphviz may also need to be installed separately on your operating system if you want to generate model architecture diagrams.

4. Launch the Notebook
jupyter notebook Computer_Vision_Case_Study.ipynb


Open the notebook in your browser and execute the cells in sequence.

Alternatively, open the notebook in Google Colab.

Note: The CIFAR-100 dataset is downloaded automatically by Keras when it is not already available locally. Running all training and evaluation cells may require considerable time and memory; a GPU-enabled environment is recommended.

Repository Structure
Computer_Vision_Case_Study/
│
├── Computer_Vision_Case_Study.ipynb
└── README.md


The notebook contains the complete workflow, including preprocessing, model definitions, training, evaluation, visualizations, and comparison of the results.

Future Improvements

Potential directions for further experimentation include:

Experimenting with deeper or more efficient CNN architectures.
Fine-tuning selected VGG16 layers after training the classification head.
Exploring alternative pretrained models and transfer learning strategies.
Applying more extensive data augmentation and hyperparameter tuning.
Evaluating per-class performance to identify difficult categories.
Improving classification accuracy through systematic model optimization.
Conclusion

This case study demonstrates two approaches to CIFAR-100 image classification: training a custom CNN from scratch and adapting a pretrained VGG16 model through transfer learning.

The recorded results show that VGG16 performs better than the custom CNN under the configurations used in this experiment. The comparison highlights the potential value of pretrained visual representations and provides a foundation for further work in deep learning and computer vision.

Author

Rini

License

No license is specified in this README. If you intend to distribute the project as open-source software, consider adding an appropriate LICENSE file to the repository.
