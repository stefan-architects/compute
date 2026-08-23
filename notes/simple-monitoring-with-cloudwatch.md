## 1. 📖 Simple Monitoring with Cloudwatch
Deployed one EC2 instance to capture and analyze network traffic

## 2. 🌩️ Skill Building
* Stress an EC2 instance and observe what happens
* Practice AWS CLI commands
* Explore EC2 console after provisioning
* Linux navigation and file management

## 3. 🛰️ AWS Resources & Services
* EC2
* Instance Connect
* EC2 Monitoring Tab

## 4. 📟 Metrics Triggered by Script
* CPUUtilization — driven to 100% by the CPU stress workload
* NetworkIn — increased by repeated 10MB file downloads
* NetworkOut — increased by outbound HTTP requests
* DiskReadBytes / DiskWriteBytes — elevated due to dd and stress‑ng disk operations
* DiskReadOps / DiskWriteOps — increased EBS-backed I/O operations

## 5. 🧪 Stress Script
```bash
### Required actions 
touch stress.sh
chmod +x stress.sh
nano stress.sh
```

### Update system and install stress-ng
```bash
sudo yum update -y
sudo yum install -y stress-ng -y
```

### Commands used to stress the instance
```bash
# CPU — pushes CPUUtilization to 100% by running intensive compute operations
stress-ng --cpu 1 --cpu-method all --timeout 300s &

# Memory — allocates and stresses 80% of system RAM to simulate high memory pressure
stress-ng --vm 1 --vm-bytes 80% --timeout 300s &

# Disk I/O — performs heavy read/write operations to trigger EBS disk metrics
stress-ng --hdd 1 --hdd-ops 50000 --timeout 300s &

# Network — generates socket operations to increase NetworkIn and NetworkOut activity
stress-ng --sock 1 --sock-ops 50000 --timeout 300s &
```

# Ensure executable
```bash
chmod +x /stress.sh
```

## 6. 👀 Metrics Observed
* Instance slowed down and/or become unresponsive
* EC2 dashboard showed sustained high utilization across multiple metrics
* Despite the load, the instance didn't shut down
* Performance returns to normal after several minutes once the stress test completes and few periods of stability 
* System and Instance status checks remained healthy during testing

## 5. 👁️ Observations & Next Actions
### 🏢 *Workplace Applications*
* Review the results with the team and/or customer and discuss potential next steps
* Evaluate test results to confirm the instance is properly sized for future workloads

### 🧙🏽 *Ongoing Development*
* Plan additional scenarios to simulate more realistic or varied production workloads
* Continue practicing AWS CLI and bash commands to interact with the environment
* Need to understand what available metrics can help determine the health of deployed resources/services