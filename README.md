# CI/CD Project

This GitHub Actions workflow automates the building, testing, deploying, and monitoring process for a Kubernetes application using Docker, ArgoCD, and Google Cloud Platform (GCP) services. <br />
This pipeline gives developers the option to deploy their app with a simple push.

## Workflow Overview
![image](https://github.com/yotamdavid/ferari_finel/assets/134198738/d1769800-4b98-41a1-938d-4ca381c6ee78)


🛠️ **Build**: The workflow starts with building a Docker image of the application, and pushing it to Docker Hub.

✅ **Test**: After building, the application is deployed to a test cluster that create with terraform, by using k8s.

🌐 **Deploy**: After successful testing, the application is deployed to a production cluster using ArgoCD.

📈 **Monitor**: Finally, the monitoring components (Prometheus and Grafana) are installed on the production cluster.

## Workflow Setup

1. Ensure you have these credentials saved as secrets in your repository settings:

   - `DOCKER_USERNAME`: Your Docker Hub username.
   - `DOCKER_PASSWORD`: Your Docker Hub password.
   - `API_KEY` : Your app API key , if there is a need
   - `GCP_SERVICE_ACCOUNT_KEY`: Contents of your GCP service account key JSON file.

2. Configure the required environment variables:

   - `PROJECT_ID`: Your GCP project ID.
   - `REGION`: Your server location.
   - `SERVER_NAME`: Your server name.
3. That's it! Push your code changes to the main branch to trigger the workflow.

GCP serverless Cloud Functions can be triggered automatically using an event trigger, but due to financial considerations, it is triggered manually during the cleanups job in the workflow.
