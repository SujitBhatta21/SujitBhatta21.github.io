---
layout: page
title: Bounce - Nokia-Inspired Platformer
description: Java platformer recreating the classic Nokia Bounce game with three ball modes and a boss battle, using city.cs.engine.
img: assets/img/project_img/6.jpg
importance: 6
category: work
github: https://github.com/SujitBhatta21/Bounce
tech:
  - java/java-original
---

A platformer puzzle game recreating the classic Nokia Bounce experience in Java using the `city.cs.engine` physics library. Players guide Bounce through three levels, rescuing ball friends who unlock new ball modes, ending in a boss battle against the Hypnotiser.

---

## Features

- **3 ball modes** switchable with `M`:
  - *Bounce* - balanced movement and jump
  - *Rock Ball* - breaks glass obstacles, slower with higher gravity
  - *Beach Ball* - lighter, reduced gravity, longer air time
- **3 levels** - Levels 1–2 are static puzzle-platform layouts; Level 3 is a scrolling screen with a boss fight
- **Full JavaDoc** documentation across all classes

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Java-city.cs.engine-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java"/>
</p>

---

## Key Highlights

- Implemented distinct physics properties per ball mode using the engine's rigid body system
- Designed the scrolling level system for Level 3 as a separate platform manager from the static levels
- Applied OOP principles throughout: separate classes for game logic, physics, level management, and character state