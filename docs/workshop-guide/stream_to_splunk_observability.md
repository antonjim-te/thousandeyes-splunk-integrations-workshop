# Step 3. Stream to Splunk Observability Cloud

## Step 3.a. Create Streaming integration on ThousandEyes for Splunk Observability Cloud

- Create a streaming integration for Splunk Observability Cloud. Check the [ThousandEyes API documentation](https://developer.cisco.com/docs/thousandeyes/create-data-stream).
- Use the `Create Integration - Splunk Observability` Postman request to create the stream

![ThousandEyes create stream](../img/postman/splunkObservabilityCloudStream.png)

## Step 3.b. Access Splunk Observability Cloud

- Navigate to [Splunk Observability Cloud](https://app.us1.signalfx.com/#/signin) 
    - Email: `antonjim+devnet<seat>@cisco.com` 
        - (e.g. `antonjim+devnet1@cisco.com`)
    - Password: `Cisco.25`

![Splunk Observability Cloud](../img/splunkObservabilityCloud/login.png)

## Step 3.c. Visualize ThousandEyes telemetry data in Splunk Observability Cloud

- In the initial page of [Splunk Observability Cloud](https://app.us1.signalfx.com/)
- Navigate to `Dashboards`
![dashboards](../img/splunkObservabilityCloud/dashboard.png)
- In `Custom dashboard groups`, expand `DEVWKS-2656` and select `Application`
![dashboard](../img/splunkObservabilityCloud/dashboardDEVWKS.png)
- Visualize the data
![Dashboard Application](../img/splunkObservabilityCloud/dashboardApplication.png)
![Dasboard Network](../img/splunkObservabilityCloud/dashboardNetwork.png)