# Python System Monitoring and Alerting Script

This Python script monitors the CPU, RAM, and disk usage of the system. If any of these resources exceed the defined thresholds, the script sends an email alert to the specified recipient using the **Mailjet** API.

---

## Features

- **System Metrics Monitoring**:
  - Monitors CPU, RAM, and disk usage using the `psutil` library.
  - Provides real-time metrics for each resource.
- **Threshold Alerts**:
  - Sends an email alert if any monitored system resource exceeds the predefined threshold.
- **Email Notifications**:

  - Utilizes the **Mailjet** API to send HTML-based email notifications to a configured recipient.

- **Customizable Thresholds**:
  - Easily configure the thresholds for CPU, RAM, and disk usage.
- **Secure Credentials**:
  - API credentials are securely loaded from environment variables.

---

## Prerequisites

Before running this script, ensure that you have:

- Python 3.x installed on your machine.
- The `psutil` library for system resource monitoring.
- A Mailjet account for sending emails.

To install the required dependencies, run:

```bash
pip install psutil mailjet-rest
```

## Installation

1. Clone or download the repository to your local machine.

2. Set up environment variables for **Mailjet API credentials**:

   You need to create two environment variables to securely store your Mailjet API key and secret:

   - `MAILJET_API_KEY`
   - `MAILJET_API_SECRET`

   You can set these in your terminal (or use a `.env` file with a library like `python-dotenv`):

   ```bash
   export MAILJET_API_KEY="your_mailjet_api_key"
   export MAILJET_API_SECRET="your_mailjet_api_secret"
   ```

3. Download or copy the script into your working directory.

---

## Configuration

The script uses the following configurable thresholds:

- **CPU_THRESHOLD**: The percentage of CPU usage that triggers an alert (default: `90%`).
- **RAM_THRESHOLD**: The percentage of RAM usage that triggers an alert (default: `10%`).
- **DISK_THRESHOLD**: The percentage of available disk space that triggers an alert (default: `50%`).

You can modify these values in the script directly.

---

## Usage

To run the script, use the following command:

```bash
python monitor.py
```

## The script will:

1. Check the system's CPU, RAM, and disk usage.
2. Compare the usage against the predefined thresholds.
3. If any metric exceeds the threshold, the script sends an email with the alert.
4. If all metrics are within normal limits, it will print `"All system metrics are within normal limits."`

## File Structure

The repository contains the following files:

```
.
├── system_monitor.py    # The main script for monitoring system metrics
├── README.md           # This README file
```

---

## Email Configuration

The script sends alerts using the **Mailjet** API. By default, it sends the alert to `delvin.yamoah@amalitechtraining.org`. You can change the recipient email address in the script.

---

## Notes

- **Security**: The Mailjet API credentials are securely loaded from environment variables to avoid hardcoding sensitive information in the script.

- **Threshold Adjustments**: You can adjust the CPU, RAM, and disk thresholds directly in the script to suit your system requirements.

- **Error Handling**: If the script fails to send an email, it will print an error message to the console.

---
