
# Keycloak-Express

## About
This is a Node js Express app that uses Keycloak to protect the /test route, 
Login and user setup are controlled by keycloak. The default route / is unprotected. 
The /logout route kills the keycloak session. 

## Demo Video

[![ScreenShot](https://s11.postimg.org/5524le62b/keycloak-express.png)](https://youtu.be/VAzI7f3pxec)

### Installation

clone the repo and run **npm install**

### Dependancies 
- Keycloak
- Node
- express
- npm 

### Requirements 
Need to have a Keycloak server up and running

Download Keycloak at 

http://www.keycloak.org/downloads.html

Setup Keycloak as outline at 

https://keycloak.gitbooks.io/documentation/getting_started/topics/first-boot.html

Setup a Realm
https://keycloak.gitbooks.io/documentation/getting_started/topics/first-realm.html

Setup a Open ID Connect Client
https://keycloak.gitbooks.io/documentation/server_admin/topics/clients/client-oidc.html


To use the Node.js adapter, first you must create a client for your application in the Keycloak Administration Console. The adapter supports public, confidential, and bearer-only access type. Which one to choose depends on the use-case scenario.

Once the client is created click the Installation tab, select Keycloak OIDC JSON for Format Option, and then click Download. The downloaded keycloak.json file should be at the root folder of your project.
See 
https://keycloak.gitbooks.io/documentation/securing_apps/topics/oidc/nodejs-adapter.html