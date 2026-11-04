# Privacy and Personal Data

This document describes how Map of Nirn at https://github.com/hmlendea/map-of-nirn handles personal data. It covers the application behaviour and verified integrations described below. Where the software is self-hosted, the instance operator may have separate responsibilities described below.

## 📑 Table of Contents

- [What This Document Covers](#what-this-document-covers)
- [Self-Hosted Deployments](#self-hosted-deployments)
- [Data We Handle](#data-we-handle)
  - [Data Provided to the Application](#data-provided-to-the-application)
  - [Data Generated or Collected by the Application](#data-generated-or-collected-by-the-application)
  - [Data Received from Integrations](#data-received-from-integrations)
- [Processing and Use](#processing-and-use)
- [Storage, Retention, and Deletion](#storage-retention-and-deletion)
- [External Processing and Integrations](#external-processing-and-integrations)
- [Data Protection and Security](#data-protection-and-security)
- [Document Changes](#document-changes)
- [Contact](#contact)

## 🔎 What This Document Covers

This document describes how Map of Nirn at https://github.com/hmlendea/map-of-nirn handles personal data. It covers the application behaviour and verified integrations described below. Where the software is self-hosted, the instance operator may have separate responsibilities described below.

## 🏠 Self-Hosted Deployments

This project consists of static SVG and raster image assets. Users may clone or fork the repository and serve the assets from their own infrastructure. Instance operators control their deployment's configuration, local storage, logs, backups, access controls, retention, and request handling. The project maintainers do not receive data from self-hosted instances.

No telemetry, update checks, crash reports, email, authentication, reverse-proxy, object-storage, or monitoring integrations are built into the assets.

## 📥 Data We Handle

### Data Provided to the Application

No personal data is requested or provided to the application. The repository contains only map assets (SVG and raster images).

### Data Generated or Collected by the Application

No personal data is generated or collected automatically by the application. The assets are static files.

### Data Received from Integrations

No personal data is received from integrations or third parties.

## 🧭 Processing and Use

The application processes no personal data. The repository provides static map assets for reference and browsing.

## 🗄️ Storage, Retention, and Deletion

No personal data is stored by the application. The repository contains only static map assets (SVG source files and raster exports). For self-hosted deployments, the instance operator controls storage, deletion, and backups of any web server logs or access records.

## 🔗 External Processing and Integrations

The application has no built-in external data transfer. GitHub hosts the repository and may process access logs per GitHub's privacy policy. Release assets are served from GitHub's infrastructure.

| Service or integration | Purpose | Data involved | Configuration or documentation |
|-----------------------|---------|---------------|--------------------------------|
| GitHub | Repository hosting and release asset delivery | Access logs (IP address, user agent, requested resource) | https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement |

## 🛡️ Data Protection and Security

The project maintainers do not collect, process, or store personal data through this repository. Static assets are served via GitHub Pages or direct repository access. For self-hosted deployments, the instance operator is responsible for updates, secrets, access controls, backups, network exposure, and log protection. The original maintainers are not responsible for changes, modifications, or privacy issues introduced by downstream forks.

## 🔄 Document Changes

Update this document when application data flows, storage, integrations, or deployment responsibilities change. The current version is published at https://github.com/hmlendea/map-of-nirn/blob/master/PRIVACY.md.

## 📬 Contact

For questions about application data handling, contact the project maintainers via GitHub issues. For a self-hosted instance, contact the instance operator. Include the repository URL and deployment context if applicable; do not send passwords, access tokens, or other secrets.