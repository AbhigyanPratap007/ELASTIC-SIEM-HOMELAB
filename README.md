# ELASTIC SIEM HOMELAB
Elastic SIEM Home Lab — Threat Simulation & Detection Engineering
📌 Overview

This project sets up an Elastic SIEM home lab using Elastic Cloud and a Kali Linux attacker machine. The aim was to simulate real-world adversary activity, write custom detection rules, and validate SOC workflows end-to-end — from log collection to email alerting and triage.

By recreating attacker behavior in a controlled lab, the project demonstrates detection engineering, SOC analysis, and incident response readiness.

⚙️ Lab Setup

Elastic Cloud Deployment — hosted Elasticsearch + Kibana.

Elastic Agent Enrollment — Elastic Defend installed on endpoints to collect process, authentication, and network telemetry.

Kali Linux Attacker Machine — used for simulating scans, brute force, and exploitation.

Alerting & Notifications — configured rule-based alerts with email delivery to analyst inbox.

🎯 Objectives

Deploy a fully functional Elastic SIEM environment.

Generate attacker activity and ensure visibility in Elastic Defend telemetry.

Write custom detection rules and map them to MITRE ATT&CK techniques.

Validate SOC workflows by triggering alerts and email notifications.

🔍 Detection Rules Implemented

Nmap Scan Detection

Triggered on reconnaissance activity from Kali (e.g., port scanning).

MITRE ATT&CK: T1046 — Network Service Scanning.

Suspicious Process Execution

Detected processes like netcat and curl launched from unexpected contexts.

MITRE ATT&CK: T1059 — Command and Scripting Interpreter.

Brute-Force Authentication

Alerted on repeated login failures followed by a successful logon.

MITRE ATT&CK: T1110 — Brute Force.

Correlation Rule — Privilege Escalation Attempt

Linked multiple failed logons (noise) with subsequent privileged logon events.

Helped distinguish between random failed logins and true escalation attempts.

📊 Results

Generated 100+ alerts across reconnaissance, brute force, and privilege escalation scenarios.

Successfully detected port scans, suspicious processes, and brute-force logins from attacker machine.

Reduced false positives by tuning rules (whitelisting expected admin activity).

Configured email notifications — rules delivered alerts directly to analyst inbox, proving real SOC workflow.

Visualized events in Kibana dashboards, aiding quick triage.
