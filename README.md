# Phase 9 — Splunk SOC Lab with Windows Firewall Logs
In this lab, I set up Splunk in Docker on Windows 11, ingested Windows sample logs and firewall logs, and practiced SPL searches along with auto and manual field extraction. 🚀
---

# Start Splunk in Docker
I got Splunk running in a Docker container with persistent storage to make sure I didn’t lose any previous uploads. 🐳

- 🖥️ Docker container — runs Splunk Enterprise on Windows  
>- 💾 Persistent volumes — keeps logs and settings safe across restarts  
>- 🌐 Ports 8000/9997/8089 — used for Web UI, data forwarding, and management  

---

# Enable Windows Firewall Logging
I configured Windows Firewall to log allowed connections and generated test traffic to populate the log. 🔥

>- 🛡️ Set-NetFirewallProfile — PowerShell cmdlet to enable logging  
>- 📄 pfirewall.log — Windows Firewall log file  
>- 📶 Ping test — generates firewall events for ingestion  

---

# Upload Windows Sample Log
I uploaded a pre-existing sample log to Splunk Web and verified that events were ingested successfully. 📂

>- ➕ Splunk Web Add Data → Upload — method to import logs  
>- 📝 Source Type (syslog) — defines the log format  
>- 📦 Index (os_logs) — Splunk storage container for events  

---

# Upload Windows Firewall Log
I copied the firewall log to a user folder to avoid permission issues, then uploaded it to Splunk and verified that events appeared. 📥

>- 📂 Copy-Item (PowerShell) — moves log to accessible folder  
>- ➕ Splunk Web → Add Data → Upload — uploads log into Splunk  
>- 📝 Source Type (windows_firewall) — identifies firewall events  
>- 📦 Index (os_logs) — stores firewall events alongside sample logs  

---

# Validate Logs in Splunk
I checked that both the sample logs and firewall logs were ingested correctly, and verified sourcetypes and indexes to avoid errors. 🔍

>- 🗂️ index/os_logs — Splunk index containing logs  
>- 📝 sourcetype — identifies log format  
>- 📊 Search & Reporting — Splunk app to run queries  
>- ⚠️ Troubleshooting SPL — ensures logs appear even if sourcetype auto-assigned  

---

# Field Extraction
I practiced both auto and manual field extraction to parse the logs into usable fields for analysis. ✂️

>- 🤖 Auto Extraction (GUI) — highlights fields visually  
>- 🔧 Manual Extraction (rex command) — uses SPL regex to extract fields  
>- 📋 table command — organizes extracted fields for viewing  

---

# Verify Everything
I ran SPL searches to confirm that all logs were counted correctly and that firewall actions (ALLOW/DROP) could be analyzed. ✅

>- 📊 stats count — validates events are present  
>- 🔍 Optional stats by action — ALLOW vs DROP analysis  
>- 📈 Ensures lab data is ready for dashboards or threat hunting  
