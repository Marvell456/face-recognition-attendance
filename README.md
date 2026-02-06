# 📸 Face Recognition Attendance System  
*A real-time, full-stack exploration project that started my journey into machine learning in real-world conditions*

## Overview

This project is a **real-time attendance tracking system** that uses face recognition to automatically log attendance without needing manual input.

A Python program runs on a local device with a webcam, detects and recognizes faces using **InsightFace (ArcFace)**, and sends attendance data to a cloud database (Supabase). A **React-based dashboard** detects changes in the database and updates instantly, showing name of person, time, and confidence score.

I built this as a **complete and integratable system**, focusing not just on making it work, but on understanding how ML behaves under real-world constraints like lighting, movement, and network latency.

## Why I Built This

I built this because attendance taking is a problem that can be found in generally all work and learning environments (offices and schools) every single day, human/manual attendance taking interrupts lessons and is prone to errors. This project became my way of learning **machine learning as a fully working system that can actually be integrated in the real world**.

## System Design

**Local ML Client (Python)**
- Captures video
- Detects faces and generates embeddings
- Applies quality checks and cooldown logic
- Logs attendance asynchronously

**Live Dashboard (React + Supabase)**
- Subscribes to database change events
- Updates instantly without page refresh
- Displays attendance logs clearly

This project helped me learn more on how **edge ML systems communicate with cloud services in real time**.

## Key Technical Decisions

- **Embeddings over images**: Faces are compared using 512-D embeddings instead of raw images for speed and privacy.
- **Cooldown logic**: Prevents repeated logs of the same person within a short time period.
- **Asynchronous logging**: Network requests are handled in background threads to keep the video feed smooth.

I learned that **engineering choices can create a realiable and effective system even when the model is not perfect**.

## Challenges & Limitations

- Reduced accuracy under poor lighting
- No liveness detection (photos could spoof the system)
- Small dataset size
- Does not account for demographic bias

## What I Learned

This was my first project where I:
- completed a complex system end to end
- integrated ML that works in real time
- debugged performance and reliability issues
- payed attention on privacy and ethics if the project was to be used in the real world

## Tech Stack

- Python, OpenCV
- InsightFace (ArcFace)
- React
- Supabase
- Realtime subscriptions (WebSockets)

## License

This project is licensed under the MIT License.
