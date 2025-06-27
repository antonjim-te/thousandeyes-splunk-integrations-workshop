# Streams telemetry data to Splunk Cloud Platform or Splunk Enterprise

## Create Metrics Streams on ThousandEyes for Splunk Cloud Platform or Splunk Enterprise

Choose one of the following methods to create your stream to Splunk Cloud Platform or Splunk Enterprise:

=== "API Method"

    Use the ThousandEyes API through Postman to create the stream programmatically.
    
    ### Create Stream via API
    - Open the request in your Postman collection
        - Splunk Cloud Platform: `Create metrics stream - Splunk Cloud Platform`
        - Splunk Enterprise:  `Create metrics stream - Splunk Enterprise`
    - Click `Send` to execute the API request
    
    ![ThousandEyes create stream](img/postman/splunkEnterpriseStream.png)
    
    !!! tip "API Documentation"
        For detailed API parameters and options, check the [ThousandEyes API documentation](https://developer.cisco.com/docs/thousandeyes/create-data-stream).

=== "UI Method"

    Use the ThousandEyes web interface to create the integration manually using Integrations 2.0.

    ### Create a Connector

    To create a new integration, follow these steps:

    - In the ThousandEyes platform, go to `Manage > Integrations > Integrations 2.0`
    - Click `+ New Connector` to select the type of connector to configure
        - Splunk Cloud Platform: `Splunk Cloud Platform HEC`
        - Splunk Enterprise: `Splunk Enterprise HEC`
    - Configure Connector Settings    
        - `Name`: A name for your connector (e.g., "My Splunk Integration")
        - `Target`: The target URL of the integration:
            - `Splunk Cloud Platform`: `https://http-inputs-<host>.splunkcloud.com:443/services/collector/event`
            - `Splunk Enterprise`: `https://<host>/services/collector/event`
        - `Token`: Enter your Splunk HEC token
    - Click `Save & Assign Operation` to save the connector

    ### Create an Operation

    Set up an operation to stream data to the target:

    - Click `+ New Operation` to open the menu for selecting the operation type
    - Choose `Splunk Enterprise, Splunk Cloud Platform` to proceed to the configuration form
    -  Configure Operation Settings
          - `Operation Name`: A name for your operation
          - `OpenTelemetry Signal`: `metric`
          - `Network & App Synthetics Tests`: Select the created tests.
    - Click `Save` to complete the creation of the integration

!!! note "Data Flow Timing"
    The stream will begin sending data to your Splunk instance within a few minutes of activation.
