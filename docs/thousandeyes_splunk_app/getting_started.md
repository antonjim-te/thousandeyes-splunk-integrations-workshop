
# Cisco ThousandEyes App for Splunk

The [Cisco ThousandEyes App for Splunk](https://splunkbase.splunk.com/app/7719) enables collecting and analyzing:

- CEA (Cloud and Enterprise Agent) and Endpoint test results data
- Event
- Activity logs

![SplunkBase](../img/thousandeyes_splunk_app/splunkbase.png)

!!! tip "Docs"
    You can find [documentation](https://docs.thousandeyes.com/product-documentation/integration-guides/custom-built-integrations/splunk-app).

## Install Cisco ThousandEyes App for Splunk

- Once we are logged into Splunk Enterprise 
- Navigate to `Apps` > `Manage Apps`
- Click on `Install app from file`
- Choose [file](https://github.com/antonjim-te/thousandeyes-splunk-integrations-workshop/raw/refs/heads/main/thousandeyes_splunk_app/cisco-thousandeyes-app-for-splunk_0022.tgz)
- Click on `Upload`

![upload](../img/thousandeyes_splunk_app/upload.png)


## Access Cisco ThousandEyes App for Splunk

- Navigate to `Cisco ThousandEyes App for Splunk`
![navigate app](../img/thousandeyes_splunk_app/navigate_app.png)
- In the app, you will find out: `configuration`, `inputs`, `search` and `dashboards`. Check the [ThousandEyes documentation](https://docs.thousandeyes.com/product-documentation/integration-guides/custom-built-integrations/splunk-app)
![configuration](../img/thousandeyes_splunk_app/configuration.png)


## Configuring Server name

- Go to `Setttings` > `General Settings` > `Server Name`
- Set the `Server Name` to the hostname of your Splunk instance. Same value that the postman variaable `splunk_hec_host` is set to.

![Server name](../img/thousandeyes_splunk_app/config_server_name.png)

- Save the changes.
- Restart the Splunk instance.
  - Go to `Server Controls` > `Restart Splunk`    