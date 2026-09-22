 Todo App

A full-stack containerized todo application with automated CI/CD and AWS deployment.

Live Demo

http://16.4.23.253:3000

Note: This instance will be stopped after grading. If the URL is unreachable, run it locally — see below.

## What It Does

A simple task management app where users can:
- Add new tasks
- Mark tasks as complete / incomplete
- Filter by All / Active / Completed
- Delete individual tasks
- Bulk-clear all completed tasks

## Tech Stack

| Layer | Technology |
|-------|------------|
| Backend | Node.js + Express |
| Database | MongoDB |
| Frontend | Vanilla HTML / CSS / JavaScript |
| Containerization | Docker + Docker Compose |
| Registry | Docker Hub |
| CI/CD | GitHub Actions |
| Cloud | AWS EC2 (Ubuntu 24.04, t3.micro, Mumbai) |

Architecture

Browser → Express API (:3000) → MongoDB (:27017)

The app and database run as two separate Docker containers managed by Docker Compose. Data is persisted to a named volume. The app image is automatically built and pushed to Docker Hub by a GitHub Actions workflow on every push to `main`. In production, the same image is pulled onto an AWS EC2 instance and started with `docker compose up -d`.

## How to Run Locally

**Prerequisites:** Docker Desktop, Git

```bash
git clone https://github.com/maryamnaz425-dev/todo-website.git
cd todo-website
docker compose up -d
