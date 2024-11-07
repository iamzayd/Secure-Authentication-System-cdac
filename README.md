# Secure Multi-Factor Authentication System

## Overview
This project presents a secure multi-factor authentication system that combines traditional password authentication with advanced biometric recognition and AI-driven liveness detection. The system utilizes face recognition, password hashing, and time-sensitive embedding to enhance security against common cyber threats like spoofing, replay attacks, and unauthorized access attempts.

## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [System Architecture](#system-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [Testing and Evaluation](#testing-and-evaluation)
- [Contributing](#contributing)
- [License](#license)

## Features
- **Multi-Factor Authentication**: Combines passwords with face recognition for a robust security framework.
- **AI-Driven Liveness Detection**: Uses AI to detect live human characteristics (e.g., blinking) to prevent spoofing attacks.
- **Intruder Detection**: Monitors login patterns and identifies anomalies that indicate potential intrusions.
- **Dynamic Embedding Generation**: Each login generates unique embeddings based on the face, password, and timestamp, preventing replay attacks.
- **High Security Threshold**: Ensures a 95% or higher similarity score for successful authentication.

## Technologies Used
- **ResNet**: For generating facial embeddings in the face recognition component.
- **GRU (Gated Recurrent Units)**: For embedding password hashes, adding a unique representation for each user’s password.
- **SHA-256**: For secure password hashing.
- **Cosine Similarity**: For embedding comparison, enabling robust accuracy in matching user credentials.
- **BERT**: For embedding login timestamps, adding a contextual layer to the security process.

## System Architecture
The system architecture integrates multiple components to deliver a secure, user-friendly authentication experience:
1. **User Input**: Collects face and password inputs from the user.
2. **Face Recognition & Liveness Detection**: Verifies that the face is real-time and live.
3. **Password Hashing and Embedding**: Hashes and embeds the password securely.
4. **Time Embedding**: Embeds login timestamps for added security context.
5. **Similarity Score Calculation**: Compares real-time embeddings with stored embeddings to determine authentication.
6. **Intrusion Detection**: Detects abnormal login behavior, such as unusual login times, to flag intruder attempts.

## Installation
1. **Clone the Repository**:
```
   git clone https://github.com/your-username/secure-mfa-system.git
   cd secure-mfa-system
   ```
   
Install Dependencies: Ensure you have Python 3.8+ installed, then run:

```
pip install -r requirements.txt
```
Configure Database: Set up your database and update the config.py file with your database credentials.

Run the Application:

```
python app.py
```
## Usage
#### Registering a User:

Input face data and a password to create a unique user embedding.
Data will be stored in the database for future authentication attempts.
#### Authenticating a User:

Input face and password.
The system will calculate real-time embeddings and compare them with stored data.
Authentication is successful if the similarity score exceeds 95%.
#### Testing and Evaluation
The system is tested against various attack simulations, including:

Spoofing Attacks: Tested with static images and videos to verify effectiveness of liveness detection.
Replay Attacks: The time embedding prevents reuse of old embeddings, countering replay attempts.
Intrusion Attempts: Analyzes login anomalies (e.g., location, time) to flag suspicious activity.
To run tests, use:
```
python -m unittest discover tests
```
Contributing
Contributions are welcome! Please follow these steps:

Fork the repository.
Create a new branch:
```
git checkout -b feature-branch
```
Make your changes and commit them.
Push to your branch:
```
git push origin feature-branch
```
Create a pull request.
