# AWS CloudWatch + SNS Architecture

                      EC2 Instance
                           |
                    CPU Utilization
                           |
                     CloudWatch Alarm
                           |
                 ------------------------
                 |                      |
           SNS Notification       EC2 Stop Action
                 |
              Email Alert

## Key Points

- CloudWatch monitors EC2 metrics
- Alarm triggers when CPU exceeds threshold
- SNS sends email notification
- Automated EC2 action protects infrastructure
