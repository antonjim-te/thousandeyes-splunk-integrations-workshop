
# Cisco ThousandEyes App for Splunk

The [Cisco ThousandEyes App for Splunk](https://splunkbase.splunk.com/app/7719) enables collectos and analyze:

- CEA (Cloud and Enterprise Agent) and Endpoint test results data
- Event
- Activity logs

![SplunkBase](img/thousandEyes/splunkbase.png)

## Navigate to Cisco ThousandEyes App for Splunk 

- Once we are logged into Splunk Enterprise 
- Navigate to `Cisco ThousandEyes App for Splunk`
![navigate app](img/thousandEyes/navigate_app.png)
- In the app, you will find out: `configuration`, `inputs`, `search` and `dashboards`. Check the [ThousandEyes documentation](https://docs.thousandeyes.com/product-documentation/integration-guides/custom-built-integrations/splunk-app)
![configuration](img/thousandEyes/configuration.png)

## Create stream test input

- In `inputs` section
- Click `Create New Input`, select `Tests Stream`
- Fill the form:
    - Name: unique name, you can use `test_<seat>`. For example `test_1`
    - ThousandEyes User: select you user
    - Account Group: selec your account
    - Cloud & Enterprise Agent Tests: select your HTTP test
    - HEC Token: select `DEVWKS-2656`
    - Test Index: select `default`

![stream Input](img/thousandEyes/streamInput.png)

## Network and Application dashboards

- In the `dashboards` section, select `Network` 
![dashboard_network](img/thousandEyes/dashboard_network.png)
- In the `dashboards` section, select `Application`
![dashboard_application](img/thousandEyes/dashboard_application.png)

## Create activity log input

- In `inputs` section
- Click `Create New Input`, select `Activity`
- Fill the form:
    - Name: unique name, you can use `activity_<seat>`. For example `activity_1`
    - ThousandEyes User: select you user
    - Account Group: selec your account
    - Index: select `default`
![Activity Input](img/thousandEyes/inputActivity.png)

## Activity logs dashboards

- In the `dashboards` section, select `Activity Logs` 
![dashboard_activity_logs](img/thousandEyes/dashboard_activity_logs.png)
