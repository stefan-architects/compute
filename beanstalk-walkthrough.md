## 1. 📖 AWS Elastic Beanstalk Deployment Walkthrough ✅
Understand the basics of creating, configuring, deploying, updating, and monitoring an Elastic Beanstalk application with environments running on Amazon EC2 instances.

## 2. 🌩️ Skill Building ✅
* Learn how Elastic Beanstalk provisions and manages underlying AWS resources such as EC2, Auto Scaling, Load Balancers, and CloudWatch.
* Use the console’s built‑in tools to access logs, view health metrics, and understand how Elastic Beanstalk manages application infrastructure.
* Learn when and why to choose Elastic Beanstalk versus other AWS deployment options based on application needs and infrastructure control.
* Use Elastic Beanstalk and CloudWatch metrics to monitor CPU usage, network traffic, request counts, latency, and HTTP errors.

## 3. 🛰️ AWS Resources & Services ✅
* AWS Elastic Beanstalk

## 4. 💡 Additional Resources ✅
- 🎥 [AWS Elastic Beanstalk Tutorial: Deploy a Web Application](https://www.youtube.com/watch?v=SgwPxZ4YQJs&t=2s)

## 6. 👀 Metrics Observed 🛑
* Instance slowed down and/or become unresponsive
* EC2 dashboard showed sustained high utilization across multiple metrics
* Despite the load, the instance didn't shut down
* Performance returns to normal after several minutes once the stress test completes and few periods of stability 
* System and Instance status checks remained healthy during testing

## 5. 👁️ Observations & Next Actions 🛑
### 🏢 *Workplace Applications*
* Review the results with the team and/or customer and discuss potential next steps
* Evaluate test results to confirm the instance is properly sized for future workloads

### 🧙🏽 *Ongoing Development* 🛑
* Plan additional scenarios to simulate more realistic or varied production workloads
* Continue practicing AWS CLI and bash commands to interact with the environment
* Need to understand what available metrics can help determine the health of deployed resources/services