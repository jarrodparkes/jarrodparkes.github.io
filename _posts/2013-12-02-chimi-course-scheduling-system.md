---
layout: post
title: Course Scheduling System
date: 2013-12-02 
tags: dev
---

![chimi-cover](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/chimi-cover.png "Chimi Course Scheduling System")

The Chimi Course Scheduling System is a web application for automatically managing the course scheduling operations of an academic department at the University of Alabama in Huntsville. I completed this semester-long senior project alongside team members James Parkes, Richard Burks, and Suzanna Vellacott-Ford. Throughout the project, I served as the project lead, a database manager, and a developer for the auto-scheduling program that powered the Chimi web experience.

The auto-scheduling program was built using the Java Development Kit 7 (JDK 7) and features a heuristic genetic algorithm that generates the best possible schedule given a data file. In the data file, constraints may exist for each course section such as classroom, technology, and instructor time requirements. Once a best schedule is calculated, the schedule is stored in Chimi's backend database for use by the web interface.

From the web interface, Chimi allowed users to upload the data file, building an ideal schedule (using a drag-n-drop), and print or save the resulting scheduling . The entire web interface was built by James Parkes while I handled the server setup and provided hooks for the database layer. Because hosting was not provided by the university, the team as forced to piggyback hosting off a personal server, so the project cannot be accessed publicly. So, I have included downloads of the user and input guides provided in the final presentation.

- [Chimi User Guide](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/chimi_user_guide.pdf)
- [Chimi Input Guide](https://s3.us-east-2.amazonaws.com/jarrodparkes.com/chimi_input_guide.pdf)