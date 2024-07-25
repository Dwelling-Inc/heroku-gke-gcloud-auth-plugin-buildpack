# Heroku Google Cloud Buildpack

This buildpack installs a pinned version of the Google Cloud SDK (445.0.0). During install, it generates ```heroku-google-cloud.sh``` script in ```.profile.d``` which installs gke-gcloud-auth-plugin upon server startup.

## Credentials

This script does not set up any credentials--unlike the project it is forked from. You will need to set up your own credentials.