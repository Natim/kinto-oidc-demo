# Kinto + OpenID Connect

## Setup

* Following this tutorial for Google https://developers.google.com/identity/protocols/OpenIDConnect
* Authorized Javascript origins: `http://localhost:3000`
* Authorized redirect URIs: `http://localhost:8888/v1/openid/token?`

## Configure Kinto

```ini

kinto.includes = kinto.plugins.default_bucket
                 kinto.plugins.openid

multiauth.policies = oidc
multiauth.policy.oidc.use = kinto.plugins.openid.OpenIDConnectPolicy

oidc.issuer_url = https://accounts.google.com
oidc.client_id = 248628588820-XXXXXXXXXXX.apps.googleusercontent.com
oidc.client_secret = UAXXXXXXXXXX
oidc.userid_field = email
```

## Run

```
    $ python3 -m http.server 3000
```

Access http://localhost:3000
