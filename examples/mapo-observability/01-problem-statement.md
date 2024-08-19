# Mapo Observabiity - Problem Statement

- [Mapo Observabiity - Problem Statement](#mapo-observabiity---problem-statement)
  - [Overview](#overview)
  - [Problem Description](#problem-description)
    - [👤 User Persona - Mapo Operations Support](#-user-persona---mapo-operations-support)
    - [👤 User Persona - Mapo Developer](#-user-persona---mapo-developer)
    - [👤 User Persona - Mapo Product Manager](#-user-persona---mapo-product-manager)


## Overview
This document outlines the problems that initiated the creation of this project. 
It documents individual problem statements, broken down by user persona. 

You could format your problem descriptions like user-stories ("As an X, I would like to X, so that I can X, but X"), but often this data comes from user-interviews, and in that case it's best to just record exactly what was said.


## Problem Description

### 👤 User Persona - Mapo Operations Support
- The only way for me to see api logs is to SSH into a VM run `docker logs`.
- I want an easy way to set alerts, based on either logs, or metric thresholds.
- I have no way of getting notified when anything happens.
- Users have no way of submitting bug tickets / incidents.

### 👤 User Persona - Mapo Developer
- The only way for me to see app logs is to SSH into a VM run `docker logs`.
- There is no way at all for me to see logs that come from the user's browser.
- If there's a bug that crashes the application, I would like to see logs from just before the crash, but `docker logs` doesn't show those logs. It only shows logs for the currently running application.
- I want to know exactly how many users a single VM can handle (in requests per minute), but I dont' have any metrics from real instances that are serving users in production. I also don't know how many requests per minute I get in prod.


### 👤 User Persona - Mapo Product Manager
- I have no real way to tell if the system is healthy at a glance. I need to actually logon to mapo to even know it's running.

- I want to see occurence of crashes and errors, so that I can better prioritize bugs and gauge their impact, but I have none of that information right now.
