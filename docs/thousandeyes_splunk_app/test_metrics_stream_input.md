## Create a Test Stream - Metrics Input

- In `inputs` section
- Click `Create New Input`, select `Test Stream - Metrics`
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

![stream Input](../img/thousandeyes_splunk_app/inputTestsMetricsStream.png)

## Network and Application dashboards

- In the `dashboards` section, select `Network` 
![dashboard_network](../img/thousandeyes_splunk_app/dashboard_network.png)
- In the `dashboards` section, select `Application`
![dashboard_application](../img/thousandeyes_splunk_app/dashboard_application.png)


## Troubleshooting

Issue 
```
Error while configuring ThousandEyes stream input.Error: The Server Name, Host Name and Host is not reachable from Cisco Thousandeyes. One of these needs to be configured so that it is reachable from Cisco Thousandeyes. Server Name: show-s4x-config-i-03af7829c8bab4176, Host Name: show-s4x-config-i-03af7829c8bab4176, Host : 127.0.0.1. Please check the logs.
```

Solution: [Configuring Server name](getting_started.md#configuring-server-name)
