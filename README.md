# Aura-Tune
This repository was created for DevJams 2025 conducted at Vellore Institute of Technology which is a 48 hour hackathon.
Of course. A great README.md is crucial for any hackathon project. It's the first thing judges will see. Here is a comprehensive template you can adapt. It's written in Markdown, so you can copy and paste it directly into a README.md file in your project's root directory.

# AuraTune: Your Personal AI Mood DJ 🎶

A real-time playlist generator that curates Spotify music to match your mood, analyzed directly from your facial expression.

📽️ Demo

(IMPORTANT: A GIF is the most powerful part of your README. Record your screen and put it here. This is non-negotiable for a good submission!)

The GIF should show: the webcam feed, the detected emotion, and the resulting Spotify playlist changing.

🤔 Inspiration

In a world with millions of songs at our fingertips, "choice paralysis" is a real problem. We often spend more time searching for the right music than actually enjoying it. We wanted to create a frictionless, almost magical way to bridge the gap between our internal emotional state and the music we listen to. What if your playlist could just know how you're feeling?

✨ What It Does

AuraTune is a web application that:

    Analyzes Your Face in Real-Time: Using your webcam, it captures and processes your facial expression.

    Recognizes Your Emotion: A lightweight, pre-trained AI model detects your primary emotion (e.g., Happy, Sad, Neutral, Surprised).

    Translates Emotion to Music: It intelligently maps your detected emotion to specific musical characteristics using Spotify's Audio Features (like valence, energy, and danceability).

    Generates Instant Playlists: It queries the Spotify API to find songs that match your unique emotional profile and instantly generates a playlist for you to enjoy.

🛠️ How It Works: The Tech Pipeline

Our system follows a simple four-step pipeline:

    Capture: We use OpenCV to access the webcam feed and a Haar Cascade classifier to detect and crop the user's face from the video stream.

    Recognize with Transfer Learning: The cropped face image is pre-processed and fed into a pre-trained Convolutional Neural Network (CNN). We use the model as a feature extractor to get a rich emotional embedding from the face without needing to train from scratch.

    Map: We created a custom mapping logic that translates the detected emotion label (e.g., "Happy") into a target vector of Spotify audio features (e.g., high valence, high energy).

    Generate: Using the Spotipy library, we call the Spotify API's recommendation endpoint with our target audio features to get a list of relevant tracks and create a new playlist.

🚀 Tech Stack

    Backend: Python (Flask / Streamlit)

    AI / Machine Learning: TensorFlow / PyTorch, OpenCV-Python

    Frontend: HTML, CSS, JavaScript (if using Flask)

    APIs: Spotify Web API

    Deployment: (Optional, if you deploy it) Heroku, Vercel, etc.

🔧 Setup and Installation

Follow these steps to get AuraTune running on your local machine.

Prerequisites

    Python 3.8+

    A Spotify Developer account to get API keys.

    A webcam.

Installation Guide

    Clone the repository:
    Bash

git clone https://github.com/your-username/AuraTune.git
cd AuraTune

Create a virtual environment and activate it:
Bash

python -m venv venv
source venv/bin/activate  # On Windows, use `venv\Scripts\activate`

Install the required dependencies:
(Make sure you have a requirements.txt file in your project!)
Bash

pip install -r requirements.txt

Set up your environment variables:

    Create a file named .env in the root of the project.

    Go to your Spotify Developer Dashboard to get your credentials.

    Add the following to your .env file:

Code snippet

    SPOTIPY_CLIENT_ID='YOUR_SPOTIFY_CLIENT_ID'
    SPOTIPY_CLIENT_SECRET='YOUR_SPOTIFY_CLIENT_SECRET'
    SPOTIPY_REDIRECT_URI='http://localhost:8888/callback'

▶️ How to Run

    Run the application:
    Bash

    python app.py

    (Or streamlit run app.py if you use Streamlit)

    Open your browser and navigate to http://127.0.0.1:5000 (or the address provided by Streamlit).

    Authorize the application with your Spotify account, face the camera, and enjoy the music!

🤯 Challenges We Ran Into

    Finding a pre-trained emotion recognition model that was both accurate and lightweight enough for real-time inference on a CPU.

    Tuning the emotion-to-music mapping to ensure the generated playlists genuinely reflected the intended mood.

    Handling inconsistent lighting conditions which significantly impacted the accuracy of facial detection and emotion recognition.

📈 Future Improvements

    Voice Emotion Analysis: Incorporate voice analysis to create a multi-modal system that is even more accurate.

    Mood Tracking: Add a feature to track the user's mood over time and visualize the data.

    Learning from Feedback: Allow users to "like" or "dislike" songs to fine-tune the recommendation model over time.
