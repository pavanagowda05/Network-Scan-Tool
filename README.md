# 🔧 Enhanced Network Scan Tool

A powerful and automated Python-based tool for network scanning, port analysis, OS fingerprinting, and HTML report generation using **Nmap**. This tool is ideal for **system administrators**, **network engineers**, and **security analysts** looking to audit, monitor, and analyze networks efficiently.

---

## 🔁 Project Overview

| Feature          | Description                                                    |
| ---------------- | -------------------------------------------------------------- |
| Tool Type        | Python script with CLI interface                               |
| Primary Function | Network Scanning, Port Detection, OS Identification, Reporting |
| Technology Stack | Python 3, Nmap, SMTP                                           |
| Output Format    | HTML Report                                                    |
| Email Support    | Yes, automated via SMTP                                        |
| Scanning Modes   | Single IP or CIDR Range                                        |
| Ideal Use Cases  | Network audits, vulnerability checks, scheduled scans          |

---

## 🔧 Features

* ✅ **Dual Scanning Modes**: Scan a single device or an entire CIDR subnet.
* 🔎 **TCP SYN, OS & Version Detection**: Uses `-sS`, `-O`, `-sV` flags for stealth scans.
* 📈 **HTML Report Generation**: Device info, open ports, services in tabular format.
* 📧 **Automated Email Reporting**: SMTP-based email delivery of scan results.
* ⚙️ **Flexible Configuration**: Customizable SMTP, timeouts, and Nmap options.
* ⚠️ **Error Handling**: Graceful fallback on missing tools, auth errors, and unreachable targets.

---

## 🔢 System Requirements

| Requirement      | Details                                           |
| ---------------- | ------------------------------------------------- |
| OS               | Linux (Preferred), Windows, macOS                 |
| Python Version   | 3.6+ (Python 2.x not supported)                   |
| RAM              | Minimum 2 GB (more for large ranges)              |
| Nmap             | Must be installed and in PATH                     |
| Python Libraries | `python-nmap`, `smtplib`, `email.mime` (built-in) |

```bash
# Check Python version
python3 --version

# Install dependencies
sudo apt install nmap python3-pip
pip3 install python-nmap
```

---

## 🚀 Installation & Setup

### ① Install Python

* [Download Python](https://www.python.org/)

### ② Install Nmap

```bash
# Linux
sudo apt update && sudo apt install nmap

# macOS
brew install nmap

# Windows
Download and install from https://nmap.org/download.html
```

### ③ Install Python Libraries

```bash
pip install python-nmap
```

### ④ Configure SMTP (inside script)

```python
SMTP_SERVER = "smtp.gmail.com"
SMTP_PORT = 587
SMTP_USERNAME = "your-email@gmail.com"
SMTP_PASSWORD = "your-app-password"
EMAIL_FROM = "your-email@gmail.com"
```

> ⚠️ Use Gmail App Passwords, not your main login password.

---

## 📝 How It Works

1. **User Input**: Choose mode (IP or range) and enter recipient email.
2. **Nmap Scan**: Performs stealth TCP, OS detection, and service fingerprinting.
3. **Parsing**: Converts raw Nmap output into structured Python data.
4. **HTML Report**: Generates a styled table with results.
5. **SMTP Delivery**: Sends report to recipient.

---

## 🔹 Sample Execution

```bash
$ python3 network_scan_tool.py

Enhanced Network Scan
1. Single IP Scan
2. CIDR Range Scan
Enter your choice (1 or 2): 2
Enter the CIDR range (e.g., 192.168.1.0/24): 192.168.1.0/24
Enter the recipient email address: admin@example.com

Scanning IP range: 192.168.1.0/24
Processing results...
Generating HTML report...
Sending report to admin@example.com...
Email sent successfully.
```

---

## 🔍 Report Format (HTML)

| IP Address  | OS Details      | Status | Firewall | Ports                       |
| ----------- | --------------- | ------ | -------- | --------------------------- |
| 192.168.1.1 | Linux 3.10–3.16 | up     | None     | 22/tcp open, 80/tcp open    |
| 192.168.1.2 | Windows 10      | up     | None     | 3389/tcp open, 135/tcp open |

---

## ⚠️ Troubleshooting

| Error                     | Fix                                                       |
| ------------------------- | --------------------------------------------------------- |
| `nmap.PortScannerError`   | Ensure Nmap is installed and in PATH                      |
| `KeyError: 'tcp'`         | Device might have no open TCP ports – scan another device |
| `SMTPAuthenticationError` | Use correct app password, not your Gmail login            |
| Long scan time            | Reduce range or adjust Nmap timing with `-T4` or `-T5`    |

---

## 🔒 Security Best Practices

* ⚠️ **Never scan networks without authorization**
* 🔐 Use App Passwords, not raw credentials in the script
* 🔒 Delete reports if they contain sensitive info
* ⚖️ Run scans during off-peak hours to avoid traffic disruption

---

## 🚪 Sample Use Cases

* Automated weekly subnet audits
* Classroom cybersecurity lab assignments
* SOC monitoring baseline scans
* Asset discovery for compliance

---

## 🌟 Future Enhancements

* Add **PDF export** option
* Integrate with **Slack/Teams for alerts**
* Add **cron job** for scheduled scanning
* Improve firewall detection accuracy

---

## 📄 License

MIT License

---

## 📢 Shields / Badges

![Python](https://img.shields.io/badge/Python-3.6+-blue)
![Tool](https://img.shields.io/badge/Tool-Nmap-green)
![Report](https://img.shields.io/badge/Output-HTML_Report-yellow)
![Email](https://img.shields.io/badge/Feature-Auto_Email-red)
![License](https://img.shields.io/badge/License-MIT-blue)

---

## ✨ Contributors

* Pavana M
* \[Add more contributors if needed]

