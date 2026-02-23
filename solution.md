# AWS CloudWatch + SNS – Solution Guide

## Step 1: Launch EC2 Instance

Launch EC2 instance and note Instance ID.

---

## Step 2: Create SNS Topic

- Go to SNS
- Select Standard Topic
- Name: CPU-utilisation
- Display Name: CPU-utilisation
- Create Topic

---

## Step 3: Create Subscription

- Protocol: Email
- Endpoint: your-email@example.com
- Create Subscription

Confirm subscription from email.

---

## Step 4: Create CloudWatch Dashboard

- Go to CloudWatch
- Create Dashboard
- Name: twr-ec2-dashboard
- Select widget type: Number

Add Metric:
- Select EC2
- Select Per-Instance Metrics
- Select CPUUtilization
- Select your instance ID

Create Dashboard.

---

## Step 5: Create CloudWatch Alarm

- Go to CloudWatch → Alarms
- Create Alarm
- Select Metric: EC2 → CPUUtilization

Configure:

- Period: 1 minute
- Threshold type: Static
- Whenever CPU >= 60%

---

## Step 6: Configure Notification

- Select existing SNS topic
- Choose CPU-utilisation topic

---

## Step 7: Configure EC2 Action

- Select Stop Instance action

---

## Step 8: Name Alarm

Alarm Name:
twr-cpuutilisation-60%

Create Alarm.

---

## Step 9: Generate Load

SSH into instance:

top

Generate load:

yes > /dev/null &

When CPU exceeds 60%:

- Email notification sent
- Alarm triggered
- EC2 instance stopped automatically

---

## Step 10: Cleanup

- Delete Alarm
- Delete SNS Topic
- Delete Subscription

---

## ✅ Outcome

Successfully implemented:

- CloudWatch Monitoring
- SNS Email Alerts
- Automated EC2 Protection
- Real-time monitoring dashboard

------------------------------------------------------------------------

## 👨‍💻 Author

Rushikesh Sutar\
DevOps Engineer

------------------------------------------------------------------------

⭐ If this repository helped you, consider giving it a star.
