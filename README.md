# Change-Detection

# Change Detection using U-Net

This project implements a Deep Learning approach for **Change Detection** in images using the **U-Net architecture**. It is designed to take a pair of images (before and after) and generate a binary mask highlighting the differences between them.

## 📂 Project Structure

### 1. Dataset Organization
The model expects the dataset to be mounted (e.g., from Google Drive) and structured as follows:
* **A (Folder):** Contains "Before" images.
* **B (Folder):** Contains "After" images.
* **label (Folder):** Contains the ground truth binary masks.

Data is split into `Train` and `Test` sets. The preprocessing pipeline automatically resizes all input images to **512x512** pixels to ensure consistency.

### 2. Model Architecture
The project utilizes a **U-Net** model built with **TensorFlow/Keras**. Key features include:
* **Contracting Path (Encoder):** Uses Convolutional layers (`Conv2D`) and Max Pooling (`MaxPooling2D`) to capture context.
* **Expansive Path (Decoder):** Uses Transpose Convolutions (`Conv2DTranspose`) for precise localization.
* **Skip Connections:** Concatenates features from the encoder path to the decoder path to preserve spatial details.

## 🛠️ Dependencies

The following Python libraries are required to run the notebook:

* **TensorFlow & Keras:** For building and training the deep learning model.
* **OpenCV (cv2) & PIL:** For image loading and preprocessing (resizing).
* **NumPy:** For numerical operations and array manipulation.
* **Matplotlib:** For visualizing the input images and predicted masks.
* **Scikit-image:** For additional image processing utilities.

## 🚀 Usage

1.  **Setup Data Path:** Update the `path_Train` and `path_Test` variables in the notebook to point to your dataset directory.
2.  **Run Preprocessing:** Execute the cells to rename and resize images to the target `(512, 512)` resolution.
3.  **Train Model:** Run the training loop. The model uses pairs of images (A, B) to learn the change features.
4.  **Inference:** Use the trained model to predict change masks on the Test set and visualize the results.
