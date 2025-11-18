# Phase 9 — Splunk SOC Lab with Windows Firewall Logs
In this lab, I set up Splunk in Docker on Windows 11, ingested Windows sample logs and firewall logs, and practiced SPL searches along with auto and manual field extraction. 🚀
---

# Start Splunk in Docker
I got Splunk running in a Docker container with persistent storage to make sure I didn’t lose any previous uploads. 🐳

<img width="811" height="647" alt="uQC7QCC" src="https://github.com/user-attachments/assets/65401608-5b74-4b42-8099-324c18655c59" />

---

<img width="835" height="605" alt="6QXqp09" src="https://github.com/user-attachments/assets/00057746-3f2e-45a5-86d9-4d2b13fbab73" />

>- 🖥️ Docker container — runs Splunk Enterprise on Windows  
>- 💾 Persistent volumes — keeps logs and settings safe across restarts  
>- 🌐 Ports 8000/9997/8089 — used for Web UI, data forwarding, and management  

---

# Enable Windows Firewall Logging
I configured Windows Firewall to log allowed connections and generated test traffic to populate the log. 🔥

<img width="833" height="668" alt="WG8gCrU" src="https://github.com/user-attachments/assets/33071c50-4808-440f-83b6-15fa0e537f96" />

---

<img width="810" height="312" alt="Ambs0Fc" src="https://github.com/user-attachments/assets/9fbaa4ab-56dd-42c1-90aa-805944e0e998" />

>- 🛡️ Set-NetFirewallProfile — PowerShell cmdlet to enable logging  
>- 📄 pfirewall.log — Windows Firewall log file  
>- 📶 Ping test — generates firewall events for ingestion  

---

# Upload Windows Sample Log
I uploaded a pre-existing sample log to Splunk Web and verified that events were ingested successfully. 📂

<img width="677" height="611" alt="hNjK5zz" src="https://github.com/user-attachments/assets/0af59c6e-502f-4a75-aa1c-f5bcb0b01d9d" />

---

<img width="978" height="313" alt="MexGGjK" src="https://github.com/user-attachments/assets/70c189c6-0bc1-4322-98cc-735206b1ed76" />

>- ➕ Splunk Web Add Data → Upload — method to import logs  
>- 📝 Source Type (syslog) — defines the log format  
>- 📦 Index (os_logs) — Splunk storage container for events  

---

# Upload Windows Firewall Log
I copied the firewall log to a user folder to avoid permission issues, then uploaded it to Splunk and verified that events appeared. 📥

<img width="831" height="98" alt="uzHEtsQ" src="https://github.com/user-attachments/assets/2af92d8e-3a0a-4397-aedf-7a20e128e19c" />

>- 📂 Copy-Item (PowerShell) — moves log to accessible folder  
>- ➕ Splunk Web → Add Data → Upload — uploads log into Splunk  
>- 📝 Source Type (windows_firewall) — identifies firewall events  
>- 📦 Index (os_logs) — stores firewall events alongside sample logs  

---

# Validate Logs in Splunk
I checked that both the sample logs and firewall logs were ingested correctly, and verified sourcetypes and indexes to avoid errors. 🔍

<img width="1029" height="235" alt="Yj71o3f" src="https://github.com/user-attachments/assets/e2da1c35-9b8e-4063-a849-836a90f593bf" />

---

<img width="549" height="308" alt="zpByzJi" src="https://github.com/user-attachments/assets/65298e70-28e7-4e06-baf6-5d74c376f418" />

---

<img width="723" height="203" alt="qpYVPKO" src="https://github.com/user-attachments/assets/4cc27ca6-17be-488a-9713-9004a8aef479" />

>- 🗂️ index/os_logs — Splunk index containing logs  
>- 📝 sourcetype — identifies log format  
>- 📊 Search & Reporting — Splunk app to run queries  
>- ⚠️ Troubleshooting SPL — ensures logs appear even if sourcetype auto-assigned  

---

# Field Extraction
I practiced both auto and manual field extraction to parse the logs into usable fields for analysis. ✂️

<img width="981" height="118" alt="mOVuuTw" src="https://github.com/user-attachments/assets/90484348-466d-4789-b242-b2e286f8cefe" />

>- 🤖 Auto Extraction (GUI) — highlights fields visually  
>- 🔧 Manual Extraction (rex command) — uses SPL regex to extract fields  
>- 📋 table command — organizes extracted fields for viewing  

---

# Verify Everything
I ran SPL searches to confirm that all logs were counted correctly and that firewall actions (ALLOW/DROP) could be analyzed. ✅

<img width="999" height="288" alt="iQ5JVYn" src="https://github.com/user-attachments/assets/73b63de0-6276-4629-8d53-a5d114afe044" />

>- 📊 stats count — validates events are present  
>- 🔍 Optional stats by action — ALLOW vs DROP analysis  
>- 📈 Ensures lab data is ready for dashboards or threat hunting  
