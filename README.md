# ttrss-kubernetes

Deployment test of [ttrss](https://tt-rss.org/) using [k3s.io](https://k3s.io/). The goal is to use as many kubernetes resources as possible to run this traditional php application.
It automatically polls the git repository for updates and updates the application once per night. The feed updater is executed every 5 minutes.

## Requirements
- Database (postgres)
- Kubernetes cluster (e.g. [k3s.io](https://k3s.io))
- Some time to play around with kubernetes

## Deploying the application
1. Create a new namespace for ttrss
> `kubectl apply -f k8s/namespace.yml`
2. Duplicate the sample configuration to a safe location so your credentials do not end up on github.
> `cp sample-config ../`
3. Create a database schema and user (currently only postgres supported by the docker image). Configure the username and password in `secrets/db-credentials.env`
4. Update the rest of the configuration variables in `configmap/app-config.env`
5. Deploy application
> user@localhost ~/sample-config `kubectl apply -k .`