# Heroku Google Cloud Buildpack

This buildpack installs a pinned version of the Google Cloud SDK (445.0.0). During install, it generates a ```google-credentials.json``` file in the build directory, and generates a ```heroku-google-cloud.sh``` script in ```.profile.d``` which activates the Google service account with this credentials file upon server startup.

## Credentials

This script generates a credentials file using the following environment variables. If they're not present, the Google Cloud SDK will be installed, but this buildpack won't generate the credentials file or set the SDK to auth on server startup:

* ```GOOGLE_CREDENTIALS_JSON```

Set the key as a Heroku config variable:

```bash
heroku config:set GOOGLE_CREDENTIALS_JSON='{"type": "service_account", ...}'
```
