# Getting Started with Distributed Tracing in Splunk Observability

Due to time limitations, we will not be able to run an application locally, instrument it with OpenTelemetry, and make it public so it can be reach by ThousandEyes. However, you can refer to the [advanced guide](../advanced/getting_started.md) for more information.

For the basic integration, we will be using the OpenTelemetry demo application running in the cloud.
This application is already instrumented with OpenTelemetry sending telemetry data to Splunk Observability account (owned by ThousandEyes).
It is publicly accessible at [http://13.52.215.7:8080](http://13.52.215.7:8080).


## Recording 

As you will only have acess to the Splunk Observability Cloud token during the workshop, we had recorded a video walkthrough of the steps to set up the service map in ThousandEyes.

<div style="padding-bottom: 56.25%; position: relative; display: block; width: 100%">
	<iframe src="https://app.vidcast.io/share/embed/b18269c6-7c47-4c31-bc11-766a8581fe73?disableCopyDropdown=1" width="100%" height="100%" title="ThousandEyes Service map - Distributed tracing Splunk Integration - Basic Workshop" loading="lazy" allow="fullscreen *;autoplay *;" style="position: absolute; top:0; left: 0; border: solid; border-radius: 12px;"></iframe>
</div>