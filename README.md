# Chatter – Real-Time Group Chat App

Chatter is a lightweight real-time group chat application built with Flask and Socket.IO. With auto-generated usernames and avatars, it provides a clean and interactive platform for multiple users to communicate in real time.

## Table of Contents
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Installation](#installation)
- [Running Locally](#running-locally)
- [Deployment](#deployment)
- [Project Structure](#project-structure)
- [Future Enhancements](#future-enhancements)
- [License](#license)

## Features
- **Real-time Communication:** Instant messaging powered by WebSockets.
- **Auto-generated Usernames and Avatars:** Each user receives a unique identity and avatar upon connection.
- **User Presence Notifications:** Dynamic notifications when users join or leave the chat.
- **Responsive Interface:** Simple and clean design using HTML, CSS, and JavaScript.

## Tech Stack
- **Backend:** Flask, Flask-SocketIO, Eventlet
- **Frontend:** HTML, CSS, JavaScript
- **WebSockets:** Socket.IO for real-time data exchange
- **Production Server:** Gunicorn with Eventlet worker class

## Installation
1. **Clone the Repository**
   ```bash
   git clone https://github.com/dubeyrudra-1808/chatter.git
   cd chatter
Install Dependencies

bash
Copy
Edit
pip install -r requirements.txt
Running Locally
Start the Application

bash
Copy
Edit
python app.py
Open in Browser Navigate to http://localhost:5000 in your browser to start chatting!

Deployment
For production deployments, use Gunicorn with Eventlet to support WebSockets.

Install Gunicorn and Eventlet

bash
Copy
Edit
pip install gunicorn eventlet
Create a WSGI Entry Point (wsgi.py) If not already present, create a file named wsgi.py with the following contents:

python
Copy
Edit
from app import app, socketio

if __name__ == "__main__":
    socketio.run(app)

app = app  # Expose the app for Gunicorn
Run Gunicorn

bash
Copy
Edit
gunicorn --worker-class eventlet -w 1 wsgi:app
This configuration is ideal for deployment on platforms like Render, Heroku, or Railway.

Project Structure
graphql
Copy
Edit
chatter/
├── app.py              # Main Flask application file
├── wsgi.py             # Production WSGI entry point
├── requirements.txt    # Project dependencies
├── templates/
│   └── index.html      # Chat interface template
├── static/
│   ├── css/            # Stylesheets
│   └── js/             # Client-side Socket.IO logic
└── .gitignore          # Git ignore rules
Future Enhancements
Database Integration: Save chat history for persistence.

User Authentication: Secure login and user management.

Private Messaging: Enable direct messaging between users.

Enhanced UI/UX: Further improvements to the chat interface and design.

AI Integration: Introduce AI-powered features such as chatbot integration or message moderation.
