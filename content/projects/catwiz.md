---
title: Catwiz
date: 2026-03-12
description: Prompt Injection CTF Game
tags:
  - ExpressJS
  - React
  - nodejs
  - MySQL
  - AI
  - LLM
github:
cover: /images/projects/catwiz/127B95963FE932E54ADCA95CDC7CC05B.png
draft: false
---
# Building CatWiz: A Prompt Injection CTF Challenge

## Introduction

As large language models become more integrated into real-world applications, **prompt injection** has emerged as a critical security concern. These attacks exploit how AI systems interpret input, often allowing users to bypass safeguards and extract sensitive information.

To explore this problem in a hands-on and engaging way, my teammate Hiten Gupta and I partnered with the **AIML Club - Adelaide University** to design and host _Catwiz_, a Capture The Flag (CTF) challenge centered around AI prompt injection.

The concept was simple but powerful: players interact with an AI chatbot and attempt to manipulate it into revealing a hidden password. While it starts off easy, the challenge quickly escalates, requiring deeper understanding and more creative attack strategies as naive prompt tricks stop working.

Over the course of four months, we built the entire platform from scratch, from system design and game logic to deployment and live monitoring with a strong focus on scalability and real-time user experience.

---

## Core Features

### Progressive Prompt Injection Challenges

CatWiz was designed with increasing difficulty levels, simulating real-world AI security scenarios. Early stages allowed basic prompt manipulation, while later stages required more advanced reasoning and creativity to bypass safeguards.

### Real-Time Leaderboard

A live leaderboard kept the competition engaging, allowing players to see how they ranked against others in real time. This added a strong competitive element and encouraged continuous participation throughout the event.


### Scalable Architecture on Limited Resources

Despite running on constrained infrastructure, the platform was built to handle a high volume of concurrent users. Efficient request handling and optimized backend logic ensured smooth gameplay throughout the event.

### Live Monitoring & Observability

During the competition, we actively monitored system performance and user activity, allowing us to quickly respond to issues and ensure a seamless experience for participants.

---

## Screenshots / Visuals

### Chat Interface

![CCDEB28EDC5975989EA7DFF9702E945B.png](/images/projects/catwiz/CCDEB28EDC5975989EA7DFF9702E945B.png)

### Live Leaderboard
![0B4E0FAC3AD0DD0FB16DC8F51CD2B182.png](/images/projects/catwiz/0B4E0FAC3AD0DD0FB16DC8F51CD2B182.png)

### Development & Event

![FFFC8202F47432D818C75447D319D827.png](/images/projects/catwiz/FFFC8202F47432D818C75447D319D827.png)

![4340E4CB2C6478490AD2111770B91074.png](/images/projects/catwiz/4340E4CB2C6478490AD2111770B91074.png)

![09128C97377D032BA0509CE47FFAD34C.png](/images/projects/catwiz/09128C97377D032BA0509CE47FFAD34C.png)

---

## Event Highlights

The competition saw strong participation, with players actively experimenting with creative prompt injection strategies to break the system.

A huge congratulations to **Charvi Bhandari** for securing 1st place and winning the $100 prize

We’re also incredibly grateful for the support that made this event possible:

- **Atlassian** for sponsoring the event
- **Zuli Posada**, **Hrayr Matevosyan**, and **Christelle Yeung** for their support
- The **AIML Club - Adelaide University** for giving us the opportunity to bring this idea to life

---

## Closing Thoughts

CatWiz was more than just a CTF challenge — it was an exploration of how **AI systems can be manipulated and how we can design better defenses**.

Building this platform from scratch taught us valuable lessons in:

- Designing secure AI systems
- Scaling applications under constraints
- Creating engaging, educational user experiences

As AI continues to evolve, understanding and mitigating risks like prompt injection will only become more important. CatWiz was our way of making that learning process interactive, competitive, and fun.
