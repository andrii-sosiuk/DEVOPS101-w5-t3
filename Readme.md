
## KUBECTL-AI
This is an example of using AI to create manifests for Kubernetes. The kubectl-ai tool was used to produce the demo.


| Name                  | Prompt                                                    | Description                | Example  |
|-----------------------|-----------------------------------------------------------|----------------------------|----------|
| Simplea application   | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. Add lables | Create simple Nginx application | app.yaml |
| Livness check | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. Add lables. Add livnes with timeout 1 and period 10. | App and Liveness | app-livenessProbe.yaml |
| Liveness plus readness | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. Add lables. Add livnes with timeout 1 and period 10. Add readness probe with period 2 | App livness and readness | app-readinessProbe.yaml |
| Livness plus readness | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. Add lables. Add livnes with timeout 1 and period 10. Add readness probe with period 2. Add volume mount from host /var/lib/data to /data. | All abowe plus volume mount | app-volumeMounts.yaml |
| Cron job | I need a cron jon scedguled fo every 5 min running command echo Hello world. | Cron job Hello world every 5 min | app-cronjob.yaml |
| A job | I need a job. Name app-job-rsync. Never restarts. mounts to /data/input, run sh script gsutil -m rsync -dr gs://glow-sportradar/ /data/input uses google/cloud-sdk:275.0.0-alpine with volume named data-input on persistent disk glow-data-disk-200 | Kubernetes Job | app-job.yaml |
| Multicontainer | I need a multicontainer app on one pod which consist of 2 containers. First is nginx maintaining default html directory second will be a bash script written as a command line. Script whould writre current date to index.html every second | Multicontainer job | app-multicontainer.yaml |
| Limit resources | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. Add lables. Add livnes with timeout 1 and period 10. Add readness probe with period 2. Limit cpu to 100m and memory to 256mi | Limit resources | app-resources.yaml |
| Env VARs | I need a Kubernetes manifest to deploy a simple application. Please include the following specifications: Application Name: SimpleApp, Container Image: nginx:latest, Port: 80x. Don\'t use deployment. I need just a pod. app Should take env vars SECRET_USERNAME and SECRET_PASSWORD | Use environment variables | app-secret-env.yaml |`

