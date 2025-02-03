# Server Stats Script

## Overview
`server-stats.sh` is a simple Bash script that gathers and displays key server statistics, including:

- Total CPU usage
- Total memory usage (Free vs Used including percentage)
- Total disk usage (Free vs Used including percentage)
- Top 5 processes by CPU usage
- Top 5 processes by memory usage

This script is useful for monitoring system performance and identifying resource-intensive processes.

## Prerequisites
Ensure you have the following installed on your system:

- `bash` (default shell in most Linux distributions)
- `mpstat` (from the `sysstat` package)
- `ps` (part of core utilities)

To install `sysstat`, use:
```bash
sudo apt install sysstat  # Ubuntu/Debian
sudo yum install sysstat  # CentOS/RHEL
sudo dnf install sysstat  # Fedora
```

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/server-stats.git
   cd server-stats
   ```

2. Make the script executable:
   ```bash
   chmod +x server-stats.sh
   ```

## Usage
Run the script using:
```bash
./server-stats.sh
```

The output will display real-time server statistics.

## Example Output
```
==== Server Statistics ====
Total CPU Usage: 15.24%

Total Memory Usage (Free vs Used):
Total: 8.0G, Used: 6.5G, Free: 1.5G (81.25% used)

Total Disk Usage (Free vs Used):
Total: 500G, Used: 250G, Free: 250G (50.00% used)

Top 5 Processes by CPU Usage:
PID   COMMAND  %CPU
1234  firefox  24.5
5678  chrome   19.8
...

Top 5 Processes by Memory Usage:
PID   COMMAND  %MEM
2345  java     35.2
6789  python   12.4
...
```

## Automating with Cron
To run the script every 30 minutes and log output:
```bash
crontab -e
```
Add this line:
```bash
*/30 * * * * /path/to/server-stats.sh >> /var/log/server-stats.log
```

## License
This project is licensed under the MIT License

## Contributing
Feel free to fork this repository, make improvements, and submit a pull request!

## Author
Arjay Sabalboro - [GitHub Profile](https://github.com/ArjaySabalboro)

