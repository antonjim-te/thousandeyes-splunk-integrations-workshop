# Create ThousandEyes HTTP Test with Distributed Tracing

We are going to create a `HTTP Test` test an endpoint to our OpenTelemetry demo application, which is already instrumented with OpenTelemetry and sending telemetry data to Splunk Observability.

Refer to [ThousandEyes documentation](https://docs.thousandeyes.com/product-documentation/tests) for test creation.

Use the ThousandEyes web interface to create the test.

- Click on `Network & App Synthetics` in the left navigation bar
- Select `Test Settings` from the dropdown menu
- Click the `+ Add New Test` button
- Select `HTTP Test` from the test type options
![create HTTP Test](../../img/thousandeyes/createHttpTest1.png)
- Configure Test Settings
      - `Test Name`: Enter a descriptive name (e.g., "Basic - Test Workshop Distributed Tracing")
      - `URL`: Enter `http://13.52.215.7:8080/api/test`
      - In the `Agents` section, select a Cloud Agent
      - Under `Advanced settings`:
          - Check `Enable Distributed Tracing`
          ![create HTTP Test](../../img/thousandeyes/createHttpTest2.png)
- Click `Create New Test`
![create HTTP Test](../../img/thousandeyes/basic_create_http_test_3.png)
