## 🚀 Live Demo
https://meridian-1-5x4j.onrender.com


## 🎥Video Conferencing App
A real-time video conferencing web application built using the MERN stack, Socket.IO, and WebRTC. The application enables users to authenticate securely, create/join video meetings, communicate in real time, and establish peer-to-peer video and audio connections.


## 📌 Features
🔐 User authentication using JWT  
👤 User registration and login  
🎥 Real-time video conferencing  
🎙️ Audio and video controls  
🔄 Peer-to-peer communication using WebRTC  
⚡ Real-time signaling using Socket.IO  
👥 Multiple users can join a meeting  
📴 Mute/unmute microphone  
📹 Turn camera on/off  
🎞️ Display Share  
💬 Real-time communication  
🔗 Meeting/room-based video calls  
📱 Responsive user interface  
🔒 Secure authentication and protected routes  


## 🛠️ Tech Stack
## Frontend
React.js  
JavaScript  
HTML5  
CSS3  
Axios  
React Router  
Socket.IO Client  
## Backend  
Node.js 
Express.js  
MongoDB  
Mongoose  
JWT Authentication  
Socket.IO  
## Real-Time Communication
WebRTC — Peer-to-peer audio/video communication  
Socket.IO — Signaling and real-time events  



## 🏗️ Architecture

The application follows a MERN-based client-server architecture.  

                    ┌─────────────────────┐
                    │      React.js       │
                    │      Frontend       │
                    └──────────┬──────────┘
                               │
                    HTTP / REST API
                               │
                               ▼
                    ┌─────────────────────┐
                    │     Express.js      │
                    │       Backend       │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │      MongoDB        │
                    │      Database       │
                    └─────────────────────┘

                               │
                         Socket.IO
                               │
                               ▼
                    ┌─────────────────────┐
                    │  WebRTC Signaling   │
                    └──────────┬──────────┘
                               │
                    Peer-to-Peer Connection
                               │
                ┌──────────────┴──────────────┐
                ▼                             ▼
          ┌───────────┐                 ┌───────────┐
          │  User A   │◄──── WebRTC ───►│  User B   │
          └───────────┘                 └───────────┘


## 🔄 How WebRTC Works in This Project

The application uses WebRTC P2P architecture for transmitting audio and video.  

Socket.IO is primarily used for signaling, while the actual media communication happens directly between peers.  

Connection Flow  
User A  
   │
   │ Join Room  
   ▼
Socket.IO Server  
   │
   │ Notify User B  
   ▼
User B  
   │
   │ WebRTC Offer/Answer  
   │
   ▼
ICE Candidate Exchange  
   │
   ▼
P2P Connection Established  
   │
   ├──────── Audio ────────►  
   └──────── Video ────────►  




## 🔐 Authentication

JWT is used to authenticate users.  

Authentication Flow  
User  
 │
 ├── Register/Login  
 │
 ▼
Backend  
 │
 ├── Validate Credentials  
 │
 ├── Generate JWT  
 │
 ▼
Client  
 │
 └── Store Authentication Token  
        │
        ▼
   Protected APIs  



## ⚡ Socket.IO

Socket.IO is used for real-time communication between clients and the server.  

It handles events such as:  

User joining a room  
User leaving a room  
WebRTC offer  
WebRTC answer  
ICE candidates  
User connected/disconnected  
Real-time meeting events  

Example signaling flow:  

Client A  
   │
   │ socket.emit("offer")  
   ▼
Socket.IO Server  
   │
   │ socket.to(room).emit("offer")  
   ▼
Client B  