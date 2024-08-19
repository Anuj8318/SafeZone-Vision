# SafeZone-Vision
PPE Violation Detection System
Overview
The PPE Violation Detection System uses deep learning and computer vision to detect personal protective equipment (PPE) violations in real-time video feeds. The system captures video frames, identifies PPE violations such as missing helmets or safety vests, and sends email alerts to designated personnel.

Project Structure
sql
Copy code
PPE-Violation-Detection-System/
├── __pycache__/
├── data/
├── models/
├── static/
├── templates/
├── utils/
├── venv/
├── yolov7/
├── app.py
├── best_old.pt
├── client_secrets.json
├── Dockerfile
├── hubconfCustom.py
├── requirements.txt
├── send_mail.py
├── test.py
├── token.json
Folders
pycache/: Stores compiled Python files.
data/: Contains datasets used for training and testing the model.
models/: Contains model-related files, possibly including custom models or configurations.
static/: Static files for the web interface, such as CSS and JavaScript.
templates/: HTML templates for the Flask web application.
utils/: Utility scripts and helper functions.
venv/: Virtual environment for managing Python dependencies.
yolov7/: Contains YOLOv7 model files and configurations.
Files
app.py: The main application script that integrates all components and runs the detection system.
best_old.pt: The pre-trained YOLOv7 model weights file.
client_secrets.json: Configuration file containing client secrets for sending emails.
Dockerfile: Contains instructions to create a Docker image for the project.
hubconfCustom.py: Custom hub configuration for loading the YOLOv7 model.
requirements.txt: Lists all the dependencies required to run the project.
send_mail.py: Script for handling the email alert functionality.
test.py: Contains test cases to validate the functionality of the system.
token.json: Token file for OAuth authentication (likely used with Google services).
Installation
Prerequisites
Python 3.8+
pip
Docker (optional, for containerized deployment)
Steps
Clone the Repository

bash
Copy code
git clone https://github.com/yourusername/PPE-Violation-Detection-System.git
cd PPE-Violation-Detection-System
Create and Activate Virtual Environment

bash
Copy code
python -m venv venv
source venv/bin/activate  # On Windows use `venv\Scripts\activate`
Install Dependencies

bash
Copy code
pip install -r requirements.txt
Download YOLOv7 Weights
Place the best_old.pt file in the root directory.

Setup Email Configuration
Update the client_secrets.json file with your email client configuration.

Run the Application

bash
Copy code
python app.py
Using Docker
Build the Docker Image

bash
Copy code
docker build -t ppe-violation-detection .
Run the Docker Container

bash
Copy code
docker run -d -p 5000:5000 ppe-violation-detection
Usage
Web Interface: Access the web interface at http://localhost:5000 to upload videos or connect to live camera feeds.
Real-time Detection: The system will display real-time detection results, highlighting any PPE violations.
Email Alerts: Configured email alerts will be sent with annotated images of the violations.
Key Components
Video Processing
Utilizes OpenCV to capture and preprocess video frames for model inference.
Model Inference
Employs YOLOv7, fine-tuned for detecting PPE items and violations.
Email Alerts
Uses threading to send email alerts without blocking the main detection process.
Docker Integration
Provides a Dockerfile for containerized deployment, ensuring consistency across environments.
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch (git checkout -b feature-branch).
Make your changes.
Commit your changes (git commit -m 'Add new feature').
Push to the branch (git push origin feature-branch).
Open a pull request.
