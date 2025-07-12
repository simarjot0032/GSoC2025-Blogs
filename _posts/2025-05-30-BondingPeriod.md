---
layout: post
title: ""
categories: Community Bonding Period
---

##  GSoC 2025 Community Bonding Period

## Pre-Coding Period Highlights
  - Leading up to the coding period, I spent time getting familiar with the project structure, exploring technical possibilities, and aligning with the mentors on the development plan. Here’s what I worked on:

  - ✅ Dev Logs Hosting & Initial Exploration
    - Set up a site to host my developer logs and added my proposal to it.
    - Started exploring how to use C++ libraries directly within Node.js using two methods:

- Node Addons via N-API and CMake.
- Using child processes to execute system commands.

I initially tried building a Node addon with CMake-js, which allowed us to invoke C++ functions from Node. Although technically feasible, this approach introduced runtime complexity and pointer-related instability.

##  Discussion & Pivot
- After some experimentation and mentor input, especially from @Divyanshu Garg and @Daniel Rossberg, I realized that a simpler and more stable method would be to run the existing gcv binary as a child process from Node.js. This method is:

- More reliable and platform-independent.

- Easier to debug and optimize (via spawn, caching, job queues).

- A good fit for the stateless nature of web backends.

## MVP Planning
Based on Divyanshu’s feedback, I restructured the original plan to focus on the Minimum Viable Product (MVP):

🎯 User Story:
“I should be able to upload a file in any supported format and get a converted file in the desired format.”

🧩 MVP Scope:
Upload a file.

Convert using the gcv backend tool.

Download the output.

I broke this down into smaller tasks and created a detailed plan which I shared with the mentors for review. The finalized document was then used to populate the GitHub Issues Board for task tracking.

