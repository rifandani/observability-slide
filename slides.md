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

///

Halo semuanya
Pada kesempatan ini, kita akan membahas "Observability"
Semoga kita semua bisa belajar sesuatu yang baru dan memahami pentingnya observability di sistem yang kompleks saat ini.
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

///

Seperti yang bisa kita lihat di Daftar Isi,
Ada beberapa topik yang akan kita bahas,
Pertama... *baca konten pertama sampai akhir*
Terakhir tapi tidak kalah penting... *baca konten terakhir*
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

///

Observability (kemampuan untuk mengamati) adalah praktik untuk dengan cepat mengetahui apa masalahnya dan sampai ke akar penyebab dengan memahami kondisi internal suatu sistem.

Manfaat:
- Pemahaman yang lebih baik tentang perilaku sistem, bagaimana komponen berbeda berinteraksi dan bagaimana perubahan di satu area memengaruhi area lain
- Troubleshooting yang lebih baik sehingga tim bisa dengan cepat mengidentifikasi dan menyelesaikan masalah di sistem kompleks
- Efisiensi dan produktivitas meningkat dengan menghemat waktu dan sumber daya
- Keunggulan strategis dengan menghubungkan kesehatan sistem ke hasil bisnis, mendorong tindakan yang actionable, dan memberikan pengalaman pengguna yang lebih baik

Site Reliability Engineering (SRE) adalah salah satu disiplin engineering yang fokus membuat sistem observable dan memastikan sistem andal serta efisien.
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

///

Monitoring adalah tindakan mengumpulkan, menganalisis, dan menyajikan log serta metrik untuk memantau fungsionalitas dan kesehatan sistem.
Tujuan utamanya adalah menemukan masalah yang sudah dikenali dan memberi tahu tim tentang masalah tersebut.

Monitoring melibatkan pengumpulan data points (metrik) seperti utilisasi CPU, penggunaan memori, disk I/O, dan latensi jaringan.
Pembacaan ini dibandingkan dengan level threshold yang sudah ditentukan.
Ketika threshold terlewati, alarm otomatis terpicu sehingga tim bisa merespons dengan cepat sebelum terjadi downtime atau degradasi.
Inilah mengapa monitoring bersifat reaktif, sementara observability bersifat proaktif.
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

///

Tiga pilar observability meliputi metrics, logs, dan traces.
Data points ini digabungkan untuk memberikan insight tentang kesehatan sistem kompleks dan membantu mendiagnosis serta menyelesaikan masalah performa dan fungsi keamanan.

- **Metrics** menyediakan data performa melalui pengukuran kuantitatif.
- **Logs** menawarkan catatan arsip peristiwa historis dan error dari suatu sistem.
- **Traces** menelusuri jalur request/transaksi untuk membantu mengidentifikasi akar penyebab.
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

///

Metrics adalah agregasi data numerik tentang infrastruktur atau aplikasi Anda selama periode waktu tertentu.
Contohnya: system error rate dan request rate untuk layanan tertentu.

Metrics memberikan gambaran high-level tentang kondisi suatu sistem.
Metrics menjadi fondasi alert karena berupa nilai numerik yang bisa dibandingkan dengan threshold yang sudah dikenal.
Alert berjalan terus di background dan terpicu ketika nilai berada di luar rentang yang diharapkan.
Ini biasanya tanda pertama bahwa sesuatu sedang terjadi dan tempat discovery pertama kali dimulai.
Metrics menunjukkan bahwa sesuatu sedang terjadi (anomali).
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

///

Tracing adalah metode untuk mengamati request, apa yang terjadi di setiap langkah atau aksi, dan berapa lama waktu yang dibutuhkan saat request menyebar/melintasi lingkungan terdistribusi.
Traces memberikan peta "di mana" sesuatu salah.
Tanpa tracing, menemukan akar penyebab masalah performa di sistem terdistribusi bisa sangat sulit.

Sebuah trace terdiri dari satu atau lebih span.
Span merepresentasikan unit kerja atau operasi.
Span pertama merepresentasikan root span dan setiap root span merepresentasikan request dari awal hingga akhir.
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

///

Logs menyediakan audit trail aktivitas dari satu proses yang menciptakan konteks informasi.
Logs berperan sebagai atomic events yang merinci apa yang terjadi di layanan aplikasi Anda.
Sementara metrics bersifat kuantitatif (numerik) dan terstruktur, logs bersifat kualitatif (tekstual) dan tidak terstruktur atau semi-terstruktur.
Logs memberikan detail lebih tinggi, tetapi dengan biaya volume data yang jauh lebih besar.
Logs memberi tahu Anda apa yang sedang terjadi pada aplikasi Anda.
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

///

Agar suatu sistem observable, sistem tersebut harus — istilahnya — "instrumented".

Pertama, Anda punya infrastruktur atau aplikasi yang ingin diamati.
Anda mengumpulkan data darinya dan mengirimkannya ke observability backend pilihan Anda.
Lalu hubungkan backend ke front end visualisasi tempat Anda bisa query dan memakai data yang dibutuhkan.

Jenis data yang paling umum dikumpulkan untuk observability adalah metrics, logs, dan traces (telemetry data).
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

///

Di sinilah OTel berperan.
OTel adalah framework observability open source dan standar terbuka untuk memfasilitasi proses generate, collect, manage (agregasi, filtering, processing, dll.), dan export telemetry data (metrics, logs, dan traces).
Proses ini disebut instrumentation.
-->

---
transition: slide-left
layout: center
---

<img class="object-cover" alt="Otel Lgtm" src="/otel-lgtm.png" />

<!--
The open source example of this is using otel-lgtm by grafana

///

Contoh open source-nya adalah menggunakan otel-lgtm dari Grafana.
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
transition: slide-left
layout: center
class: text-center
---

# Hidden Cost of Telemetry

https://blog.platformatic.dev/the-hidden-cost-of-context

<!--
Ok, so "How much performance do we sacrifice for observability?"
https://github.com/platformatic/async-local-storage-perf-node-24

///

Oke, jadi "Seberapa banyak performa yang kita korbankan untuk observability?"
https://github.com/platformatic/async-local-storage-perf-node-24
-->

---
transition: slide-left
layout: center
class: text-center
---

# Logging Sucks

https://loggingsucks.com/

↓

https://www.evlog.dev/start/introduction

<!--
Common logging practice breaks in distributed systems.
Your logs are lying to you — not maliciously. They're not equipped to tell the truth.

///

Praktik logging umum gagal di sistem terdistribusi.
Log Anda "bohong" — bukan karena jahat. Log tidak dirancang untuk memberi kebenaran.
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
