---
title: "AWS docs-as-code integration"
description: "Overhaul of documentation creation, review, and editing workflow"
documents:
  - title: "Gitlab contributor guide"
    file: "aws-gitlab-contributors-guide.pdf"
    type: "pdf"
  - title: "Gitlab repository"
    file: "aws-gitlab-setup-2.png"
    type: "image"
  - title: "Gitlab template"
    file: "aws-gitlab-setup-1.png"
    type: "image"
---

I implemented an entirely new docs-as-code integration for the AWS Well-Architected content team, including internal documentation and training for writers unfamiliar with Git.

## Project overview

### Problem
The documentation workflow relied heavily on Word documents, which were uploaded into an imperfect version control system. Oftentimes, authors worked on local versions of the documents independently, leading to multiple document mismatch scenarios. 

A large amount of manual work is performed to reconcile these versions of the documents.

### Solution
Adopt a docs-as-code approach to content authoring. 

Author all content in Markdown, and use Gitlab to store our content, manage versions, perform reviews, and tech edit content. 

I created an infrastructure for each of the Well-Architected Framework pillars, scripting to pull down existing documentation files as Markdown, and a training and documentation ecosystem for non-technical authors to learn Git and Gitlab. 

Our docs-as-code approach needed to have two essential parts:

1. We needed a solution to allow multiple different stakeholder groups (SMEs, guidance leads, and tech writers) to review content in the same place without working on local copies of documentation
2. We needed to provide templates that were easy to copy into new repositories for new documents and whitepapers

Gitlab solved both of these issues: 

* We can use _merge requests_ as centralized tickets to perform SME review, gather feedback, and implement tech edits before merging into versioned branches. 
* Because of its GitHub-style repository structure, we can create template repositories, allowing authors to easily fork them for new whitepapers

## Project timeline

- Researched docs-as-code solutions available within AWS (decided on Gitlab)
- Wrote one-page document to support a new docs-as-code approach
- Created initial Gitlab repositories as proof-of-concept
- Used this approach for one documentation release to demonstrate efficiency
- Migrated the rest of our in-progress documentation to Gitlab
- Created template files for other documentation types as forkable repositories
- Created CI/CD Gitlab pipelines that automatically convert documentation to requisite end XML format on merge to main
- Wrote documentation to train content creators on Git ideology and how to use Gitlab

## Skills used

- Docs-as-code
- Markdown
- Gitlab
- CI/CD
- Git
- Template design
- Stakeholder consensus
- Training documentation
