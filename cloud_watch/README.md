# Structured Logging in AWS CloudWatch

1. Clone this repo

```shell
git clone https://github.com/tsahaca/aws-samples.git
cd cloud_watch
```
2. get the current timestamp in milli seconds

```shell
date +%s%3N
```
3. Replace the timestamp in log_events.json file with the current timestamp
4. Inject the log events in CloudWatch from cli
```shell
aws logs put-log-events --log-group-name greeting-app --log-stream-name my-localhost --log-events file://log_events.json
```
5. Go to CloudWatch Dashboard and validate the log events
6. Query the log events from CloudWatch Log Insights

```shell
fields @timestamp, @message, @logStream, @log
| filter user.email = 'tanmay.saha@example.com'
| sort @timestamp desc
| limit 20```

## [Structured Logging with Spring Boot and Amazon CloudWatch](https://reflectoring.io/struct-log-with-cloudwatch-tutorial/)
