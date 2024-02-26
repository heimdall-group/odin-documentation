---
Created by: felix rydberg
Created time: 2023-11-18T20:14
Last edited by: felix rydberg
Last edited time: 2023-11-23T20:52
---
This document will provide an idea of the intended workflow while working in Odin.

  

### Table of contents:

- [Development flow](#Development%20flow)
    - [App](#App)
    - [Website](#Website)
    - [Internal Functions](#Internal%20Functions)
- [NPM commands](#NPM%20commands)

  

  

## Development flow

### App:

- Initiate environment:
    - Run this command to initiate app environment. This includes frontend and development backend
    - Command: [[Development - Production]]
    - This command creates the following:
        - Electron app
        - Electron front end ([[Development - Production]])
        - Electron dev-backend ([[Development - Production]])
- Refreshing Electron frontend:
    - Run this command to see changes made to website. Example is when changing frontend / public assets like pictures.
    - Command: [[Development - Production]]
- Refreshing Electron backend:
    - Run this command to see changes made to website. Example is when changing Api / Authentication flow.
    - Command: [[Development - Production]]

### Website:

Nuxt provides hot reloading (auto refresh when files are changed) during development. Production environment will have to be rebuilt using [[Development - Production]] to preview changes.

  

### Internal Functions

Since this project frontend renderd as Website and Desktop application certain interval functions has been built to provide a better code structure in frontend files.

|Name|Page|Description|
|---|---|---|
|useInternalFetch|TBD|Adds a base url to every request. Used when fetching from API|
|useInternalCookie|TBD|Depending on environment different storage solutions are used|

  

## NPM commands:

Tables are in chronological order (first row triggers first).

### web:build

Description: Builds production web application.

|Action|Description|
|---|---|
|set ENVIRONMENT=web|Sets Environment variable to web|
|set PRODUCTION=1|Sets Production to true|
|nuxt build|Triggers nuxt build command|

### web:dev

Description: Starts development web environment

|Action|Description|
|---|---|
|set ENVIRONMENT=web|Sets Environment variable to web|
|set PRODUCTION=0|Sets Production to false|
|nuxt dev|Triggers nuxt dev command|

### app:frontend

Description: Prerenders all /app routes that [[v1 Electron]] uses.

|Action|Description|
|---|---|
|set ENVIRONMENT=app|Sets Environment variable to app|
|npx nuxi generate|Triggers nuxi generate command|

### app:dev-backend

Description: Prerenders all /app routes that [[v1 Electron]] uses.

|Action|Description|
|---|---|
|set ENVIRONMENT=web|Sets Environment variable to web|
|nuxt build|Triggers nuxt build command|

### app:dev-create

Description:

|Action|Description|
|---|---|
|set PRODUCTION=0|Sets Production to false|
|npm run app:dev-assets|Triggers [app:dev-assets](#app%20dev-assets)|
|electron-builder|Builds Electron application|

### app:dev-assets

Description:

|Action|Description|
|---|---|
|set PRODUCTION=0|Sets Production to false|
|npm run app:frontend|Triggers [app frontend](#app%20frontend)|
|npm run app:dev-backend|Triggers [app dev-backend](#app%20dev-backend)|

### app:start-dev

Description: Starts electron application. If in development (PRODUCTION = 0) a nuxt development instance will be booted in the background to simulate a production deployment.

|Action|Description|
|---|---|
|electron .|Starts electron application|