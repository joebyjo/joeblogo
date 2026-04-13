---
title: Smartcourse Advisor
date: 2026-02-07
description: Hackathon project for CSCxUPC Hackathon
tags:
  - AI
  - LLM
  - React
  - ExpressJS
  - nodejs
  - team
  - MySQL
  - Docker
github:
cover: /images/projects/smartcourse/EB6071833EA65FA2A0D29B52F7884C13.png
draft: true
---
# SmartCourse Advisor: Merging AI, Data, and Student Voices

## Introduction

Choosing the right university courses is a decision that can significantly shape a student’s academic journey, yet the process is often fragmented and overwhelming. Students typically rely on scattered sources such as informal reviews, outdated course guides, or trial-and-error when planning their degree.

This challenge becomes even more relevant in the context of institutional change, such as the **University of Adelaide** merger, where navigating course options can become even more complex.

To address this, we built **SmartCourse Advisor** during a hackathon under the theme _“Merger”_. The goal was to unify **student feedback, official course data, and AI-driven insights** into a single, intuitive platform. By leveraging technologies like **Node.js**, **Express.js**, SQL databases, and AI tools such as **Pickaxe**, we created a system that empowers students to make smarter, faster, and more informed course decisions.

---

## Core Features

### AI-Powered Course Advisor

At the heart of the platform is an intelligent chatbot that recommends courses based on:

- Academic history and current enrolments
- Interests and career direction
- Workload preferences and balance

This transforms course planning from a manual process into a **personalized, conversational experience**.

---

### Peer Ratings & Reviews

Students can contribute quick, meaningful feedback using tags like:

- “Great lecturer”
- “Heavy workload”

This crowdsourced layer adds **real-world insight** that traditional course planners often lack.

---

### My Courses Tracker

A dedicated space for students to:

- Input completed and current courses
- Avoid prerequisite conflicts or duplication
- Receive more accurate AI recommendations

This ensures suggestions are **context-aware and academically relevant**.

---

### Course Explorer

Each course includes a rich profile with:

- Descriptions and prerequisites
- Workload expectations
- Syllabus details
- Student ratings

By consolidating this information, the platform eliminates the need to navigate multiple systems.

---

### Saved Plan & Comparison

Students can shortlist courses and compare them side by side, enabling:

- Better decision-making
- Clearer academic planning

---

## System Architecture

SmartCourse Advisor was designed for **rapid prototyping without compromising functionality**, making it well-suited for a hackathon environment.

### Frontend

The frontend was initially prototyped using **Replit** and refined with **Figma** to create a clean, student-friendly interface.

Key considerations included:

- Simple navigation for complex academic data
- Clear presentation of course details
- Seamless interaction with the AI advisor

---

### Backend

The backend was built using:

- **Node.js** for server-side execution
- **Express.js** for API routing and logic

It handles:

- User data and course tracking
- Integration of reviews and ratings
- Communication with the AI advisor

---

### Database

An SQL database hosted on **Hostinger** was used to:

- Store course data
- Manage user inputs and reviews
- Support real-time recommendations

---

### Data Integration

One of the most technically interesting aspects was reverse-engineering the **University of Adelaide Course Planner API** to seed the platform with real course data.

This allowed the system to operate with **authentic academic context**, significantly improving the quality of recommendations.

---

### AI Integration

The AI advisor was built using **Pickaxe**, enabling:

- Conversational course recommendations
- Context-aware suggestions based on user input
- A balance between natural dialogue and structured academic logic

Additionally, tools like **ChatGPT** were used during development to refine features and improve the user experience.

---

### Pictures

![F1F9258502B5797D56AA1F282D16B080.png](/images/projects/smartcourse/F1F9258502B5797D56AA1F282D16B080.png)

![D200B88F1482293CE2429341D7A94EB6.png](/images/projects/smartcourse/D200B88F1482293CE2429341D7A94EB6.png)

![4F78F2CED74573D9BD29E56C1B3A217F.png](/images/projects/smartcourse/4F78F2CED74573D9BD29E56C1B3A217F.png)

---

## Closing Thoughts

SmartCourse Advisor demonstrates how powerful it can be to **merge data, AI, and human insight into a single experience**.

In just 48 hours, we built a working prototype that:

- Integrates real university data
- Provides personalized AI recommendations
- Prioritizes a student-first design

Beyond the technical implementation, this project reinforced the importance of designing systems around **real user workflows**—in this case, how students actually explore, compare, and choose their courses.

As universities continue to evolve, tools like SmartCourse Advisor highlight the potential of technology to make complex decisions **simpler, smarter, and more accessible**.
