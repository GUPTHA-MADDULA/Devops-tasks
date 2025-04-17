
# Monitoring System Resources using Docker Desktop

## Introduction
This guide explains how to run Netdata in a Docker container to monitor your system metrics in real-time.  
Netdata is a highly interactive and real-time monitoring dashboard that provides insights into CPU, memory, disk activity, network traffic, and many more system metrics.

---

## Prerequisites
- Docker installed and running on your machine
- Basic understanding of Docker commands
- Internet connection to pull the Netdata image

---

## Docker Command

You can run the Netdata container using the following command:

```bash
docker run -d --name=netdata -p 19999:19999 --cap-add SYS_PTRACE --security-opt apparmor=unconfined -e CLOUD_DISABLE=true netdata/netdata
```

### Explanation of the command:
- `docker run -d`: Run the container in detached mode (in the background).
- `--name=netdata`: Assigns a custom name "netdata" to the container.
- `-p 19999:19999`: Maps the container's internal port 19999 to the host machine's port 19999.
- `--cap-add SYS_PTRACE`: Grants the container additional capabilities required by Netdata.
- `--security-opt apparmor=unconfined`: Disables AppArmor security profiles for better compatibility.
- `-e CLOUD_DISABLE=true`: Disables Netdata Cloud functionality for local monitoring only.
- `netdata/netdata`: Specifies the Netdata image from Docker Hub.

---

## Accessing Netdata Dashboard
After running the container, open your web browser and go to:

```
http://localhost:19999
```

You will see the Netdata dashboard displaying real-time system metrics.

---
![Ram Utilization](./pictures/Screenshot%202025-04-17%20220452.png)

![Memory Utilization Metrics](./pictures/Screenshot%202025-04-17%20220509.png)

![Network Metrics](./pictures/Screenshot%202025-04-17%20220522.png)

## Troubleshooting
- If you encounter a "no such host" or "unexpected EOF" error while pulling the image, ensure that your system has a stable internet connection.
- If using PowerShell on Windows, avoid using backslashes (`\`) for multi-line commands. Instead, run the full command in one line or use the backtick ( ` ) character for line continuation.

---

## Additional Notes
- Netdata collects detailed metrics by default. It may slightly increase resource usage depending on your system.
- To stop the container:

```bash
docker stop netdata
```

- To remove the container:

```bash
docker rm netdata
```

- If you want to monitor other Docker containers, Netdata automatically detects them if you install the `netdata/netdata` container with the necessary permissions.

---

## Conclusion
By running Netdata inside a Docker container, you can easily monitor your system's health and performance metrics without modifying your base operating system.  
It is lightweight, easy to set up, and provides immediate visual feedback on system activity.

---
