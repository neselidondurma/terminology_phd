--- 
tags: [#ops]
created: 27-10-2025
--- 
### 🔹 Definition / Formula

- An **Application Programming Interface (API)** is a set of defined rules, protocols, and tools for building software applications. It is a software intermediary that allows two applications to talk to each other.
    

### 🔹 Explanation (in my words)

- An API acts as a **middleman** or a **waiter** that takes a request from one software system (the client) and delivers it to another system (the server), then brings the response back. It exposes only the necessary functions and data, hiding the complexity and inner workings of the service provider.
    
- This layer of abstraction is like the electrical outlet in your wall; you don't need to know the complex wiring behind the wall (the implementation) to get power (the service); you just need to know the correct **interface** (the plug and voltage specification) to make a connection.
    

### 🔹 Components

- **Client (or Consumer):** The application or system that initiates the request.
    
- **Server (or Provider):** The application or system that processes the request and sends a response.
    
- **Endpoint:** The specific URL or address where the API can be accessed (e.g., `/users/123`).
    
- **Methods:** The types of requests that can be made (e.g., **GET** to retrieve data, **POST** to create data, **PUT/PATCH** to update, **DELETE** to remove).
    
- **Request/Response:** The structured messages containing the data sent to and from the API, often using formats like JSON or XML.
    

### 🔹 Context

- **Where it’s used:** Everywhere in **Software Development** and **Web Development**, including microservices, mobile apps, operating systems, and software libraries.
    
- **When it appears:** It's fundamental for enabling integration and communication between disparate software systems, especially in modern cloud-based and distributed architectures (e.g., a mobile app calling a weather service).
    

### 🔹 Related

- [[REST]] - [[Web Services]] - [[JSON]]
    

### 🔹 Examples / Applications

- **Google Maps API:** A third-party application can send an address to the Google Maps API. The API processes the request (finds the coordinates, generates the map image) and returns the map data/image to the application for display, all without the application needing to hold or process all the world's map data.