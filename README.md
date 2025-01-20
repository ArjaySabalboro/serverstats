// # serverstats
// Roadmap.sh first project (beginner)

#!/bin/bash

echo "==== Server Statistics ===="
echo "Hostname: $(hostname)"
echo "OS Version: $(lsb_release -d | cut -f2)"
echo "Kernel Version: $(uname -r)"
echo "System Uptime: $(uptime -p)"
echo

echo "==== CPU Information ===="
echo "CPU Load Average: $(uptime | awk -F'load average:' '{print $2}')"
echo "CPU Usage:"
mpstat | grep -A 5 "%idle" | awk '{if ($1 ~ /^[0-9]/) print "CPU "$2": "100-$NF"%"}'
echo

echo "==== Memory Usage ===="
free -h
echo

echo "==== Disk Usage ===="
df -h | grep '^/dev'
echo

echo "==== Network Statistics ===="
ip -br addr
echo


// https://roadmap.sh/projects/server-stats
