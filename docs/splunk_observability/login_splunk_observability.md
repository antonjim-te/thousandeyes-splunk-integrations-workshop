# Login to Splunk Observability Cloud

This guide will help you log into Splunk Observability Cloud and obtain an access token for the ThousandEyes stream.

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
    
    ### Verify Your Account
    - Check your email for a verification message
    - Click the verification link to activate your account
    - Complete your profile setup
    - Access your new Splunk Observability Cloud dashboard

## Generate Access Token

Once you're logged into Splunk Observability Cloud, generate your access token:

- Navigate to the `Settings` -> `Access Tokens`
- Click `Create Token`
- Configure the token settings:
    - `Name`: Enter a descriptive name (e.g., "ThousandEyes Integration Token")
    - `Scope`: Select `INGEST` and `API` 
        - Check `Please accept to continue with your selection.`
- Click `Next` to proceed
- Copy the token

![access token](../img/splunk_observability/access_token.png)

## Postman Variables

Now that you have your Splunk Observability Cloud access token and realm, add it to your Postman collection variables:

- In Postman, navigate to your `ThousandEyes Splunk Integration` collection
- Go to the `Variables` tab
- Find the variable named `Splunk_Observability_access_token` in the list
    - In the `Current Value` column, paste your Splunk access token
- Find the variable named `Splunk_Observability_realm` in the list
    - In the `Current Value` column, enter your Splunk realm (e.g., `us0`, `us1`, `eu0`)
        - For example if your Splunk Observability Cloud URL is `https://us0.signalfx.com`, then your realm is `us0`.
- Click `Save` to apply the changes

![splunk observability variables](../img/postman/splunk_observability_variables.png)