---
layout: page
title: AALC - Interactive Storyline
description: Puzzle-based educational web app teaching apartheid history to ages 10-14, built as a Final Year BSc project.
img: assets/img/project_img/1.png
importance: 1
category: work
github: https://github.com/SujitBhatta21/AALC-IndividualProject
tech:
  - react/react-original
  - typescript/typescript-original
  - java/java-original
  - spring/spring-original
  - postgresql/postgresql-original
  - docker/docker-original
---

An interactive educational web application built for the **Anti-Apartheid Legacy Centre (AALC)** as a Final Year BSc project. The app introduces users aged 10-14 to the apartheid regime in South Africa and the resistance movements centred around **28 Penton Street** - the African National Congress (ANC)'s London office - through a series of engaging, puzzle-based learning experiences.

**Live demo:** [aalc-individual-project.vercel.app](https://aalc-individual-project.vercel.app/)

> The backend is hosted on Render's free tier and may take ~30-120 seconds to wake up on first request.

---

## Features

- **9 interactive Shards** - puzzle-gated learning modules covering apartheid history across three narrative tracks: *Apartheid (South Africa)*, *UK Actions*, and *Global Solidarity*
- **10 puzzle types** - Fill-in-the-Blank, Jigsaw, Redacted Reveal, Drag & Categorise, Decision Tree, Audio Matching, and more
- **Progressive unlock system** - users must complete shards sequentially
- **User accounts** - register/login with auto-generated usernames; progress is saved per user
- **Interactive tutorial** - guided onboarding tour powered by driver.js

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/React-19.2-61DAFB?style=flat-square&logo=react&logoColor=white" alt="React"/>
  <img src="https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white" alt="TypeScript"/>
  <img src="https://img.shields.io/badge/Vite-7.2-646CFF?style=flat-square&logo=vite&logoColor=white" alt="Vite"/>
  <img src="https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white" alt="Java"/>
  <img src="https://img.shields.io/badge/Spring_Boot-4.0-6DB33F?style=flat-square&logo=springboot&logoColor=white" alt="Spring Boot"/>
  <img src="https://img.shields.io/badge/PostgreSQL-16-4169E1?style=flat-square&logo=postgresql&logoColor=white" alt="PostgreSQL"/>
  <img src="https://img.shields.io/badge/Docker-Compose-2496ED?style=flat-square&logo=docker&logoColor=white" alt="Docker"/>
  <img src="https://img.shields.io/badge/Vercel-Deploy-000000?style=flat-square&logo=vercel&logoColor=white" alt="Vercel"/>
  <img src="https://img.shields.io/badge/Render-Deploy-46E3B7?style=flat-square&logo=render&logoColor=white" alt="Render"/>
</p>

<div class="row mt-2">
  <div class="col-sm-4">
    <h3>Frontend</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Technology</th><th>Version</th></tr></thead>
      <tbody>
        <tr><td>React + TypeScript</td><td>19.2 / 5.9</td></tr>
        <tr><td>Vite + SWC</td><td>7.2.4</td></tr>
        <tr><td>React Router DOM</td><td>7.12.0</td></tr>
        <tr><td>driver.js</td><td>1.4.0</td></tr>
      </tbody>
    </table>
  </div>
  <div class="col-sm-4">
    <h3>Backend</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Technology</th><th>Version</th></tr></thead>
      <tbody>
        <tr><td>Java + Spring Boot</td><td>21 / 4.0.0</td></tr>
        <tr><td>Spring Data JPA</td><td>-</td></tr>
        <tr><td>PostgreSQL</td><td>16</td></tr>
      </tbody>
    </table>
  </div>
  <div class="col-sm-4">
    <h3>Infrastructure</h3>
    <table class="table table-sm table-bordered mt-1">
      <thead><tr><th>Service</th><th>Purpose</th></tr></thead>
      <tbody>
        <tr><td>Vercel</td><td>Frontend</td></tr>
        <tr><td>Render</td><td>Backend</td></tr>
        <tr><td>Neon.tech</td><td>PostgreSQL</td></tr>
        <tr><td>Docker Compose</td><td>Local dev</td></tr>
      </tbody>
    </table>
  </div>
</div>

---

## Architecture

The app follows a client-server split. Each shard follows the pattern: **Context → Fill-in-the-Blank → Shard-specific puzzle**.

- **Frontend** (`/client`) - React SPA with per-shard page components and a library of reusable puzzle components
- **Backend** (`/server`) - Spring Boot REST API with JPA entities, service layer, and a database seeder that auto-populates shard content on first startup
- **Database** - PostgreSQL storing user accounts, shard definitions (puzzle data as JSON), and per-user progress

---

## What I Built

- Designed and implemented all 10 puzzle types from scratch as self-contained React components
- Built a progressive unlock system that gates each shard behind completion of the previous one
- Architected the Spring Boot REST API including CORS configuration and a JSON type converter for storing puzzle answer structures in PostgreSQL
- Wrote a multi-stage `Dockerfile` (Maven build → JRE 21 runtime) for backend deployment on Render
- Deployed the full stack across Vercel, Render, and Neon.tech with environment-specific configuration