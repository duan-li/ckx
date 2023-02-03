# Env Variables

 - CKA
    - Workload and Scheduling
    - App Lifecycle
    - Env Variables

1. Update the environment variable on the POD to display a green background
  - Pod Name: webapp-color
  - Label Name: webapp-color
  - Env: APP_COLOR=green
2. Update the environment variable on the POD to use the newly created ConfigMap
  - Pod Name: webapp-color
  - EnvFrom: webapp-config-map