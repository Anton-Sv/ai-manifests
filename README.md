# ai-manifests
Collection of k8s yaml manifests, made by ai

| NAME                    | PROMPT                                                                                                                                                                                                                                                                                                                                                         | DESCRIPTION           | EXAMPLE                                                   |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------|-----------------------------------------------------------|
| app.yaml                | Create a pod with name demo, label demo and open port 8080, by using a container europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0. Container name is demo-app.                                                                                                                                                                                  | Simple pod            | [app.yaml](./yaml/app.yaml)                               |
| app-livenessProbe.yaml  | Create a liveness probe pod with conteiner name demo-app, source image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0, httpget on port 8080 with 15 sec delay and 30 sec period Liveness probe.                                                                                                                                               | Liveness probe        | [app-livenessProbe.yaml](./yaml/app-livenessProbe.yaml)   |
| app-readinessProbe.yaml | Create readines-probe-demo from a container named demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0 with httpget on port 8080.                                                                                                                                                                                                | Readiness probe       | [app-readinessProbe.yaml](./yaml/app-readinessProbe.yaml) |
| app-volumeMounts.yaml   | Create volume-mount-demo from container name demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0. For volumemount use data-volume with path data and readonly true, config-volume with path config and readonly false. Data-volume with pvc name my-pvc and config-volume with configmap named configmap-demo.                  | Mounting of volumes   | [app-volumeMounts.yaml](./yaml/app-volumeMounts.yaml)     |
| app-cronjob.yaml        | Create cronlob-demo with schedule every 3 minutes and template from container named demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0.                                                                                                                                                                                        | Cron job              | [app-cronjob.yaml](./yaml/app-cronjob.yaml)               |
| app-job.yaml            | Create a job with name job-demo and use container with name demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0 and restart policy never.                                                                                                                                                                                       | Job for pod           | [app-job.yaml](./yaml/app-job.yaml)                       |
| app-multicontainer.yaml | Create multicontainer-pod-demo with two source containers - first with name demo-app-v1 and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0, second with name demo-app-v2 and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v2.0.0. Second image should sleep one hour.                                                 | Multicontainer deploy | [app-multicontainer.yaml](./yaml/app-multicontainer.yaml) |
| app-resources.yaml      | Create pod with resources-demo name from container named demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0. Set resource limits to 500m cpu and 256Mi memory.                                                                                                                                                                 | Resources limit       | [app-resources.yaml](./yaml/app-resources.yaml)           |
| app-secret-env.yaml     | Create a pod with name demo-secret-env from container named demo-app and image europe-west1-docker.pkg.dev/k8s-k3s-406521/k8s-repo/demo:v1.0.0. Set first env with name secret_username and value from reference with name my-secret and key username. Set second env with name secret_password and value from reference with name my-secret and key password. | Add secret envs       | [app-secret-env.yaml](./yaml/app-secret-env.yaml)         |

