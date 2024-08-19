# Mapo Observabiity - Requirements

- [Mapo Observabiity - Requirements](#mapo-observabiity---requirements)
  - [Overview](#overview)
  - [Functional Requirements](#functional-requirements)
    - [👤 User Persona - Mapo Operations Support](#-user-persona---mapo-operations-support)
    - [👤 User Persona - Mapo Developer](#-user-persona---mapo-developer)
    - [👤 User Persona - Mapo Product Manager](#-user-persona---mapo-product-manager)
  - [Non-Functional Requirements](#non-functional-requirements)


## Overview
This document outlines the requirements of this project, broken down into functional and non-functional

Functional requirements are usually expressed as a user-story for a defined user-persona, following the format:

- "I want to (be able to) \<action> so that I can \<business action>"

Non Functional requirements don't have a specific format. They include things like form factor, latency requirements, accessibility, and anything else that would constrain the problem space.

## Functional Requirements

### 👤 User Persona - Mapo Operations Support
- I want to see all logs coming from the system, and do basic log search, so that I can triage and debug issues.
- I want to create dashboards, so that I can aggregate a bunch of important metrics into a single screen.
- I want to create alerts for metrics, so that I can monitor important metrics, and know if they reach a threshold.

### 👤 User Persona - Mapo Developer
- I want to easily push logs and metrics to the Observability system.
- I want to track all my calls to 3rd party services, so that I can identify when some dependency system is having issues.
- I want to search through logs, looking for specific keywords, so that I can find instances of a known issue (assuming I've logged something about that issue in code).
- I want to see hardware metrics for Mapo infrastructure, so that I can right-size the infrastructure to save money.


### 👤 User Persona - Mapo Product Manager
- I want to see basic usage metrics, like number of users per day, so that I can tell whether people are actually using the application

- I want to be able to query for occurence rate of specific errors, so taht I can prioritize bugs and issues.

## Non-Functional Requirements

- Cost. This solution shouldn't be too expensive. Mapo doesn't make any money, so ideally, the observablity stack would be cheap or free.

- Ease. This solution also shouldn't be too hard to maintain. I don't want to have to setup observability for my observability.
