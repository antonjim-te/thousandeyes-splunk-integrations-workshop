## Create a Test Stream - Traces Input

- In `inputs` section
- Click `Create New Input`, select `Test Stream - Traces`
- Fill the form:
    - Name: unique name
    - ThousandEyes User: select you user
    - Account Group: select your account
    - HEC Target: The HEC target of your Splunk instance. Example HEC Target:
        - For Splunk Cloud Platform: `https://http-inputs-<host>.splunkcloud.com:443/services/collector/event`
        - For Splunk Enterprise: `https://<host>:8088/services/collector/event`
    - Cloud & Enterprise Agent Tests: select your HTTP test
    - HEC Token: select `ThousandEyesToken`
    - Test Index: select `default`

![stream Input](../img/thousandeyes_splunk_app/inputTestsTracesStream.png)

## Traces dashboards

Note: 

!!! warning "Version limitation"
    This dashboard requires features available only in Splunk Enterprise/Splunk Cloud version 9.4.0 or newer

- In the `dashboards` section, select `Traces` 

    - Main: See the list of traces

        ![dashboard_main](../img/thousandeyes_splunk_app/dashboard_traces_main.png)

    - Details: Explore a trace:

        ![dashboard_details](../img/thousandeyes_splunk_app/dashboard_traces_detail.png)

## Troubleshooting

Issue 
```
Error while configuring ThousandEyes stream input.Error: The Server Name, Host Name and Host is not reachable from Cisco Thousandeyes. One of these needs to be configured so that it is reachable from Cisco Thousandeyes. Server Name: show-s4x-config-i-03af7829c8bab4176, Host Name: show-s4x-config-i-03af7829c8bab4176, Host : 127.0.0.1. Please check the logs.
```

Solution: [Configuring Server name](getting_started.md#configuring-server-name)
