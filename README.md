# python-security-lab
# 🛡️ Automated Threat Intelligence & Log Analyzer
A modular Python suite designed to perform behavioral analysis on Linux `auth.log` files. This tool automates the detection of common attack vectors and aggregates historical data to identify persistent threats.

### 🔍 Detection Capabilities
- **Brute Force Detection:** Identifies repeated `Failed password` attempts from specific IP addresses.
- **User Enumeration:** Flags attempts to log in with non-existent usernames (e.g., `invalid user admin`).
- **Privilege Escalation:** Monitors `sudo` failures and unauthorized attempts to gain root access.
- **Persistent Threat Tracking:** Uses historical CSV archiving to detect IPs that target the system over multiple sessions.

### 🚀 How It Works
The suite consists of two primary modules:
1. **Live Analyzer (`log_analyzer.py`):** - Reads the raw `auth.log` file line-by-line using Regex.
   - Generates a terminal-based **Threat Intelligence Summary**.
   - Outputs a unique, timestamped CSV report (e.g., `attack_report_20260206_1500.csv`) to prevent data overwriting.
   
2. **Master Aggregator (`master_report.py`):**
   - Scans the directory for all archived CSVs.
   - Uses the **Pandas** library to merge datasets and identify long-term trends.

  ### 🛠️ Setup & Usage
1. **Clone the repository:**
   `git clone https://github.com/Protege-max/Python-Security-Lab.git`
3. **Install dependencies:**
   `pip install pandas`
4. **Run the analysis:**
   `python3 log_analyzer.py`
