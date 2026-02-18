# Spring Boot WebSocket Chat Application

This is a simple real-time chat application built with **Spring Boot**, **STOMP WebSocket**, and **Thymeleaf** for the front-end. The application demonstrates bidirectional communication between clients and the server using an in-memory message broker.

## 🔍 Project Structure

```
app/
├── src/
│   ├── main/java/com/chat/app
│   │   ├── AppApplication.java          # Spring Boot entry point
│   │   ├── config/WebSocketConfig.java  # STOMP/WebSocket configuration
│   │   ├── controller/ChatController.java
│   │   └── model/ChatMessage.java       # Message payload
│   ├── main/resources
│   │   └── templates/chat.html          # Thymeleaf view for chat UI
│   └── test/java/com/chat/app
│       └── AppApplicationTests.java    # Basic context test
├── pom.xml                              # Maven build file
└── HELP.md                              # Reference links and notes
```

## ✅ Features

- WebSocket connection using STOMP protocol
- Simple broker at `/topic` for broadcasting messages
- REST endpoint (`/chat`) to serve chat interface
- Real-time display of messages with sender name

## ⚙️ Technologies Used

- Java 17+ (or later)
- Spring Boot 3 / 4 (as indicated by dependencies)
- Spring WebSocket & STOMP
- Thymeleaf templating engine
- Maven wrapper (`mvnw`) for build automation
- Bootstrap 5 for basic styling

## 🚀 Getting Started

### Prerequisites

- JDK 17 or newer installed and `JAVA_HOME` configured
- Git (optional)

### Build & Run

From the project root (the directory containing `pom.xml`), run:

```bash
# on Windows
./mvnw clean package
./mvnw spring-boot:run
```

or use your IDE to run `com.chat.app.AppApplication` directly.

The application will start on `http://localhost:8080` by default.

### Using the Chat

1. Open your browser and navigate to [http://localhost:8080/chat](http://localhost:8080/chat).
2. Enter your name in the **Your name** field.
3. Type a message and click **Send**.
4. Open additional browser windows or devices to see real‑time broadcasting.

> 🔒 The WebSocket endpoint is defined at `/chat` and allows cross‑origin requests from `http://localhost:8080`.

## 🧠 How It Works

- **WebSocketConfig** registers the STOMP endpoint and configures a simple in‑memory message broker.
- **ChatController** listens for messages sent to `/app/sendMessage` and forwards them to `/topic/messages`.
- **chat.html** includes client‑side JavaScript that establishes a SockJS/STOMP connection, subscribes to the topic, and sends messages.

## 🧪 Testing

A basic Spring context test is provided in `AppApplicationTests.java`. Run tests with:

```bash
./mvnw test
```

## 📁 Additional Information

- The `HELP.md` file in the repository contains links to relevant Spring Boot and WebSocket documentation.
- Adjust or extend this application by adding persistence, user authentication, or advanced message handling.

---

Feel free to use and modify this project as a starting point for real-time web applications!