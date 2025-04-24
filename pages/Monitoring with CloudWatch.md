---
title: "Monitoring with CloudWatch"
---

from  [[Summer Polis Festival 2024]]
Monitoring with CloudWatch

1:
Ask about monitoring while waiting for build
<img src='https://scrapbox.io/api/pages/nishio-en/gpt/icon' alt='gpt.icon' height="19.5"/>The following are some specific means of easily monitoring the load on servers running on EC2.
- Amazon CloudWatch:
    - Configuration: Access the CloudWatch dashboard from the AWS Management Console and select the metrics you wish to monitor.
    - Functions: Real-time monitoring of CPU utilization, disk I/O, network traffic, memory utilization (configurable as custom metrics), etc.
    - Alerts: Can be configured to receive notifications when certain thresholds are exceeded.

<img src='https://scrapbox.io/api/pages/nishio-en/nishio/icon' alt='nishio.icon' height="19.5"/>Amazon CloudWatch console first look, what to do

ChatGPT
If you are using the Amazon CloudWatch console for the first time, the following steps are recommended to proceed with the configuration.

1. access the CloudWatch console
Log in to the AWS Management Console.
Select "CloudWatch" from the list of services.
2. checking the metrics
Click on "Metrics" in the left navigation pane.
Select the "All Metrics" tab, and from the list of resources displayed, select the metrics for the EC2 instance you wish to monitor.
Common metrics include CPU utilization (CPUUtilization), disk read/write (DiskReadOps, DiskWriteOps), and network traffic (NetworkIn, NetworkOut).
3. create a dashboard
In the left navigation pane, click on "Dashboards" and select "Create Dashboard".
Name the dashboard and click "Add" to add the widget.
Select a widget such as "Line Chart" or "Numeric" and add the metrics you wish to monitor.
4. alarm settings
In the left navigation pane, click on "Alarms" and select "Create Alarm".
From "Metrics," select the metrics you wish to monitor and set the conditions (thresholds).
Example: Triggering an alarm when CPU utilization exceeds 80%.
Set up a notification destination (SNS topic) to receive an email or SMS notification when an alarm is triggered.
5. installation of CloudWatch Agent (optional)
Install CloudWatch Agent to monitor metrics that are not available by default, such as memory usage.
Log in to the EC2 instance via SSH and execute the following command to install the CloudWatch Agent.
bash
Copy code
sudo yum install amazon-cloudwatch-agent
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-config-wizard
Follow the wizard to create a configuration file and start CloudWatch Agent.
bash
Copy code
sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -a fetch-config -m ec2 -c file:/path/to/your/config.json -s
By following these steps, you can configure the Amazon CloudWatch console to monitor the performance of your EC2 instance.


hmm
![image](https://gyazo.com/a66d0511dc03fa9b6ee8e5b1d0577584/thumb/1000)

I see
![image](https://gyazo.com/1557f93bca949479e4a245b21371bc6d/thumb/1000)


from  [[Summer Polis Festival 2024]]
- [[Monitoring with CloudWatch]]
2:
ClaudWatch

:

```
Current config as follows:
{
        "agent": {
                "metrics_collection_interval": 60,
                "run_as_user": "cwagent"
        },
        "metrics": {
                "metrics_collected": {
                        "disk": {
                                "measurement": [
                                        "used_percent"
                                ],
                                "metrics_collection_interval": 60,
                                "resources": [
                                        "*"
                                ]
                        },
                        "mem": {
                                "measurement": [
                                        "mem_used_percent"
                                ],
                                "metrics_collection_interval": 60
                        }
                }
        }
}
```


:

```
$ sudo /opt/aws/amazon-cloudwatch-agent/bin/amazon-cloudwatch-agent-ctl -m ec2 -a status
{
  "status": "stopped",
  "starttime": "",
  "configstatus": "configured",
  "version": "1.300041.0b681"
}
```

I'm not sure if that's right.
- ![image](https://gyazo.com/9b7b91a21e6c4bf8d31e504fc374c779/thumb/1000)
    - You're not even getting any zeros!


---
This page is auto-translated from [/nishio/CloudWatchで監視](https://scrapbox.io/nishio/CloudWatchで監視) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.