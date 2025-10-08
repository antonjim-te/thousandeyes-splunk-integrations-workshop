# Obtain your star
![Star](../img/star.png) 

**CHALLENGE**
To obtain your star please post in the [CX Observability Hackathons Webex Space](https://eurl.io/#_mvufmNou):

- Screenshot of the output from the `Search & Reporting` app:
      - Query: `index="*" source="ThousandEyesOTel" | timechart avg("metric_name:network.latency") as "Avg" span=60s`
      - Tab: `Visualization`
- Screenshot of the output from the `Search & Reporting` app:
      - Query: `index="*" source="ThousandEyesOTel" | timechart avg("metric_name:http.server.request.availability") as "Avg" span=60s` 
      - Tab:`Visualization`
- Screenshot of the output from the `Search & Reporting` app:
      - Query: `index="*" source="ThousandEyesOTel" otel.log.severity.text="Info"`
      - Tab: `Events`