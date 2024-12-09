Dashcam Route Overlay with Pix2Pix

This project explores training a Pix2Pix model to generate route overlays on dashcam images. The goal is to develop a proof-of-concept (PoC) model that can take a raw dashcam image as input and output the same image with a superimposed route.

Dataset

	•	Source: The dataset is derived from the comma2k19 dataset.
	•	Augmented Dataset: Initial dashcam footage frames are stored as input and a corresponding output was generated using comma2k19 repository utility functions.
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
	•	Training is implemented in the notebook training_metrics.ipynb.
	•	The model learns to map input dashcam images to their corresponding output images with a route overlay.

Project Files

	•	training_metrics.ipynb: The core notebook for training the Pix2Pix model.
	•	dataset/: Directory containing input and output image pairs for training.
	•	utils/: Utility scripts borrowed from the comma2k19 repository for dataset augmentation and preparation.
	•	models/: Definitions for the generator and discriminator architectures.


To train the model, run the notebook:
	1.	unzip the dataset.zip file
	2.	Open training_metrics.ipynb.
	3.	Execute the cells to preprocess the data and train the model.
	* Note this notebook was intended for use in Google Colab, but should work with minor adjustments for local execution.

Logs:
	1. Metrics per epoch will be generated measuring Generator and discriminator loss along with an FID score.
	2. Std out will be saved as a text file and optionally stored in a mounted Google drive instance if running in Colab.  

Use the trained model to generate overlays for new dashcam video:
	1.	There exists optional code blocks to process and create an output video overlaid with route prediction. Video's can be user generated or sourced from the original comma2k19 dataset.

![image](https://github.com/user-attachments/assets/b651ef62-de19-4c3d-9647-cbc7721907cf)

Acknowledgments

	•	Comma2k19 Dataset: For the base dataset and utility files.
		https://github.com/commaai/comma2k19
	•	Pix2Pix Paper: For the underlying architecture and methodology.
		https://www.tensorflow.org/tutorials/generative/pix2pix

