---
layout: post
title: Book Notes – DevOps for Developers
meta: Notes from reading DevOps for Developers
tags: book
---

# {{ page.title }}

Some notes from reading [DevOps for Developers](http://www.apress.com/9781430245698).

![Book Cover of DevOps for Developers](/images/posts/devops-for-developers.jpg)

## DevOps is a culture

You can't be "a devop" in the same way that you can't be "a hiphop"

Traditional roles still exist, but how they interact should change.

DevOps ideas can help all parts of the business

## Why do these silos exist?

Conflict of interest because of different measurements of success:

- **Development**: Build and release the features quickly
- **Operations**: Keep the application stable and available

This conflict is inevitable and should be accepted; by both sides.

## How to improve

Metrics, Process, Automation.

### Metrics: Quality and shared incentives

**System monitoring:**

Visibility of system to detect (and even prevent) incidents.
(Ops more confident in accepting releases).

**Progress metrics:**

  Feature progression to help predict rate of change.

**Definition of Done:**

  In use by the customer rather than thrown over the wall.

  Developers should see code through to production.

**Deployments vs Performance:**

  Mark deployments on important performance and metric graphs to give context to code changes.

### Process: Harmony in teams

Fast releases with increasing technical debt leads to degeneration.
Inject quality gates (TDD, CI, CR, QA, UAT) to maintain quality.

Hold retrospectives and make sure feedback is addressed.

Consider whole organisation: Sales > Dev & Design > QA > Ops > Support

### Technical: Fast feedback through automation

**Automate environment creation:**

  - Onboard new team members faster
  - Allow first line support teams to investigate issues quickly
  - Scale production systems

**Automate deployment:**

  - Confidence that release won't cause instability
  - Safer deployments give more confidence in doing them regularly

## Shared Goals

Everyone: Ship quality (stable, performant) features sustainably

**What happens:**

Devs ensure pre-release process maximises quality (TDD, CI, CR) and coordinate (plan!) sustainable release candidates (chunk at a time vs all at once)

Ops build system to allow repeatable releases and facilitate feedback to project teams

**Outcome:**

Both teams compromise, but get desired result!

## Sum is greater than its parts

An application is not just a collection of features; it solves a business need.

New features only add value if they are released in to the *production* environment: No good on a test or dev machine.

Long journey for software and all areas need to be understood:

  - cpus
  - memory
  - disks
  - OS configuration
  - network infrastructure
  - middleware (web server; database)
  - infrastructure configuration
  - programming language
  - framework
  - vendors
  - front end code
  - design
  - user experience
  - requirements
  - business need

Each silo sees a blurred picture of the other.

## What DevOps is Not

Doesn't mean that developers work on the production systems

Doesn't mean there is no process

Discipline, conventions, defined process: Transparent


## Impact elsewhere

Shared goal: Stable, reliable software

HR: Hire good programmers & good communicators so that teams can interact –> software is more likely to be well written and architected –> stable, reliable software

Sales: Get good projects with good clients –> more likely to be visionary and easy to work with –> stable, reliable software
