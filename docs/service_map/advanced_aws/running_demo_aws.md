# Running the OpenTelemetry demo application in AWS

## Running the OpenTelemetry demo application locally

- Clone the [OpenTelemetry demo application](https://github.com/open-telemetry/opentelemetry-demo) repository.
```
git clone https://github.com/open-telemetry/opentelemetry-demo.git
cd opentelemetry-demo
```

- Update the trace exporter to send to Splunk Observability.
    - Change `src/otel-collector/otelcol-config-extras.yml`
    ```
    exporters:
      otlphttp/splunk:
        traces_endpoint: https://ingest.<Splunk_Observability_realm>.signalfx.com:443/v2/trace/otlp
        headers:
            "X-SF-Token": "<Splunk_Observability_access_token>"
            "Content-Type": "application/x-protobuf"

    service:
      pipelines:
        traces:
            exporters: [spanmetrics, otlphttp/splunk]
    ```
        - Replace `<Splunk_Observability_realm>` with your Splunk Observability realm (e.g., `us0`, `us1`, `eu0`, etc.)
        - Replace `<Splunk_Observability_access_token>` with your Splunk Observability access token.
- Start the OpenTelemetry demo application
```
docker compose up --force-recreate --remove-orphans --detach
```

- Verify that the application is running by visiting [http://localhost:8080](http://localhost:8080) in your web browser. You should see the OpenTelemetry demo application homepage.

## View a trace in Splunk Observability

- Call a REST API of the OpenTelemetry demo application to generate some traces
```
curl http://localhost:8080/api/cart -H 'traceparent: 00-4bf92f3577b34da6a3ce929d0e0e4736-00f067aa0ba902b7-01'
```
- Open the trace [https://app.us1.signalfx.com/#/apm/traces/4bf92f3577b34da6a3ce929d0e0e4736](https://app.us1.signalfx.com/#/apm/traces/4bf92f3577b34da6a3ce929d0e0e4736).

![trace](../../img/splunk_observability/trace.png)
