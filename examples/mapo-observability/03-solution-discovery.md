# Mapo Observability - Solution Discovery

- [Mapo Observability - Solution Discovery](#mapo-observability---solution-discovery)
  - [Overview](#overview)
  - [Tools / Approaches](#tools--approaches)
    - [🔎 OpenTelemetry](#-opentelemetry)
    - [🔎 NewRelic](#-newrelic)
    - [🔎 Datadog](#-datadog)
    - [🔎 Grafana Cloud](#-grafana-cloud)
    - [🔎 OpenObserve](#-openobserve)
    - [🔎 SigNoz](#-signoz)
    - [🔎 Etc.](#-etc)


## Overview
This document is a review of all the tools and approaches that could go into the final solution design. These could be vendor services, libraries, or even high-level design decisions (e.g. "Event-Driven paradigm vs Client-Server paradigm")

Software Architecture is all about tradeoffs, so for each option, the following should be documented:
- Description
- Factors
- Consequences
- References


This document should provide the team with all the information required to make architectural decisions, and produce an Architectural Decision Record. 

## Tools / Approaches

### 🔎 OpenTelemetry
Description:
- An open-source framework for observability. Supported by many vendors.
- Supports Logs, Metrics, and Traces.
- Can be implemented in many ways, usually by installing libraries in your application code, or running opentelemetry collector as an agent on your hardware.

Factors / Consequences:
- OpenTelemetry is a very widely-supported framework, almost all Observability vendors support ingest through the OTLP protocol.
- Using Otel is probably not going to be as seamless as using libraries and agents produced by that vendor for their own platform. 
- OpenTelemetry's libraries are pretty hard to learn and work with for people who've never seen them before. Initial development time will be much higher.

References:
- https://opentelemetry.io/

---

### 🔎 NewRelic
Description:
- NewRelic is an all-in-one managed observability platform, offered as a managed service

Factors / Consequences:
- Free Tier: NewRelic's free tier is generous. They allow 100GB of data ingest or free, and unlimited basic users. And no credit card required
- NewRelic supports all the basic Observablity signals: logs, metrics, and traces, and it has an Otel ingest endpoint
- Becuase it's fully-managed, there's no infrastructure to deploy
- People do complain about NewRelic's pricing beyond the free-tier. If Mapo were to scale, this could become pricey, but for now we'd be well under the free-tier limit.


References:
- Pricing / Feature charts: https://newrelic.com/pricing

---

### 🔎 Datadog
Description:
- Datadog is another all-in-one managed observability platform, direct competitor to NewRelic

Factors / Consequences:
- Free Tier: Datadog's free tier is not as good as NewRelic's, they can do some infra monitoring, but custom application-level monitoring is not ofered in the fre plan.
- For logs, Datadog charges $0.10 per GB, opposed to NewRelic's free 100GB
- In general, Datadog's pricing model seems very confusing, so I would be worried about suddenly getting larger-than-expected bills.


References:
- Pricing for Logs: https://www.datadoghq.com/pricing/?product=log-management#products

### 🔎 Grafana Cloud
Description:
- The managed versino of the grafana, prometheus, loki stack

Factors / Consequences:
- Free Tier: Also pretty generous, 10k metrics, 50Gb logs, 50GB traces, 14 day retention
- Very popular and mature, Prometheus especially is the reigning champ for self-hosted metrics.
- If we wanted to self-host, it is pretty complicated to setup. We'd have to self-host Grafana, Mimir/Prometheus, Loki, and Tempo


References:
- https://grafana.com/products/cloud/


---
### 🔎 OpenObserve
Description:
- A newer open source observability Platform, marketed as the next Elasticsearch

Factors / Consequences:
- Free Tier: 200GB free
- Full otel support
- Can be self-hosted too, but unlike Grafana, it's just 1 application, not 4. And they provide a docker container, so we could host it in the exact same way we do mapo itself.
- Newer than any of the other options mentioned.
- For self-hosting, uses cloud-native object-storage, not a database. Reducing overall deployment complexit


References:
- Pricing: https://openobserve.ai/pricing
- comparison with Grafana: https://openobserve.ai/blog/openobserve-vs-grafana

---

### 🔎 SigNoz
Description:
- Another open-source observablity platform that is OpenTelemetry native.

Factors / Consequences:
- Free Tier: None for their managed service, but if you host it yourself it's free
- Self-hosting is significantly more complex than OpenObserve, involves Zookeeper, Clickhouse, and several images.

References:
- Github: https://github.com/SigNoz/signoz


---
### 🔎 Etc.
Other tools I looked at briefly, but didn't proceed with for one reason or another:

- ELK: I've used this in the past, and it works, but self-hosting is a nightmare, and no free tier.
- Honeycomb.io: Seemed interesting, but it's more focused on Distributed tracing, and less on logs and metrics.
- Dynatrace: Seems more focused on enterprises, not side projects
- Instana: Owned by IBM