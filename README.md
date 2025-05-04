#  NmapBuddy - Automated Port & Vulnerability Scanner

**Author:** Tamieka Horne  
**Date Started:** 4/27/2025

---

##  Table of Contents

1. [Overview](#overview)
2. [Setup](#setup)
3. [Timestamp + Logging](#timestamp--logging)
4. [Target Selection](#target-selection)
5. [Nmap Scan Execution](#nmap-scan-execution)
6. [Output & Results](#output--results)
7. [Project Structure](#project-structure)
8. [Future Features](#future-features)

---

##  Overview

NmapBuddy is a Python-based tool that automates port scanning and basic vulnerability detection using Nmap.  
It streamlines manual security assessments by allowing users to quickly identify open ports and potential vulnerabilities on target systems or networks.

---

## ⚙️ Setup

To get started with NmapBuddy, follow these steps:

```bash
1. Clone this repository
   git clone https://github.com/Thorne10/NmapBuddy.git
   cd NmapBuddy

2. Create and activate a virtual environment
   python -m venv scanner_env
   source scanner_env/bin/activate   # For Mac/Linux
   scanner_env\Scripts\activate      # For Windows

3. Install required dependencies
   pip install -r requirements.txt

4. Launch the project
   jupyter notebook

## 🕒 Logging
Every scan is logged automatically in `scan_log.txt`, located in the main project directory. Logs include:

- The target host
- Output format chosen (text or JSON)
- A timestamp of when the scan was completed

This helps track scanning activity over time and supports record-keeping for compliance or analysis.

## 🎯 Target Selection
NmapBuddy accepts multiple targets in a single input session. When prompted, you can enter one or more IP addresses or domain names separated by spaces:


The tool will loop through each target and allow individual output format selection per host.

## Nmap Scan Execution
The core of the project uses the `python-nmap` library to:

- Scan ports in the range 20–100
- Identify open ports and their associated services
- Return scan data in a structured format

Scans are performed with a timeout-safe method and basic error handling to skip invalid or unreachable targets.

## Future Implementations

While the current version of nmapBuddy performs basic port and service scanning effectively, several enhancements could further increase its functionality and value:

CSV/JSON Export Options
Add built-in options to export scan results directly to .csv or .json formats for easier integration with other tools or data analysis platforms.

Web Interface or Dashboard
Create a lightweight web interface using Flask or Streamlit to allow non-technical users to run scans and view results in a more user-friendly way.

OS Detection and Vulnerability Mapping
Integrate advanced Nmap flags like -O (OS detection) and tie results into a vulnerability database (e.g., CVEs) for basic risk scoring.

Automated Scheduled Scans
Implement the ability to schedule recurring scans using cron jobs or Windows Task Scheduler, with optional email notifications upon completion.

Input Validation and Error Handling
Improve robustness by adding input validation, custom error messages, and recovery options for common issues like network errors or invalid targets.

Multi-Target Scanning
Extend the tool to support scanning multiple IPs or domains from a list, looping through them automatically and saving results separately.