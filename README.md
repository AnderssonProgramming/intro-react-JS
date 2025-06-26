# Introduction to React with JSX

A Spring Boot web application demonstrating the basics of React with JSX, showcasing real-time clock updates and server status monitoring through REST API integration.

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Prerequisites](#prerequisites)
- [Installation & Setup](#installation--setup)
- [Running the Application](#running-the-application)
- [API Endpoints](#api-endpoints)
- [React Components](#react-components)
- [How It Works](#how-it-works)
- [Learning Objectives](#learning-objectives)
- [Contributing](#contributing)

## 🎯 Overview

This project serves as an introduction to React with JSX, demonstrating how to build interactive web components that communicate with a Spring Boot backend. The application features a real-time clock and a server status monitor that polls the backend every 5 seconds.

## ✨ Features

- **Real-time Clock**: Displays current time that updates every second
- **Server Status Monitoring**: Polls server status every 5 seconds via REST API
- **Session Management**: Demonstrates basic session handling with personalized greetings
- **JSX Components**: Introduction to React component lifecycle and state management
- **Spring Boot Backend**: RESTful API endpoints for status and session management

## 🛠 Technology Stack

### Backend
- **Java 8**
- **Spring Boot 2.3.1** - Web framework and application container
- **Maven** - Dependency management and build tool

### Frontend
- **React 16** - JavaScript library for building user interfaces
- **JSX** - JavaScript syntax extension for writing HTML-like code in JavaScript
- **Babel Standalone** - JavaScript compiler for transforming JSX in the browser
- **HTML5 & CSS3** - Basic web technologies

## 📁 Project Structure

```
intro-react-JS/
├── src/
│   ├── main/
│   │   ├── java/edu/eci/arsw/introReactJS/
│   │   │   ├── App.java                    # Main application class
│   │   │   ├── WebSiteController.java      # Basic REST controller
│   │   │   └── WebSiteController2.java     # Enhanced controller with session management
│   │   └── resources/
│   │       ├── application.properties       # Spring Boot configuration
│   │       └── static/
│   │           ├── index.html              # Main HTML page
│   │           └── js/
│   │               └── FirstComponent.jsx   # React components
│   └── test/
│       └── java/edu/eci/arsw/introReactJS/
│           └── AppTest.java                # Unit tests
├── pom.xml                                 # Maven configuration
└── README.md                              # Project documentation
```

## 📋 Prerequisites

Before running this application, make sure you have the following installed:

- **Java 8 or higher**
- **Maven 3.6+**
- **Web browser** (Chrome, Firefox, Safari, etc.)

## 🚀 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone https://github.com/AnderssonProgramming/intro-react-JS.git
   cd intro-react-JS
   ```

2. **Build the project**
   ```bash
   mvn clean compile
   ```

3. **Run tests (optional)**
   ```bash
   mvn test
   ```

## ▶️ Running the Application

### Option 1: Using Maven Spring Boot Plugin
```bash
mvn spring-boot:run
```

### Option 2: Using Java directly
```bash
mvn clean package
java -jar target/intro-react-JS-1.0-SNAPSHOT.jar
```

### Option 3: Run from IDE
- Import the project into your IDE (IntelliJ IDEA, Eclipse, etc.)
- Run the `WebSiteController` or `WebSiteController2` class

The application will start on **http://localhost:8081**

## 🔗 API Endpoints

| Method | Endpoint | Description | Response |
|--------|----------|-------------|----------|
| GET | `/status` | Get server status with timestamp | JSON with status message and current date/time |
| GET | `/setname?name=<name>` | Set user name in session | Greeting message with the provided name |

### Example API Responses

**GET /status**
```json
{
  "status": "Greetings from Spring Boot. 2025-06-26, 14:30:45. The server is Running!"
}
```

**GET /setname?name=John**
```
Hello John!
```

## ⚛️ React Components

### 1. Clock Component (tick function)
- **Purpose**: Displays current time that updates every second
- **Features**: 
  - Uses `setInterval` to update every 1000ms
  - Demonstrates basic JSX syntax and React rendering
  - Shows date and time formatting in JavaScript

### 2. StatusComponent (Class Component)
- **Purpose**: Monitors server status through API polling
- **Features**:
  - React class component with lifecycle methods
  - State management (`error`, `isLoaded`, `status`)
  - API calls using `fetch()`
  - Error handling and loading states
  - Automatic polling every 5 seconds

**Component Lifecycle:**
1. `constructor()` - Initialize state
2. `componentDidMount()` - Set up interval timer
3. `checkStatus()` - Fetch data from API
4. `render()` - Display component based on state

## 🔄 How It Works

1. **Application Startup**: Spring Boot starts the web server on port 8081
2. **Frontend Loading**: Browser loads `index.html` which includes React libraries and JSX components
3. **Component Initialization**: 
   - Clock component starts ticking immediately
   - Status component begins polling the server every 5 seconds
4. **Real-time Updates**: Both components update the DOM automatically
5. **Session Management**: Users can set their name via `/setname` endpoint for personalized responses

## 🎓 Learning Objectives

This project demonstrates the following React and web development concepts:

### React Fundamentals
- ✅ **JSX Syntax**: Writing HTML-like code in JavaScript
- ✅ **Component Types**: Function components vs Class components
- ✅ **State Management**: Using `this.state` and `this.setState()`
- ✅ **Lifecycle Methods**: `componentDidMount()` for setup
- ✅ **Event Handling**: Managing timers and intervals
- ✅ **Conditional Rendering**: Displaying different UI based on state

### Web Development Concepts
- ✅ **REST API Integration**: Making HTTP requests with `fetch()`
- ✅ **Asynchronous Programming**: Handling promises and async operations
- ✅ **Error Handling**: Managing API errors and loading states
- ✅ **Session Management**: Basic server-side session handling
- ✅ **Polling**: Implementing periodic data updates

### Development Tools
- ✅ **Babel**: Transpiling JSX in the browser
- ✅ **Spring Boot**: Building REST APIs
- ✅ **Maven**: Project management and dependencies

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 Notes for Learners

- This project uses **Babel Standalone** for JSX transformation, which is great for learning but not recommended for production
- The React version (16) used here is for educational purposes - consider upgrading to React 18+ for new projects
- Session management is simplified - consider using more robust solutions for production applications
- Error handling can be enhanced with proper logging and user feedback mechanisms

## 🐛 Common Issues

- **Port 8081 already in use**: Change the port in `application.properties`
- **CORS issues**: The current setup serves static files from the same origin to avoid CORS
- **JavaScript errors**: Check browser console for debugging information

---

**Happy Learning! 🚀**

This project provides a solid foundation for understanding React basics and client-server communication patterns.