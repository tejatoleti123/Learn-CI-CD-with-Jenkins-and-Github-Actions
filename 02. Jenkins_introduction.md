# Jenkins – Introduction and Architecture

---

## What is Jenkins?

Jenkins is an open-source automation server used to implement CI/CD pipelines.

It helps automate:
- Code builds
- Testing
- Packaging
- Deployment

---

## Why Jenkins is widely used

- Open-source and free
- Huge plugin ecosystem
- Works with any programming language
- Highly customizable
- Widely used in enterprises

---

## Jenkins Architecture

Jenkins follows a Controller and Agent architecture.

### Jenkins Controller
- Provides Web UI
- Manages jobs and pipelines
- Schedules builds
- Distributes work to agents

### Jenkins Agent
- Executes the actual jobs
- Can run on Linux, Windows, or Docker
- Can be on the same or different machine

---

## Jenkins in a real-world setup

Typical setup:
- Jenkins Controller on an EC2 instance
- Agents on EC2 or Docker containers
- Jenkins connected to Git repositories
- Jenkins connected to deployment targets

---

## Why Jenkins is still relevant

Even though newer tools exist:
- Jenkins supports complex workflows
- Jenkins works outside GitHub
- Jenkins is highly extensible

Jenkins is powerful when flexibility is required.
