
---

## 📄 `02.GitHub-Actions-Workflows.md`

```md
# GitHub Actions – Workflows

## Overview

A **workflow** is the heart of GitHub Actions.

It defines:
- When automation should run
- What steps should execute
- Which runner should be used

Workflows are written in **YAML** and stored in the repository.

---

## Basic Workflow Structure

A workflow contains:

- Name
- Trigger (event)
- Jobs
- Steps

High-level structure:

```yaml
name: Example Workflow

on: push

jobs:
  example-job:
    runs-on: ubuntu-latest
    steps:
      - name: Run a command
        run: echo "Hello World"
Key Workflow Sections
name
Human-readable workflow name.

on
Defines the event trigger.

Examples:

push to branch

pull request

manual trigger

jobs
Contains one or more jobs.

Each job:

Runs independently

Executes on a runner

Contains steps

steps
Steps are executed in order inside a job.

Steps can:

Run shell commands

Use pre-built actions

Jobs and Runners
Each job must specify a runner:

runs-on: ubuntu-latest
This tells GitHub where the job should execute.

Workflow Execution Flow
Event Occurs
↓
Workflow Triggered
↓
Job Created
↓
Runner Assigned
↓
Steps Executed
↓
Status Reported to GitHub
Best Practices (Early Stage)
Keep workflows simple

One responsibility per job

Use clear step names

Avoid hardcoding secrets

Summary
Workflows define CI/CD logic

Written in YAML

Event-driven

Executed by runners
