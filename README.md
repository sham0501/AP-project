# Epsilon: The Trojan War 🔵⚔️🦠

A feature-rich, multiplayer 2D survival-shooter game developed in Java. This project was built across three progressive phases as part of an Advanced Programming course, focusing on Object-Oriented Programming (OOP), SOLID principles, Model-View-Controller (MVC) architecture, Multithreading, and Network Client-Server architecture.

---

## 📌 Overview

You play as **Epsilon** (a circle), the last surviving properly encapsulated object in a system overrun by a malicious Trojan (the "Smiley" emoji). Epsilon must survive relentless waves of corrupted geometric shapes, navigate shifting application frames, upgrade abilities via a Skill Tree, and eventually team up with other players online in Squad Battles to reclaim the system.

### 🛠️ Tech Stack & Concepts
* **Language:** Java (JDK 8+)
* **Architecture:** MVC (Model-View-Controller), Event-Driven Architecture
* **Graphics:** Java Swing & AWT (Custom Layered Window Rendering)
* **Networking:** Custom Client-Server architecture (TCP/UDP/QUIC)
* **Data Management:** Custom Manual Serialization (POJO), Database integration (Hibernate ORM)
* **Advanced Java:** Multithreading, Reflection, Generic Programming
* **Build Tools:** Maven / Gradle

---

## 🚀 Development Phases

### Phase 1: Foundation (OOP & GUI Mechanics)
The first phase establishes the core game loop, basic graphics, and essential physics.
* **MVC Architecture:** Strict separation of game logic from graphical rendering.
* **Physics & Movement:** Smooth, acceleration-based movement, impact mechanics, and collision detection (Broad/Narrow Search).
* **Dynamic Environment:** The main game frame continuously shrinks to limit the player's movement, but can be expanded by shooting the walls.
* **Progression System:** Introduction of Experience Points (XP), a dynamic Skill Tree, and an in-game Shop for temporary buffs (e.g., *O' Hephaestus*, *Writ of Ares*).
* **Enemies:** Basic routing (Local Routing) for geometric enemies like Squarantine (squares) and Trigorath (triangles).

### Phase 2: Advanced Mechanics, Physics & Concurrency
The second phase introduces advanced physics, multiple overlapping frames, and complex boss fights.
* **Layered Window Rendering:** Support for multiple overlapping Swing frames with synchronized entity painting and movement constraints (Isometric vs. Rigid frames).
* **Advanced Routing:** Implementation of Global Routing and Area of Effect (AoE) attacks.
* **Boss Fights:** 
  * *Mini-bosses:* Archmire, Wyrm, Barricados, and Black Orb.
  * *Final Boss:* **Smiley** (a multi-stage boss fight featuring dynamic frame manipulation, projectile spam, and environment destruction).
* **Real-Time Serialization:** A robust, thread-safe checkpoint and save system to manually serialize and deserialize game states mid-action to prevent data loss.
* **Dynamic Spawn Mechanics:** Progressive difficulty scaling with positive and negative feedback loops based on player performance.

### Phase 3: Multiplayer & Networking (Client-Server)
The final phase transforms the offline survival game into a fully networked multiplayer experience.
* **Client-Server Architecture:** Decoupled game clients that communicate asynchronously with a central server to validate actions and update the game state.
* **Data Integrity Validation (DIV):** Server-side validation to prevent client-side cheating or tampering with offline save files.
* **Squads & Leaderboards:** Players can create or join Squads, manage a shared XP Vault, and compete for top spots on global leaderboards.
* **Multiplayer Battle Modes:**
  * **Monomachia (1v1):** Two players face off while simultaneously defending against enemy waves.
  * **Colosseum (Co-op):** Two squadmates team up to survive high-difficulty enemy waves and defeat the final boss.
  * **Battle Summon:** Dynamically call an online squadmate into an active match for assistance.
* **Automated Wave Generation:** Utilizing Java **Reflection** to dynamically detect and instantiate enemy classes without hardcoding wave compositions.
* **Global Exception Handling:** Centralized server-side error handling inspired by Spring Boot's `@ControllerAdvice`.

---

## 🕹️ How to Play

### Prerequisites
* **Java:** JDK 17 or higher recommended.
* **Build Tool:** Maven or Gradle installed on your system.
* **OS:** A desktop environment capable of running Java Swing applications.

### Running the Server
1. Navigate to the `server` directory.
2. Build the project using Maven: `mvn clean install`
3. Run the server application. The server will begin listening for incoming client connections. (A CLI console is available to execute commands like `initiateSquadBattle`).

### Running the Client
1. Navigate to the `client` directory.
2. Build the project using Maven: `mvn clean install`
3. Run the client application.
4. On the main menu, connect to the Server's IP address. (You can also play in Offline Mode, and your progress will sync once reconnected).

### Controls
* **WASD / Arrow Keys:** Move Epsilon.
* **Mouse Cursor:** Aim.
* **Left-Click:** Fire Laser/Projectiles.
* **Custom Keybinds:** Fully remappable via the in-game Settings menu.

---
*Developed as a comprehensive exercise in software engineering, architectural design, and complex state management.*
