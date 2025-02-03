# DEVWKS-2656 Stream ThousandEyes Data to Splunk Using OpenTelemetry

![DEVWKS-2656](img/banner.png)

# Table of Contents
- [DEVWKS-2656 Stream ThousandEyes Data to Splunk Using OpenTelemetry](#devwks-2656-stream-thousandeyes-data-to-splunk-using-opentelemetry)
- [Table of Contents](#table-of-contents)
- [Introduction](#introduction)
  - [Note](#note)
- [Step-by-Step Guide](#step-by-step-guide)
  - [Step 1. Postman](#step-1-postman)
    - [Step 1.a. Login Postman](#step-1a-login-postman)
    - [Step 1.b. Verify Postman collection `DEVWKS-2656`](#step-1b-verify-postman-collection-devwks-2656)
  - [Step 2. Login ThousandEyes](#step-2-login-thousandeyes)
  - [Step 3. Obtain ThousandEyes OAuth Bearer token](#step-3-obtain-thousandeyes-oauth-bearer-token)
  - [Step 4. Create ThousandEyes HTTP Server test](#step-4-create-thousandeyes-http-server-test)
  - [Step 5. Create Splunk Enterprise integration](#step-5-create-splunk-enterprise-integration)
    - [Step 5.a. Login into Splunk Enterprise](#step-5a-login-into-splunk-enterprise)
    - [Step 5.b. Get Splunk HEC token](#step-5b-get-splunk-hec-token)
    - [Step 5.c. Create Streaming integration on ThousandEyes for Splunk Enterprise](#step-5c-create-streaming-integration-on-thousandeyes-for-splunk-enterprise)
  - [Step 6. Visualize ThousandEyes telemetry data in Splunk Enterprise](#step-6-visualize-thousandeyes-telemetry-data-in-splunk-enterprise)
  - [Step 7. Create Splunk Observability Cloud integration](#step-7-create-splunk-observability-cloud-integration)
    - [Step 7.a. Login into Splunk Observability Cloud](#step-7a-login-into-splunk-observability-cloud)
    - [Step 7.b. Get Splunk Observability Cloud Access Tokens](#step-7b-get-splunk-observability-cloud-access-tokens)
    - [Step 7.c. Create Streaming integration on ThousandEyes for Splunk Observability Cloud](#step-7c-create-streaming-integration-on-thousandeyes-for-splunk-observability-cloud)
  - [Step 8. Visualize ThousandEyes telemetry data in Splunk Observability Cloud](#step-8-visualize-thousandeyes-telemetry-data-in-splunk-observability-cloud)

# Introduction

Welcome to the workshop for streaming ThousandEyes data to Splunk using OpenTelemetry.
This workshop will guide you through setting up integrations between ThousandEyes and Splunk, enabling you to visualize and analyze network monitoring data effectively.

## Note

Each attendee has a unique login:
 - User: `antonjim+devnet.ws2.<seat>@cisco.com` 
   - E.g. `antonjim+devnet.ws2.seat1@cisco.com`. Correspond with your seat.
 - Password: `C1sco12345!`

# Step-by-Step Guide

## Step 1. Postman

### Step 1.a. Login Postman

> [!NOTE]
> You may be already singed in. Then, you can skip this step.

- Open Postman application
  -  Sign in ![Postman Sign in](img/postman/signin.png)
     - Email: `antonjim+devnet.ws2.<seat>@cisco.com` (e.g. `antonjim+devnet.ws2.seat1@cisco.com`)
     - Password: `C1sco12345!`
    ![Postman Sign in](img/postman/signin2.png)

### Step 1.b. Verify Postman collection `DEVWKS-2656` 

- Navigate to `Workspaces` -> `My Workspace` ![Postman Sign in](img/postman/workspace.png)
- Identify the collection `DEVWKS-2656`
  - Confirm the requests and variables are there. We will use them during the session.
  -  ![Postman collection DEVWKS](img/postman/DEVWKS.png)

## Step 2. Login ThousandEyes

- Navigate to [ThousandEyes Login](https://app.thousandeyes.com/login){:target="_blank"}
  -  ![ThousandEyes Login](img/thousandeyes/login.png)
     - Email: `antonjim+devnet.ws2.<seat>@cisco.com` (e.g. `antonjim+devnet.ws2.seat1@cisco.com`)
     - Password: `C1sco12345!`
  
## Step 3. Obtain ThousandEyes OAuth Bearer token

Each API request to ThousandEyes should be authenticated using OAuth Bearer Token.

To obtain it follow the following steps:
- After logging in, navigate to `Account Settings` -> `Users and Roles` ![ThousandEyes user and roles](img/thousandeyes/usersRoles.png)
- Click `Create` next to `OAuth Bearer Token` on `User API Tokens` ![ThousandEyes create token](img/thousandeyes/createToken.png)
- ThousandEyes will generate new OAuth Bearer Token for you and show it in a new popup window ![ThousandEyes token](img/thousandeyes/token.png)
- Click `Copy` and
- Save the token into the variable `ThousandEyes_token` in Postman ![ThousandEyes token variable](img/postman/thousandeyesToken.png)

> [!WARNING]
> The OAuth Token is shown only once. If lost, you need to revoke and create a new one.

## Step 4. Create ThousandEyes HTTP Server test

For ThousandEyes to be able to stream data to Splunk, the data first needs to be collected by ThousandEyes. To achieve this, we
need to create a ThousandEyes test.
Refer to [ThousandEyes documentation](https://docs.thousandeyes.com/product-documentation/tests){:target="_blank"} for test creation.

We are going to create an `HTTP Server` test that validates the availability of `www.google.com`.
Full description of the API request is available at [ThousandEyes API Reference](https://developer.cisco.com/docs/thousandeyes/create-http-server-test){:target="_blank"}.

- Use the following Postman request to create the HTTP test ![ThousandEyes create test](img/postman/createHttpTest.png)

> [!NOTE]
> You can use other `agentId` using [ThousandEyes API List Agents](https://developer.cisco.com/docs/thousandeyes/list-cloud-and-enterprise-agents){:target="_blank"}, [more info](<getAgentId.md>).

- Save the `testId` from the response into the variable `ThousandEyes_test_id` in Postman ![ThousandEyes test id variable](img/postman/testId.png)

## Step 5. Create Splunk Enterprise integration

### Step 5.a. Login into Splunk Enterprise

- Navigate to [Splunk Enterprise](https://splunk.pseudoco.net){:target="_blank"}
  -  ![Splunk Enterprise Login](img/splunkEnterprise/login.png)
  - Username: `antonjim+devnet.ws2.<seat>@cisco.com`  (e.g. `antonjim+devnet.ws2.seat1@cisco.com`)
  - Password: `C1sco12345!`
- Welcome page ![Splunk Enterprise Login](img/splunkEnterprise/welcomepage.png)

### Step 5.b. Get Splunk HEC token

- Navigate to `Settings` -> `Data Inputs`  ![datainputs](img/splunkEnterprise/datainputs.png)
- Open `HTTP Event Collector`  ![HTTP Event Collector](img/splunkEnterprise/HttpEventCollector.png)
- There you can find a pre-provisioned token called `Default` which you can use. Copy `Token Value`
![HEC token](img/splunkEnterprise/hecToken.png)
- Save the `HEC token` into the variable `Splunk_Enterprise_HEC_token` in Postman ![Splunk Enterprise HEC token variable](img/postman/splunkEnterpriseToken.png)

### Step 5.c. Create Streaming integration on ThousandEyes for Splunk Enterprise

- Create a stream integration for Splunk Enterprise. Check the [ThousandEyes API documentation](https://developer.cisco.com/docs/thousandeyes/create-data-stream){:target="_blank"}.
- Use the following Postman request to create the stream ![ThousandEyes create stream](img/postman/splunkEnterpriseStream.png)

## Step 6. Visualize ThousandEyes telemetry data in Splunk Enterprise

- Open [Splunk Enterprise](https://splunk.pseudoco.net){:target="_blank"}
- Navigate to `Search & Reporting` ![Search](img/splunkEnterprise/search.png)
- Search by `index="*" source="ThousandEyesOTel"` ![Search by source](img/splunkEnterprise/searchSource.png) ![Expand metric](img/splunkEnterprise/expandMetric.png)
- Navigate to `Dashboards` ![Dashboards](img/splunkEnterprise/dashboard.png)
- Select `DEVWKS-2656` ![Dashboards](img/splunkEnterprise/dashboardDEVWKS.png)
- Visualize the data
![Dashboard Application](img/splunkEnterprise/dashboardApplication.png)
![Dasboard Network](img/splunkEnterprise/dashboardNetwork.png)

## Step 7. Create Splunk Observability Cloud integration

### Step 7.a. Login into Splunk Observability Cloud

- Navigate to [Splunk Observability Cloud](https://app.eu1.signalfx.com/#/signin){:target="_blank"}
  - ![Splunk Observability Cloud](img/splunkObservabilityCloud/login.png)
  - Email: `antonjim+devnet.ws2.<seat>@cisco.com` 
    - (e.g. `antonjim+devnet.ws2.seat1@cisco.com`)
  - Password: `C1sco12345!`

### Step 7.b. Get Splunk Observability Cloud Access Tokens

- Navigate to `Settings` -> `Access Tokens`
- There you can find a pre-provisioned token called `Default` which you can use. Copy `Token Value` ![token](img/splunkObservabilityCloud/token.png)
- Save the `token` into the variable `Splunk_Observability_access_token` in Postman  ![Splunk Observability Cloud token variable](img/postman/splunkObservabilityCloudToken.png)

### Step 7.c. Create Streaming integration on ThousandEyes for Splunk Observability Cloud

- Create a streaming integration for Splunk Observability Cloud. Check the [ThousandEyes API documentation](https://developer.cisco.com/docs/thousandeyes/create-data-stream){:target="_blank"}.
- Use the following Postman request to create the stream ![ThousandEyes create stream](img/postman/splunkObservabilityCloudStream.png)

## Step 8. Visualize ThousandEyes telemetry data in Splunk Observability Cloud

- Open [Splunk Observability Cloud](https://app.eu1.signalfx.com/#/signin){:target="_blank"}
- Navigate to `Dashboard` ![dashboard](img/splunkObservabilityCloud/dashboard.png)
- In `Custom dashboard groups`, expand `DEVWKS-2656` and select `Application` ![dashboard](img/splunkObservabilityCloud/dashboardDEVWKS.png)
- Visualize the data
![Dashboard Application](img/splunkObservabilityCloud/dashboardApplication.png)
![Dasboard Network](img/splunkObservabilityCloud/dashboardNetwork.png)