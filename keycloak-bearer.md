# Setting up Keycloak with Express in bearer configuration

Set your applications 'Access type'  to bearer only

[![keycloak bearer.png](https://s14.postimg.org/hnpcj6341/keycloak_bearer.png)](https://postimg.org/image/qvhkzva65/)


Download the keycloak.json file from 'Installation'
```$xslt
{
  "realm": "test",
  "bearer-only": true,
  "auth-server-url": "http://keycloak-server-snapscreen.74.207.224.48.xip.io/auth",
  "ssl-required": "external",
  "resource": "snapscreenServer"
}

```
Install keycloak-connect npm to your project
```
npm install keycloak-connect --save
```

import keycloak-connect 
```
const Keycloak = require('keycloak-connect');
```

Instantiate keycloak and protect route

```$xslt
// keycloak-connect needs an object for new Keycloak() to compile
app.keycloak = new Keycloak({});

app.use(app.keycloak.middleware());
app.use(app.keycloak.middleware( { logout: '/'} ));

// endpoint tests
app.get('/test', app.keycloak.protect(), function(req, res){
  res.json({ message: 'test' });
});
```

To test your route you need a bearer token, You can generate a one time client access token in Realm Settings\Client Registeration

[![initial access token.png](https://s17.postimg.org/lukkjrlnj/initial_access_token.png)](https://postimg.org/image/qt82yapgb/)

This can only be viewed on creation so copy and paste it somewhere, if misplaced create a new one.

[![initial access token 2.png](https://s9.postimg.org/ld3lzfd8v/initial_access_token_2.png)](https://postimg.org/image/lpv05lvij/)

This is a bearer token and can be used to access the route 

http://localhost:3000/test/

By adding the header 

```
Authorization Bearer eyJhbGciOiJSUzI1NiIsImtpZCIgOiAiOHN3ZkU0b0VvbDZCdjFXeVZDdzZVandNYUtyaEg5N3NvdTdwcy1XS1lJTSJ9.eyJqdGkiOiIxMDNmMjY2Zi00YmRkLTRhNGUtODAxMy0zNTgzNGI5YzNiM2IiLCJleHAiOjE1MDE2NzM5NzgsIm5iZiI6MCwiaWF0IjoxNDkzMDMzOTc4LCJpc3MiOiJodHRwOi8va2V5Y2xvYWstc2VydmVyLXNuYXBzY3JlZW4uNzQuMjA3LjIyNC40OC54aXAuaW8vYXV0aC9yZWFsbXMvU25hcFNjcmVlbiIsImF1ZCI6Imh0dHA6Ly9rZXljbG9hay1zZXJ2ZXItc25hcHNjcmVlbi43NC4yMDcuMjI0LjQ4LnhpcC5pby9hdXRoL3JlYWxtcy9TbmFwU2NyZWVuIiwidHlwIjoiSW5pdGlhbEFjY2Vzc1Rva2VuIn0.Z9HPq2bYHQWARXq02sssVsacWud106HTQxoczjaQIy7llXa5UI6dL_y2ctxiWs3J2_wXAp9aVtDeSqdAIT2cBudOlkuHodhtHLbeMf7gTimgZ3D9W--hKfvHj3fZ8JaxD7Sm1v4GNSB_T6ME5hepnK-7srE8tVI9zlLH8qK8jbP1ICEAcMwFfjngixsBtKIV-1PkwIcQg2ldx9mBaibl_9ALp9uCXmzA78cAlpWxy-TV808TwgON4bcN_TGGwtRudMJhANQXKYvVSM0ZApBFioIWwUYQA6pV4g4lZFVG-K1phnsa9i4qP03G_W8RaEHxTcLAE3LGRsiivAfMcm9gTQ
```

# Video of Bearer in action 

[![ScreenShot](https://s23.postimg.org/ptaa5yz57/keycloak-express-bearer.png))](https://www.youtube.com/edit?o=U&video_id=UaV3kBEZ9N8)

