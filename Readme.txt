########################################
    APP DEPLOYMENT USING KUBERNETES
########################################

Learning Resource:
    https://www.youtube.com/watch?v=EQNO_kM96Mo&list=PLy7NrYWoggjziYQIDorlXjTvvwweTYoNC&index=8
    - we can do same app stuff in 1 yaml file using separator `---` 
      but for learning purpose, everything is in separate files.

App Design:
    1. Database App (Mongo Db)
    2. Mongo Web App (mongo-express: web interface for mongo Db).

Kubernetes components:
    1. secrets for mongo.               (mongo-secret.yaml)
    2. deployment for mongo.            (mongo-deploy.yaml)
    3. internal-service for mongo.      (mongo-internal-svc.yaml)
    4. configuration map for web-mongo. (web-mongo-config.yaml)
    5. deployment for web-mongo.        (web-mongo-deploy.yaml)
    6. external-service for web-mongo.  (web-mongo-external-svc.yaml)

Summary:
    when we will visit http://<master-node-ip>:30000. 
    communication will be.
    |
    '-> web-mongo external service
      |
      '-> web-mongo pod
        |
        '-> mongo internal service
            |
            '-> mongo db pod