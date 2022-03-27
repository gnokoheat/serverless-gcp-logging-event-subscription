# GCP Logging Sink Subscription Example

This example demonstrates how to trigger a cloud functions when a specific event occurs in Google Cloud Platform project.

## How to work

GCP project event -> Logging sink -> Pub/Sub -> Cloud functions

## Use Cases

- When a storage bucket is created, the cloud function is called. Event details are left in the cloud function log.
  - `protoPayload.methodName:("storage.buckets.create")`
- You can change the filter to receive the desired events.
  - `severity="ERROR"`, Filtering error events.
  - `protoPayload.methodName:("compute.instances.insert" OR "beta.compute.instances.insert")`, Filtering instance creation events

## Setup

You should add permission `Logging` to IAM of `cloudservices.gserviceaccount.com` before deployment. This is required to create a logging sink in the deployment manager.

## Run
Install serverless framework
```
npm install -g serverless
```
Deploy features
```
serverless deploy
```
