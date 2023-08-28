# CI/CD Project

Using the ArgoCD_Jenkins.file the building, testing, deploying, and monitoring process for a Kubernetes application using Docker, ArgoCD, and Google Cloud Platform (GCP) services. <br />


## Workflow Overview
![image](https://github.com/yotamdavid/ferari_finel/assets/134198738/d1769800-4b98-41a1-938d-4ca381c6ee78)


🛠️ **Build**: Starts with building a Docker image of the application, and pushing it to Docker Hub.

✅ **Test**: After building, the application is deployed to a test cluster that create with terraform, by using k8s.

🌐 **Deploy**: After successful testing, the application is deployed to a production cluster using ArgoCD.

📈 **Monitor**: Finally, the monitoring components (Prometheus and Grafana) are installed on the production cluster.
