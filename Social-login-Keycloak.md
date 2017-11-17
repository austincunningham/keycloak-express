# Social Login with Keycloak

First this is very well documented at 
http://www.keycloak.org/docs/latest/server_admin/index.html#social-identity-providers

But here are a few tips

- Click on identity providers
- Click on the dropdown to select a provider or select an existing provider

[![keycloak-social.png](https://s21.postimg.org/vqhf1f8bb/keycloak-social.png)](https://postimg.org/image/4fw3ti5eb/)

- After selection you will be brought to the following screen 


[![social-setup.png](https://s13.postimg.org/pkcr3ftl3/social-setup.png)](https://postimg.org/image/mq9lpzrer/)

Most Social login providers need the redirect URI.
 
They usually provide the Client ID and Client Secret

Sometimes called the Application ID and secret, Consumer Key and secret

The inbuilt list is below with links to there developer consoles

- Google https://cloud.google.com/console/project
- Facebook https://developers.facebook.com/
- Twitter https://dev.twitter.com/apps
- LinkedIn https://www.linkedin.com/secure/developer
- Microsoft https://account.live.com/developers/applications/create
- GitHub https://github.com/settings/applications
- Stackoverflow http://stackapps.com/apps/oauth/register
You have to be registered with https://stackapps.com/ first for Stackoverflow

## Login Screen after setup

[![social login.png](https://s24.postimg.org/4rufb2lmd/social_login.png)](https://postimg.org/image/oz7v3dj3l/)

Clicking on a social login creates a new user on the Keycloak server

