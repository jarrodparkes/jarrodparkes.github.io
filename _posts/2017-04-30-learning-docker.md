---
layout: post
title:  Learning Docker
date:   2017-04-30 
tags:   docker, server, linux
---

Recently, I’ve been learning about Docker — and it’s great! I won’t go as far as full fanboy, but what it does for virtualizing lightweight Linux systems is really beneficial for development and deployment of applications that will eventually live in the cloud. I’ve also been using it for a pet project called "A-Z Programming"; hopefully, posts related to A-Z Programming will become norm on my blog, but I still have a few things to prepare before that becomes a reality. If you’ve never heard of Docker, here are few analogies and principles I’ve been using to keep its major components in my mind:

1. A **Dockerfile** describes an **image**.
2. *An **image** is like a template* for your ideal execution environment.
3. An **image** can be built from a **Dockerfile** using the `docker build` command.
4. *A **container** is like an instance of an image*.
5. A **container** can be created from an **image** using the `docker run` command.
6. *Running a **container** is like installing and running an iOS app* — the app comes bundled with all its necessary dependencies and files, and it runs in its own sandboxed environment.

To learn more about Docker and the Docker CLI (which exposes the `docker build` and `docker run` commands, check out the [Docker CLI Docs](https://docs.docker.com/engine/reference/commandline/docker/).
