---
layout: page
title: Venue and You - Booking System
description: Java Swing desktop app for managing venue seat and room bookings with MySQL persistence, built as a team project.
img: assets/img/project_img/5.png
importance: 5
category: work
github: https://github.com/SujitBhatta21/venue-and-you
tech:
  - java/java-original
  - mysql/mysql-original
---

A Java Swing desktop application for managing single and group bookings across venue halls, built as a multi-team coursework project. The marketing team (my team) owned the booking UI and database layer, interfacing with separate Operations and Box Office teams via defined API contracts.

---

## Features

- **Single & group bookings** - reserve individual seats or entire rooms
- **Interactive seat maps** - dynamic layouts for Main Hall and Small Hall with real-time availability
- **MySQL persistence** - all bookings saved via JDBC; viewable and deletable from the UI
- **MVC architecture** - clean separation between UI, service, and database layers
- **Live clock** embedded in the dashboard

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Java-JDK_17-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/Java_Swing-UI-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Swing"/>
  <img src="https://img.shields.io/badge/MySQL-Database-4479A1?style=flat-square&logo=mysql&logoColor=white" alt="MySQL"/>
  <img src="https://img.shields.io/badge/JDBC-Driver-007396?style=flat-square" alt="JDBC"/>
</p>

---

## Key Highlights

- Designed and implemented the interface contracts between the Marketing team and Operations/Box Office teams
- Built the full booking flow: seat selection → validation → database write → confirmation UI
- Team of 5 working across independently developed modules integrated through shared interfaces