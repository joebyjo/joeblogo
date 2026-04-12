---
title: Cinematch
date: 2025-09-09
description: Movie discovery and Movie journaling platform
tags:
  - ExpressJS
  - Vue.js
  - node.js
  - MySQL
  - Docker
github:
cover: /images/projects/cinematch/9BE4B97F60A0D8984AEE6BEE9C15BEF6.png
---
# Building Cinematch: A Full-Stack Movie Discovery Platform

![DD2850F505CA855C9A4DE298B27A8DFD.png](/images/projects/cinematch/DD2850F505CA855C9A4DE298B27A8DFD.png)
## Introduction

One of the biggest problems with modern streaming platforms is not the lack of content, it’s deciding *what to watch*. With thousands of movies and TV shows available, users often spend more time browsing than actually watching.

To solve this, We worked on **Cinematch**, a full-stack web application designed to make movie and TV discovery fast, personalised, and interactive. The goal was to create a platform that feels engaging like a swipe-based app, while still providing powerful filtering, search, and watchlist management features.

This project allowed me to design and implement a complete production-style system covering backend architecture, authentication, database design, API integrations, and frontend interaction.

---
## The Idea Behind Cinematch

Cinematch focuses on one core principle:

> The more you interact, the better your recommendations become.

Instead of forcing users to manually search through endless categories, the platform lets them like or dislike content through a swipe-style interface. These preferences are then used to tailor future recommendations.

The experience is designed to be:

* Fast to start
* Easy to use
* Personalised over time
* Fun and visually engaging
---
## Core Features
Cinematch includes a wide range of functionality expected from a modern entertainment platform:
* Personalised movie and TV recommendations
* Homepage showing trending and top-rated media
* Swipe-based discovery system
* Full search capability for titles
* Detailed media pages with extended information
* Personal watchlist with rating and status tracking
* Secure login and signup system
* Sorting, filtering, and management tools
* Admin dashboard for platform control
* Profile picture uploads
* Dark and light theme toggle

These features together create a seamless discovery-to-watchlist workflow.

---
## System Architecture

![A610C129AF211CB358A1B693D533217A.png](/images/projects/cinematch/A610C129AF211CB358A1B693D533217A.png)

The project follows a structured full-stack architecture:

```

cinematch/
├── backend/ # Express API
│ ├── app.js
│ ├── db/
│ ├── .env
│ ├── routes/
│ ├── services/
│ ├── uploads/
│ └── views/
└── frontend/ # Static frontend using Vue
```
### Backend
The backend was built using Node.js and Express, structured around:
* Route controllers for request handling
* Service layers for business logic
* MySQL database with schema, seed, and view scripts
* Session-based authentication using Passport

Security and stability were important priorities, so the backend includes:
* Password hashing using bcrypt
* Parameterised SQL queries to prevent injection
* Request sanitisation and validation
* Secure session storage in MySQL

The system also integrates external movie data providers via API requests, allowing the platform to dynamically fetch media information.

![3837F8FD4B46367A8A8836492D24F752.png](/images/projects/cinematch/3837F8FD4B46367A8A8836492D24F752.png)

---
### Frontend

The frontend combines:
* Vue.js for reactive UI components
* Vanilla JavaScript ES6 modules
* HTML5 and CSS3

The interface was designed to prioritise usability and responsiveness, ensuring users can:

* Browse trending titles
* Swipe through recommendations
* Manage their watchlist
* Switch between dark and light themes
---

  

## Development Environment

To make the project easier for contributors and evaluators to run locally, I implemented:
* A VS Code Dev Container setup
* Automated Makefile commands
* Database reset and seed automation
* Environment-based configuration via `.env`

This allows the entire application to be launched in just a few commands, recreating a fully working development environment.

---
## Security Considerations

Security was treated as a first-class concern during development.

The application includes:
* Secure password hashing
* Sanitised user input
* Protection against SQL injection
* Authenticated session management
* Environment variable configuration

Building these protections into the system helped reinforce best practices for production-level web applications.
  
---
## What I Learned From This Project

Cinematch was more than just a coding exercise, it was an opportunity to simulate building a real product from scratch.

Through this project I strengthened my experience in:

* Designing scalable backend architecture
* Structuring full-stack applications cleanly
* Managing authentication flows
* Integrating third-party APIs
* Designing interactive user experiences
* Building developer-friendly setup tooling

Perhaps most importantly, it improved my ability to think about software not just as code, but as a complete user-focused system.

---
## Future Improvements

While Cinematch already provides a complete discovery workflow, there are several planned enhancements:

* Expanded TV show support
* Updated Frontend using react native
* Automated unit testing
* More extensive documentation
* Social “party mode” discovery sessions
* Shareable playlists
* Direct streaming platform linking

These improvements would move the project even closer to a real-world production entertainment platform.

---
## Screenshots

  

![D7684A38DEF5D97CF07E8966F877B795.png](/images/projects/cinematch/D7684A38DEF5D97CF07E8966F877B795.png)

![E67EEE9ABD03DFE4C6A0A8563EFF3B7B.png](/images/projects/cinematch/E67EEE9ABD03DFE4C6A0A8563EFF3B7B.png)

![211E702047659AC3D94425A6B1441806.png](/images/projects/cinematch/211E702047659AC3D94425A6B1441806.png)