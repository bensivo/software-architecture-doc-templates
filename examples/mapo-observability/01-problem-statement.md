# Mapo Observabiity - Problem Statement

- [Mapo Observabiity - Problem Statement](#mapo-observabiity---problem-statement)
  - [Overview](#overview)
  - [Problem Description](#problem-description)
    - [👤 User Persona - Mapo Developer](#-user-persona---mapo-developer)
    - [👤 User Persona - Mapo Product Manager](#-user-persona---mapo-product-manager)


## Overview
This document outlines the problems that initiated the creation of this project. 
It documents individual problem statements, broken down by user persona and action.


Each problem statement includes: 
- A user persona
- An action that that user is trying to do
- Something that maeks that action difficult or impossible

A problem statement here follows the format: "To \<business action>, I want to \<technical action>, But \<problem>"


## Problem Description

### 👤 User Persona - Mapo Developer
- To debug mapo-api, I want to see logs. The only way for me to see app logs is to SSH into a VM run `docker logs`.

- To debug mapo-webapp, I want to see browser logs,but there is no way at all for me to see logs that come from the user's browser.

- To investigate crashes for mapo-api, I would like to see logs from just before the crash, but `docker logs` doesn't show those logs. It only shows logs for the currently running application.

- To save on VM cost, I want to know exactly how many users a single VM can handle (in requests per minute), but I dont' have any metrics from real instances that are serving users in production. I also don't know how many requests per minute I get in prod.


### 👤 User Persona - Mapo Product Manager
- To understand the health of our system at a glance. Right now, the only way for me to know everything is okay is to actaully login to MApo myself. Then I just assume if it works for me, then it works for everyone.

- To better prioritize bugs that pop up in Mapo, I want to see occurence of crashes and errors, but I have none of that information right now.

- To prioritize features in Mapo (esp. related to browser support, etc.), I want to see metrics related to user's location, browser types, etc., but I have none of that right now.

  - NOTE: this is arguably analytics, not observability