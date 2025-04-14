# 🛡️ Real-World Permissions Example (Defense Contractor Use Case)

## 🧱 Scenario

You are a Linux systems engineer at a defense contractor. There are three teams:

- `engineer` – Writes and deploys scripts
- `analyst` – Reviews logs and alerts
- `officer` – Final sign-off and high-security data access

Each team must have **restricted but efficient access** to their own resources.

---

## 🗂️ 1. Setup Shared Directories for Teams

```bash
sudo mkdir -p /opt/defense/{scripts,logs,briefings}
sudo groupadd engineer
sudo groupadd analyst
sudo groupadd officer
sudo chgrp engineer /opt/defense/scripts
sudo chgrp analyst /opt/defense/logs
sudo chgrp officer /opt/defense/briefings
sudo chmod 770 /opt/defense/scripts       # engineers only
sudo chmod 750 /opt/defense/logs          # readable by analysts and root
sudo chmod 770 /opt/defense/briefings     # officers only


---


