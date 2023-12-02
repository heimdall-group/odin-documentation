---
Created by: felix rydberg
Created time: 2023-11-18T20:08
Last edited by: felix rydberg
Last edited time: 2023-11-18T20:14
---
- Depending on command different nuxt config settings will be set
- env.ENVIRONMENT set to ‘app’
- Base route is /app
    - To config this go to electron/main.ts and change serveInstance options
- If production = 0 a node js instance will be started to provide the env.DEVELOPMENT base url a endpoint.