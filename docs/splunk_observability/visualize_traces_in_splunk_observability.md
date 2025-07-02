# Visualize ThousandEyes Page Load HAR as a trace in Splunk Observability Cloud 

- In the initial page of Splunk Observability Cloud
- Navigate to `APM` -> `Traces`
- Filter by `Services` and select `www.google.com`
![Search traces](../img/splunk_observability/searchTraces.png)
- Click on a trace to view details
![Trace details](../img/splunk_observability/traceDetails.png)
- Each span will be a step in the page load
- Each span will contains:
    - Information about the request: URL, method, duration, and status code
        - ![span request details](../img/splunk_observability/span_request_details.png)
    - ThousandEyes identification: account, test, agent, stream
        - ![span thousandeyes details](../img/splunk_observability/span_thousandeyes_details.png)