# face-based-attendance-monitor
Face-Based Attendance Monitoring System
An AI-powered face recognition system that automates attendance logging using live webcam feed.
A real-time Face-Based Attendance Monitoring System using deep learning with PyTorch, facenet-pytorch, and MTCNN for facial recognition and automatic attendance logging.

Project Structure

project_root/

├── photos/                 # Stores user face images (photos/username/)

├── data.pt                 # Stores face embeddings and names

├── attendance_log.csv      # Logs attendance with Name, Date and Time

├── register_user.py        # Script to register user faces via webcam

├── generate_embeddings.py  # Generate embeddings from registered photos

├── live_attendance.py      # Run live face recognition attendance

├── monthly_attendance.py   # Generate monthly attendance reports

├── requirements.txt        # Python dependencies

└── README.md               # Project documentation

Setup Instructions

1.Clone the repository
git clone https://github.com/indianresearcher/face-based-attendance-monitor.git
cd face-based-attendance-monitor

2.Install required packages
pip install -r requirements.txt

requirements.txt
torch
torchvision
facenet-pytorch
pillow
opencv-python
pandas

Steps to Run the Project

Step 1: Organize the Project Structure
Ensure the following folder exist: photos/          # For storing registered user images

Step 2: Register Users (Collect Face Data)
Run: python register_user.py

Prompt will ask for the user's name; a folder like photos/Sabu/ will be created.
Opens webcam and detects faces in real-time.
Press Spacebar to capture an image.
Capture 5-10 images per user.
Repeat for multiple users.
Press ESC to exit.

Step 3: Generate Facial Embeddings
After registering all users run: python generate_embeddings.py

Reads all images in photos/.
Detects faces and generates embeddings using FaceNet (InceptionResnetV1).
Saves embeddings to data.pt.

Step 4: Run Live Attendance System
run : python live_attendance.py

Opens webcam and recognizes registered users in real-time.
Logs recognized names with current time into attendance_log.csv.
Press ESC to stop.

Step 5: Generate Monthly Attendance Report
run : python monthly_attendance.py

