📌 Project Overview: Selfie Segmentation
This project performs real-time background replacement using a webcam feed. It uses MediaPipe’s Selfie Segmentation model and supports both:

OpenCV for real-time segmentation.

Gradio for building a web app interface.

🚀 Features
Real-time person/background segmentation using webcam.

Replace background with a static image.

Toggle between multiple backgrounds with keyboard keys.

Gradio-powered web interface to test segmentation on webcam input.

Visualization using OpenCV and Matplotlib.

🧠 How It Works
MediaPipe’s SelfieSegmentation model is used with model_selection=0.

Captures frames from webcam using OpenCV.

Converts frame to RGB and feeds it to the segmentation model.

Retrieves the segmentation_mask that highlights the person.

Replaces the background using numpy masking:

python
Copy
Edit
mask = np.stack((results.segmentation_mask,)*3, axis=-1) > 0.5
segmented_image = np.where(mask, frame, background)
Displays the live feed with the new background.

You can press:

a, s, d to switch between backgrounds.

q to quit.

Gradio web app allows webcam testing with randomly selected background images.

📤 Input
Real-time webcam feed.

Background images (stored locally, e.g. download.jpg, GGG.jpg).

📈 Output
Webcam feed with background removed and replaced by a selected image.

Gradio web interface output showing segmented image.

📁 Project Structure
sql
Copy
Edit
Selfie-Segmentation/
├── SelfieSegmentationwithGradio-main/
│   ├── selfie segmentation.ipynb        # Notebook with real-time and Gradio-based segmentation
│   ├── GGG.jpg
│   ├── download.jpg
│   └── download (1).jpg
├── selfie segmentation in real-time/
│   ├── selfie segmentation.ipynb        # Another real-time implementation
│   ├── img1.jpg
│   ├── img2.jpg
│   └── img3.png
