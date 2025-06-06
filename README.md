# 🔐 Task 4 - Linux UFW Firewall Configuration

## 🎯 Objective

Demonstrate basic firewall configuration and traffic control using **UFW (Uncomplicated Firewall)** on Kali Linux.

---

## 💪 Tools Used

* **Kali Linux**
* **UFW (Uncomplicated Firewall)**
* **Systemd (for managing SSH)**
* **Netcat & Telnet (for testing port access)**

---

## 🧪 Actions Performed

### ✅ 1. Enabled UFW

Used the following commands:

```bash
sudo ufw enable
sudo ufw status verbose
```

📸 `ufw-enable.png`

---

### 🚫 2. Blocked Inbound Traffic on Telnet Port (23)

Command used:

```bash
sudo ufw deny 23
```

Verified denial using:

```bash
telnet localhost 23
```

📸 `ufw-port-23-denial.png` – Output shows connection refused (as expected).

---

### ✅ 3. Allowed Inbound SSH Traffic (Port 22)

Commands used:

```bash
sudo ufw allow 22
sudo systemctl start ssh
nc -vz localhost 22
```

📸 `ufw-port-22-allowed.png` – Output shows connection to port 22 succeeded.

---

### 🔍 4. Verified Rule List with UFW

Command used:

```bash
sudo ufw status numbered
```

📸 `ufw-status.png` – Confirms that port 23 is denied and port 22 is allowed.

---

## 🗈 Screenshot Summary

| Filename                  | Description                           |
| ------------------------- | ------------------------------------- |
| `ufw-enable.png`          | UFW successfully enabled              |
| `ufw-port-23-denial.png`  | Port 23 (Telnet) connection denied    |
| `ufw-port-22-allowed.png` | Port 22 (SSH) connection allowed      |
| `ufw-status.png`          | All firewall rules listed numerically |

---

## ✅ Outcome

Successfully demonstrated firewall rule management on Linux using UFW:

* Denied Telnet traffic on port 23 (for security).
* Allowed SSH traffic on port 22 (for remote access).
* Validated rules through system tools and command-line tests.
