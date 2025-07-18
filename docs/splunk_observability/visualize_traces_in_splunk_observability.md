# Visualize ThousandEyes Page Load HAR as a trace in Splunk Observability Cloud 

- In the initial page of Splunk Observability Cloud
- Navigate to `APM` -> `Traces`
![Trace view](../img/splunk_observability/trace_view.png)
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

## Now you can use the Observability backend feature

### Search for traces with a specific duration

- In the search bar, use the following query to find traces with a duration greater than 2000ms:
![Search traces by duration](../img/splunk_observability/search_traces_by_duration.png)

### Search for traces with errors

- In the search bar, select the `Error Only` checkbox to filter traces with errors
![Search traces with errors](../img/splunk_observability/search_traces_with_errors.png)
