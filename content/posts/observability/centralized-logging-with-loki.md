---
title: "Centralized Logging With Loki"
date: 2022-03-25T13:11:56+01:00
draft: true
---

# Foreword

Here's where I would speak about how important distributed systems are nowadays, and talk about few examples.
Let's skip that part, you already know most of computing systems nowadays scale horizontally by adding
more and more small hosts.

Under that paradigm there's only one question, when bugs come (because trust me, they will) how would you
troubleshoot them? When working with distributed systems, specially if it contain different technologies and programming languages,
logs are vital piece of information. 

The goal of this project is explore different logging solutions and different centralization strategies and technologies.

# Research questions

* Let's explore Loki
  * Log shipping techniques
  * Log processing and serialization
  * Log storage
  * Log indexing
  * Log granularity and retention period

* For the typical trendy solutions, what's the quantitative solution between them?

# Log shipping
