npm init -y
npm install typescript ts-node-dev express @types/express
tsc --init

Swap package.json "test" script command to: "start": "ts-node-dev src/index.ts"

Test Set-up:
...
import express from 'express';
import { json } from 'body-parser';

const app = express();
app.use(json());

app.listen(3000, () => {
console.log('Listening on port 3000');
});

Dockerfile Set-up
.dockerignore

Google Cloud CI/CD Set-up

gcloud auth application-default login

Credentials saved to file: [/Users/chaseriddick/.config/gcloud/application_default_credentials.json]

These credentials will be used by any library that requests Application Default Credentials (ADC).

Quota project "tickets-dev-381601" was added to ADC which can be used by Google client libraries for billing and quota. Note that some services may still bill the project owning the resource.
Chases-MacBook-Air:Ticketing chaseriddick$ skaffold dev

Skipping test and deploy due to build error:build [us.gcr.io/tickets-dev-381601/auth] failed: getting cloudbuild client: google: could not find default credentials. See https://developers.google.com/accounts/docs/application-default-credentials for more information.

This page describes the locations where Application Default Credentials (ADC) looks for credentials. Understanding how ADC works can help you understand which credentials ADC is using, and how it's finding them.

Application Default Credentials (ADC) is a strategy used by the Google authentication libraries to automatically find credentials based on the application environment. The authentication libraries make those credentials available to Cloud Client Libraries and Google API Client Libraries. When you use ADC, your code can run in either a development or production environment without changing how your application authenticates to Google Cloud services and APIs.

For information about how to provide credentials to ADC, see Set up Application Default Credentials.

Search order
ADC searches for credentials in the following locations:

GOOGLE_APPLICATION_CREDENTIALS environment variable
User credentials set up by using the Google Cloud CLI
The attached service account, returned by the metadata server
The order of the locations ADC checks for credentials is not related to the relative merit of each location. For help with understanding the best ways to provide credentials to ADC, see Set up Application Default Credentials.
