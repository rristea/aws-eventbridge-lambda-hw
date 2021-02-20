# Hello World application with EventBridge and Lambda

This is a simple Hello World project that makes use of EventBridge Rule to invoke a Lambda function.

The Rule has both a scheduled pattern and an event pattern:
* It has a Schedule rule to invoke the lambda every two minutes.
* The event pattern searches for an Event with Source 'helloworld' (so a custom rule).

There is a custom Event defined in `event.json`, and the event can be sent with `put-event.sh`.

The Lambda function simply prints "Hello World!" and the Event Detail Type (either "Custom Event" or "Scheduled Event"). This can be seen in the CloudWatch Logs log-group associated with the Lambda.

The application is defined in the CloudFormation template `eventbridge-lambda.yml`, and can be created/deleted/updated with the scripts:
* create-stack.sh
* delete-stack.sh
* update-stack.sh

Ex: `./create-stack.sh eventbridge-lambda.yml`
