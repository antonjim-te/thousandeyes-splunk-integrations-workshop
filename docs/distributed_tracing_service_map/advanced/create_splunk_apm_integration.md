# Create Splunk APM Integration

We need to provide to ThousandEyes the Splunk Observabiltiy APM url and token to be able to get the traces and represent it as a Service Map.

- In the ThousandEyes platform, navigate to `Manage` > `Integrations` > `Integrations 2.0`
- Create a **Generic Connector** with the following details:
    - Target URL: `https://api.<REALM>.signalfx.com`
        - Replace `<REALM>` with your Splunk realm (for example, `us0`, `us1`, `eu1`)
    - Custom headers:
        - `X-SF-Token`: `<access_token>`
            - Replace `<access_token>` with your Splunk Observability access token

![Create connector Splunk APM](../../img/thousandeyes/create_connector_splunk_APM.png)

-  Create an **Operation**:
      -  Click `+ New Operation` to open the menu to select the operation type
      -  Choose `Splunk Observability APM` to proceed to the configration form
      -  Enter the Operation Name
      -  Enable the operation

![Create Operation Splunk APM](../../img/thousandeyes/create_operation_splunk_APM.png)
