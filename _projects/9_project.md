---
layout: page
title: Random Quote Email Sender
description: Python script that picks a random quote from a CSV and emails it daily using smtplib and Gmail SMTP.
img: assets/img/project_img/9.png
importance: 9
category: work
github: https://github.com/SujitBhatta21/email_sender
tech:
  - python/python-original
---

A small Python utility that selects a random quote from a curated CSV of 1,665+ quotes and sends it to a recipient via Gmail SMTP. Built as a scripting exercise.

```bash
python script.py sender@gmail.com app_password recipient@example.com
```

---

## Features

- Email address validation before sending
- Random quote selection from `quotes.csv`
- Gmail SMTP via `smtplib` with app-password authentication

---

## Tech Stack

<p>
  <img src="https://img.shields.io/badge/Python-3.x-3776AB?style=flat-square&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/smtplib-Email-EA4335?style=flat-square&logo=gmail&logoColor=white" alt="smtplib"/>
</p>