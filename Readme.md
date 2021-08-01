# Getting Started

This is simple project which show how to integrate spring boot app with different oauth providers

By default spring auth has integration(CommonOAuth2Provider) with github, google, facebook, okta if we need connect other we can see it by example auth0.
## Github

navigate to github acc ->settings->developer settings->OAuth Apps->
register new App->
name=
homepage=http://localhost
calback=http://localhost/login/oauth2/code/github

-> Register app.

Get id, secret and paste it to application.yml


## Facebook

navigate to https://developers.facebook.com

cereate App - > users ->

name="""   ->create


-> create test app(from above created)

-> settings  copy id and secret and paste to application.yml 

-> signup from facebook -> settings "url to redirect oauth =http://localhost/login/oauth2/code/facebook"


## Auth0

create App -> regular web app ->

name="" "   ->create

-> settings -> copy id, secret,domain ->advanced settings copy urls to application.yml

callvack=http://localhost/login/oauth2/code/my-app

->auth pipeline - > Rules -> IDTOKEN-RULE

```
function(user, context, callback){
const fieldName='http://localhost/authorities';
context.idToken[fieldName] = ["CREATE_MESSAGE" , "DELETE_MESSAGE"];
return callback(null, user, context);
}
```

## Run

After steps above you can just run spring boot app.
