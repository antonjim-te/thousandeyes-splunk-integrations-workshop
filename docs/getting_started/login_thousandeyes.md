# Log In to ThousandEyes

Choose one of the following options to access ThousandEyes:

=== "Existing Account"

    If you already have a ThousandEyes account:
    
    1. Go to the [ThousandEyes login page](https://app.thousandeyes.com/login).
    1. Enter your email address and password.
    1. Click **Sign In**.
    <!-- FIXME: I'd suggest using a formatting convention for UI literals that isn't a monospace/code-formatted option. You'll want to preserve things that look like code for things that are actually code :) -->

=== "Free Trial"

    If you don't have a ThousandEyes account:
    
    1. Navigate to [create a ThousandEyes free trial](https://www.thousandeyes.com/signup).
    1. Fill out the registration form with your business information.
    1. Verify your email address.
    1. Sign in to your trial account.

## Get Your ThousandEyes Bearer Token

Once you're logged into ThousandEyes, follow these steps to generate your API bearer token:

1. Navigate to your user profile:

   In the left-hand navigation bar, select  **Manage >Account Settings > Users and Roles**.
   
2. Generate the API token:

   On the **Profile** tab, scroll down to the **User API Tokens** section.
   
   Click **Generate OAuth Bearer token**. <!-- FIXME: If you have generated an API token in the past, the button is labeled **Regenerate**. Should the user copy the existing one, or regenerate? -->
   
   Copy the token.

   ![copy Token](../img/thousandeyes/copyToken.png)
  
## Add Your Token to Your Postman Variables

Now that you have your ThousandEyes bearer token, add it to your Postman collection variables:

1. In Postman, navigate to your `ThousandEyes Splunk Integration` collection.
1. Go to the **Variables** tab.
1. Find the variable named `ThousandEyes_token` in the list.
    - In the **Current Value** column, paste your bearer token.
1. Click **Save** to apply the changes.

   ![ThousandEyes Token](../img/postman/thousandeyesToken.png)
