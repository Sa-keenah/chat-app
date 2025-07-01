REAL-TIME CHAT APP
This is a simple real-time chat application built with Node.js, Express, and Socket.io. It allows users to send and receive messages instantly using WebSockets.

Implementation Details
Backend: Node.js + Express for the HTTP server and routing.
Real-time Communication: Socket.io enables real-time, bidirectional communication between the client and server.
Frontend: A basic HTML + JavaScript interface to send and display messages.

File Structure
chat-app/
├── public/
│   └── index.html
|__ .gitignore
|__ package-lock.json
|__ package.json
|__ READ.me.md
|__ REPORT.md
├── server.js

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
- [Artillery](https://artillery.io): Used to simulate users and generate load.
- `console.log()` statements to observe connection counts and message volume.

//Example: ```yaml
config:
  target: "ws://localhost:3000"
  phases:
    - duration: 60
      arrivalRate: 10
scenarios:
  - engine: "ws"
    flow:
      - send: { emit: "chat message", data: "Test message from Artillery" }
      - think:

Run the test:
    npm install -g artillery
    artillery run load-test.yml

Example Results (Simulated)
Users	    Avg. Latency	Throughput	    Memory  	CPU
100	        25ms	        200 msg/s	    80MB	    18%
500     	40ms	        600 msg/s	    130MB	    40%

Conclusion
This chat app demonstrates Node.js's non-blocking architecture and real-time capabilities using Socket.io. It efficiently handles multiple users with low latency and can be further scaled using tools like PM2 or Redis for load balancing.
It is ideal for learning:
- WebSocket communication
- Node.js backend setup
- Frontend interaction with live server events