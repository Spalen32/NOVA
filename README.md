# NOVA
services:
  - type: web
    name: website1
    env: node
    rootDir: .
    buildCommand: cd . && npm install
    startCommand: cd . && npm start
    envVars:
      - key: NODE_ENV
        value: production
      - key: MONGODB_URI
        sync: false
      - key: SESSION_SECRET
        sync: false
      - key: PORT
        value: 10000
    healthCheckPath: /
    autoDeploy: true
