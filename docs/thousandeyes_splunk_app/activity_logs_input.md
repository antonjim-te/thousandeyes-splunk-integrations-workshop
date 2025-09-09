## Create an Activity Log Input

- In `inputs` section
- Click `Create New Input`, select `Activity logs Stream`
- Fill the form:
    - Name: unique name
    - ThousandEyes User: select you user
    - Account Group: select your account
    - HEC Target: The HEC target of your Splunk instance. Example HEC Target:
        - For Splunk Cloud Platform: `https://http-inputs-<host>.splunkcloud.com:443/services/collector/event`
        - For Splunk Enterprise: `https://<host>:8088/services/collector/event`
    - HEC Token: select `ThousandEyesToken`
    - Activity logs Index: select `default`

![Activity Input](../img/thousandeyes_splunk_app/inputActivityLogStream.png)

## Activity Log Dashboards

- In the `dashboards` section, select `Activity Log` 
![dashboard_activity_logs](../img/thousandeyes_splunk_app/dashboard_activity_logs.png)
- In case you do not have data in the table, you can generate by using ThousandEyes. For example: creating/deleting tests.
- Once you see data, you can filter by account group, user, event and time interval.