---
# You can also start simply with 'default'
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: Observability
# titleTemplate for the webpage, `%s` will be replaced by the slides deck's title
titleTemplate: "%s - Observability"
info: |
  ## Observability
# enable presenter mode, can be boolean, 'dev' or 'build'
presenter: "dev"
# download: true
# exportFilename: 'observability'
highlighter: shiki
lineNumbers: true
# apply unocss classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
transition: slide-left
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# take snapshot for each slide in the overview
overviewSnapshots: true
---

# Observability (o11y)

<!--
Hello everyone
On this opportunity, we will discuss "Observability"
Hopefully, we can all learn something new and understand the importance of observability in today's complex systems.
-->

---
transition: fade-out
---

# Table of Contents

<Toc :style="{ columnCount: 2, columnGap: '5rem', height: '100%' }" />

<!--
As we all can see the Table of Contents,
There are few topics that we are gonna discuss,
First... *read first content to the end*
Last but not least... *read last content*
-->

---
transition: slide-left
layout: center
---

# Observability (o11y)

<img class="object-cover h-80" alt="Observability" src="https://arize.com/wp-content/uploads/2021/05/observability-iceberg-2.png" />

<!--
Observability (an ability to observe) is the practice of quickly finding out what the problem is and getting to the root cause by understanding the internal state of a system.

Benefits:
- Better understanding of system behavior how different components interact and how changes in one area affect others
- Improved troubleshooting so that teams can quickly identify and resolve issues in complex systems 
- Increased efficiency and productivity by saving time and resources
- Strategic advantage by linking system health to business outcomes, driving actionable actions and delivering better user experience

Site Reliability Engineering (SRE) is one of the engineering disciplines that focuses on making systems observable and to ensure they're reliable and efficient.
-->

---
transition: slide-left
layout: center
---

<img class="object-cover h-100" alt="Monitoring vs Observability" src="https://cdn.prod.website-files.com/64b7ba4dc9375b7b74b2135e/67d81950378ffdda21c51fa6_1.jpg" />

<!--
Monitoring is the act of collecting, analyzing, and presenting some logs and metrics to monitor the functionality and health of systems. 
The main goal is to find recognized problems and notifying teams of problems.

Monitoring involves the gathering of data points (metrics) like CPU utilization, memory usage, disk I/O, and network latency. 
These readings are contrasted to predetermined threshold levels.
When a threshold is crossed, it automatically triggers alarms, allowing teams to quickly respond before downtime or degradation occurs.
This is why monitoring is a reactive approach, while observability is a proactive approach.
-->

---
transition: slide-up
layout: center
---

# Three Pillars of Observability

<img class="object-cover h-80" alt="Three Pillars of Observability" src="https://www.eginnovations.com/blog/wp-content/uploads/2023/04/Three-Pillars-03.webp" />

<!--
The three pillars of observability include metrics, logs, and traces. 
These data points combine to provide insights into the health of complex systems and can help diagnose and resolve performance issues and security functions.

- **Metrics** provide performance data through quantitative measurements.
- **Logs** offer archived records of historical events and errors of a system.
- **Traces** request/transaction paths to help identify root causes.
-->

---
transition: slide-up
layout: center
---

# Metrics

<img class="object-cover h-100" alt="Metrics" src="https://grafana.com/media/docs/tempo/intro/exemplar-metric-totrace.png" />

<!--
Metrics are aggregations over a period of time of numeric data about your infrastructure or application. 
Examples include: system error rate, and request rate for a given service.

Metrics provide a high level picture of the state of a system. 
Metrics are the foundation of alerts because metrics are numeric values and can be compared against known thresholds. 
Alerts constantly run in the background and trigger when a value is outside of an expected range. 
This is typically the first sign that something is going on and are where discovery first starts.
Metrics indicate that something is happening (anomaly).
-->

---
transition: slide-up
layout: center
---

# Traces

<img class="object-cover h-100" alt="Traces" src="https://encore.dev/assets/blog/tracing-data-model.png" />

<!--
Tracing is a method of observing requests, what happens at each step or action and how long does it take as they propagate / move through distributed environments.
Traces provide the map "the where" something is going wrong. 
Without tracing, finding the root cause of performance problems in a distributed system can be challenging.

A trace is made of one or more spans.
A span represents a unit of work or operation.
The first span represents the root span and each root span represents a request from start to finish. 
-->

---
transition: slide-left
layout: center
---

# Logs

<img class="object-cover h-110" alt="Logs" src="https://grafana.com/media/docs/tempo/intro/loki-trace-to-logspng.png" />

<!--
Logs provide an audit trail of activity from a single process that create informational context. 
Logs act as atomic events, detailing what’s occurring in the services in your application. 
Whereas metrics are quantitative (numeric) and structured, logs are qualitative (textual) and unstructured or semi-structured. 
They offer a higher degree of detail, but also at the expense of creating significantly higher data volumes. 
Logs let you know what’s happening to your application.
-->

---
transition: slide-up
layout: center
---

# OpenTelemetry (OTel)

<img class="object-cover h-100" alt="Open Telemetry" src="/otel.png" />

<!--
To make a system observable, it must be - quote unquote "instrumented". 

First, you have your infrastructure or applications that you want to observe.
You'll collect data from it and send the data to the observability backend of your choosing.
Then connect the backend to a visualization front end where you can query and use the data that you're interested in.

The most common types of data collected for observability are metrics, logs, and traces (telemetry data).
-->

---
transition: slide-up
layout: center
---

<img class="object-cover" alt="Open Telemetry 2" src="/otel-2.png" />

<!--
This is where OTel comes in.
OTel is an open source observability framework and open standard to facilitate the process of generating, collecting, managing (aggregating, filtering, processing, etc), and exporting telemetry data (metrics, logs, and traces).
This process is known as instrumentation.
-->

---
transition: slide-left
layout: center
---

<img class="object-cover" alt="Otel Lgtm" src="/otel-lgtm.png" />

<!--
The open source example of this is using otel-lgtm by grafana 
-->

---
transition: slide-left
layout: center
---

# OpenTelemetry

Demo

<!--
-->

---
transition: slide-up
layout: center
---

# Logging Sucks

TODO

<!--
-->

---
layout: center
class: text-center
---

# Thank You 🙏

<PoweredBySlidev />

<div class="abs-br m-6 flex gap-2">
  <a href="https://github.com/rifandani/observability-slide" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl icon-btn !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>
