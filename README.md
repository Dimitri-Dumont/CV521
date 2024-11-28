Dashcam Route Overlay with Pix2Pix

This project explores training a Pix2Pix model to generate route overlays on dashcam images. The goal is to develop a proof-of-concept (PoC) model that can take a raw dashcam image as input and output the same image with a superimposed route.

Dataset

	•	Source: The dataset is based on the comma2k19 dataset.
	•	Augmented Dataset: Dashcam images from the comma2k19 dataset were augmented to include a route overlay as output.
	•	Structure:

dataset/
├── input/   # Dashcam images
└── output/  # Corresponding images with route overlays

Methodology

	1.	Data Preparation:
	•	Utility scripts borrowed from the comma2k19 repository were used for data processing and augmentation.
	•	Images were resized and normalized for compatibility with the Pix2Pix architecture.
	2.	Model:
	•	The project uses a Pix2Pix architecture comprising:
	•	Generator: A U-Net-based generator to translate input images to output overlays.
	•	Discriminator: A PatchGAN discriminator to differentiate real vs. generated overlays.
	3.	Training:
	•	Training is implemented in the notebook poc_p2p.ipynb.
	•	The model learns to map input dashcam images to their corresponding output images with a route overlay.

Project Files

	•	poc_p2p.ipynb: The core notebook for training the Pix2Pix model.
	•	dataset/: Directory containing input and output image pairs for training.
	•	comma_utils/: Utility scripts borrowed from the comma2k19 repository for dataset augmentation and preparation.
	•	models/: Definitions for the generator and discriminator architectures.
	•	logs/: TensorBoard logs for visualizing training progress.

Usage



Install the dependencies:


Training

To train the model, run the notebook:
	1.	Open poc_p2p.ipynb.
	2.	Execute the cells to preprocess the data and train the model.

Inference

Use the trained model to generate overlays for new dashcam images:
	1.	Preprocess the input image using the same steps as in training.
	2.	Pass the image through the trained generator to produce the overlay.

Results

	•	Example outputs will be added in future updates.

Acknowledgments

	•	Comma2k19 Dataset: For the base dataset and utility files.
	•	Pix2Pix Paper: For the underlying architecture and methodology.

