# REAPER

## Repository Exposure Analysis Platform for Evaluation & Reconnaissance

REAPER is a high-performance repository intelligence platform written in Go that analyzes public repositories, commit history, pull requests, issues, and security advisories to identify exposed credentials, security risks, and repository intelligence signals.

The project combines detector-based analysis, entropy scoring, repository intelligence, advisory correlation, and concurrent scanning to provide meaningful context around discovered exposures.

---

## Features

* Concurrent repository analysis
* Credential and token detection
* Entropy-based exposure identification
* Pull request analysis
* Issue and discussion inspection
* Commit history intelligence
* Security advisory correlation
* CSV and JSONL reporting
* Stateful repository tracking
* Continuous monitoring mode
* Rate-limit aware architecture
* Configurable worker pools
* Email deduplication and filtering
* Repository intelligence collection
* Real-time reporting pipeline

---

## Architecture

REAPER consists of several major components:

### Repository Discovery Engine

Discovers and queues repositories for analysis based on configurable criteria.

### Analysis Engine

Processes source code, pull requests, issues, commits, and repository metadata.

### Detection Framework

Uses pattern matching and entropy analysis to identify potential exposures.

### Intelligence Layer

Correlates findings with repository metadata and advisory information.

### Reporting Pipeline

Exports findings to CSV and JSONL formats for further analysis.

---

## Technology Stack

* Go
* GitHub REST API
* GitHub GraphQL API
* Concurrent Worker Pools
* Entropy Analysis
* CSV Reporting
* JSONL Reporting

---

## Installation

### Prerequisites

* Go 1.21+
* Git
* GitHub Personal Access Token

Verify Go installation:

```bash
go version
```

### Clone Repository

```bash
git clone https://github.com/YOUR_USERNAME/REAPER.git
cd REAPER
```

### Install Dependencies

```bash
go mod tidy
```

### Build

```bash
go build -o reaper .
```

### Configure Authentication

```bash
export GITHUB_TOKEN="your_token_here"
```

---

## Quick Start

Analyze a single repository:

```bash
./reaper -repo https://github.com/owner/repository -verbose
```

Analyze multiple repositories:

```bash
./reaper \
  -repo https://github.com/owner/repo1 \
  -repo https://github.com/owner/repo2 \
  -verbose
```

Run continuous monitoring:

```bash
./reaper \
  -workers=20 \
  -continuous \
  -sleep-minutes=10 \
  -verbose
```

---

## Command Line Flags

| Flag             | Description                  |
| ---------------- | ---------------------------- |
| -workers         | Number of concurrent workers |
| -verbose         | Enable detailed output       |
| -continuous      | Continuous monitoring mode   |
| -sleep-minutes   | Delay between cycles         |
| -since-days      | Repository age filter        |
| -scan-prs        | Analyze pull requests        |
| -scan-issues     | Analyze issues               |
| -scan-commits    | Analyze commit history       |
| -scan-advisories | Analyze advisories           |
| -entropy         | Enable entropy analysis      |
| -min-stars       | Minimum repository stars     |
| -repo            | Single repository target     |
| -repo-list       | Repository list file         |
| -output          | Output directory             |

---

## Output

Generated reports are stored inside:

```text
output/
├── reaper_exposures.jsonl
├── reaper_report_TIMESTAMP.csv
├── advisories.jsonl
└── scanned_repositories.txt
```

---

## Detection Categories

### Cloud Credentials

* AWS Access Keys
* AWS Secret Keys
* Google API Keys
* Azure Connection Strings
* Alibaba Cloud Credentials
* DigitalOcean Tokens

### Platform Tokens

* GitHub Tokens
* GitLab Tokens
* Docker Hub Tokens
* NPM Tokens
* Pulumi Tokens

### Communication Platforms

* Slack Tokens
* Discord Bot Tokens
* Telegram Bot Tokens

### Payment & SaaS Platforms

* Stripe Keys
* Twilio Keys
* SendGrid Keys
* OpenAI Keys

### Database Credentials

* PostgreSQL
* MySQL
* MongoDB
* Redis

### Cryptographic Material

* RSA Private Keys
* SSH Private Keys
* EC Private Keys

### Generic Credentials

* Passwords
* API Keys
* Email Addresses
* JWT Tokens

---

## Roadmap

* [ ] Web Dashboard
* [ ] SQLite Backend
* [ ] HTML Reporting
* [ ] Risk Scoring Engine
* [ ] Repository Reputation Scoring
* [ ] SARIF Export
* [ ] GitLab Support
* [ ] Bitbucket Support
* [ ] Slack Notifications
* [ ] REST API
* [ ] Web Interface

---

## Educational Goals

REAPER was developed to explore:

* Go concurrency
* Security engineering
* Detection engineering
* API integration
* Repository intelligence
* Exposure discovery workflows
* Large-scale analysis systems

---

## Disclaimer

REAPER is intended for educational purposes, defensive security research, and authorized security assessments only.

Users are responsible for ensuring compliance with applicable laws, platform policies, and terms of service.

---

## License

This project is provided for educational and research purposes. Review all applicable platform policies before use.
