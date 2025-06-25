# Login to Splunk Observability Cloud

This guide will help you log into Splunk Observability Cloud and obtain an access token for the ThousandEyes integration.

## Choose Your Access Method

=== "Existing Account"

    If you already have a Splunk Observability Cloud account:
    
    ### Login to Your Account
    - Navigate to [Splunk Observability Cloud](https://login.signalfx.com/)
    - Enter your `email address` and `password`
    - Click `Sign In`

=== "Free Trial"

    If you don't have a Splunk Observability Cloud account:
    
    ### Start Free Trial
    - Navigate to [Splunk Observability Cloud Free Trial](https://www.splunk.com/en_us/products/observability-cloud.html)
    - Click `Start Free Trial` or `Try Free`
    - Fill out the registration form with your business information:
        - `First Name` and `Last Name`
        - `Business Email Address`
        - `Company Name`
        - `Phone Number`
        - `Country/Region`
    
    ### Verify Your Account
    - Check your email for a verification message
    - Click the verification link to activate your account
    - Complete your profile setup
    - Access your new Splunk Observability Cloud dashboard

## Generate Access Token

Once you're logged into Splunk Observability Cloud, follow these steps to generate your access token:

### Navigate to Access Token Settings
- Click on your `profile icon` in the top-right corner
- Select `Organization Settings` from the dropdown menu
- In the left navigation, click on `Access Tokens`

### Create New Access Token
- Click `+ New Token` button
- Configure the token settings:
    - `Token Name`: Enter a descriptive name (e.g., "ThousandEyes Integration Token")
    - `Token Description`: Optional description for the token's purpose
    - `Token Type`: Select `INGEST` (required for receiving data from ThousandEyes)
    - `Permissions`: The INGEST type automatically has the correct permissions

### Generate and Copy Token
- Click `OK` to generate the token
- `Copy the token immediately` - it will only be displayed once
- Store the token securely (you'll need it for Postman configuration)

### Note Your Realm
- While in the Access Tokens section, note your `Realm` information
- Your realm is visible in the URL or in the organization settings (e.g., us0, us1, eu0)
- You'll need this realm information for the ThousandEyes integration

## Add Token to Postman Variables

Now that you have your Splunk Observability Cloud access token, add it to your Postman collection variables:

### Open Collection Variables
- In Postman, navigate to your `ThousandEyes Splunk Integration` collection
- Go to the `Variables` tab

### Set the Splunk Access Token Variable
- Find the variable named `Splunk_access_token` in the list
- In the `Current Value` column, paste your Splunk access token
- Find the variable named `Splunk_Observability_realm` in the list
- In the `Current Value` column, enter your Splunk realm (e.g., us0, us1, eu0)
- Click `Save` to apply the changes
