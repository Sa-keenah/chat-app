REAL-TIME CHAT APP
This is a simple real-time chat application built with Node.js, Express, and Socket.io. It allows users to send and receive messages instantly using WebSockets.

Implementation Details
Backend: Node.js + Express for the HTTP server and routing.
Real-time Communication: Socket.io enables real-time, bidirectional communication between the client and server.
Frontend: A basic HTML + JavaScript interface to send and display messages.

File Structure
chat-app/
├── public/
│   └── index.html         # Frontend UI
├── server.js              # Main server file
├── package.json           # Project dependencies

How it Works
1. Users load the chat page.
2. A WebSocket connection is established with the server.
3. Users send messages via Socket.io.
4. Server receives and broadcasts the message to all connected clients.

How to Run the Application
Prerequisites
[Node.js](https://nodejs.org/) and npm installed on your machine.

Steps to Run
Step 1: Clone or create the folder
    mkdir chat-app
    cd chat-app

Step 2: Initialize project
    npm init -y

Step 3: Install dependencies
    npm install express socket.io cors

Step 4: Create your server.js and public/index.html files

Step 5: Run the server
node server.js

Step 6: Open in browser
Visit http://localhost:3000

Performance Metrics and Scalability Testing
Monitored Metrics

| Metric           | Description                                  |
| ---------------- | -------------------------------------------- |
| Concurrent Users | Number of users connected without lag        |
| Message Latency  | Delay between sending and receiving messages |
| Memory Usage     | RAM consumed during normal and high load     |
| CPU Usage        | % of CPU used during messaging               |
| Throughput       | Number of messages handled per second        |

Tools Used
[Artillery](https://artillery.io) for load testing

Run the test:
    artillery run load-test.yml