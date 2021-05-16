# Wake-up Call Setter Function

Function to set a Wake-up call.

## Testing locally

Run the Function
```bash
 ./gradlew runFunction \
    -Prun.functionTarget=com.guestassist.wakeupcall.WakeUpCallSetterFunction
```

Invoke the function
```bash
curl localhost:8080
# Output: Hello World!
```

## Deploying
```bash

gcloud functions deploy wakeup-call-setter-function \
 --entry-point com.guestassist.wakeupcall.WakeUpCallSetterFunction \
 --runtime java11 \
 --trigger-http \
 --memory 512MB \
 --allow-unauthenticated
 
```

### Testing the deployed function
When the function finishes deploying, take note of the httpsTrigger.url property or find it using the following command:

```bash

gcloud functions describe my-first-function
```
It should look like this:

```text
https://GCP_REGION-PROJECT_ID.cloudfunctions.net/my-first-function
```

Visit this URL in your browser. You should see a Hello World! message.

## Viewing logs
Using the command-line tool
Logs for Cloud Functions are viewable in the Cloud Logging UI, and via the gcloud command-line tool.

To view logs for your function with the gcloud tool, use the logs read command, followed by the name of the function:

```bash

gcloud functions logs read my-first-function
```