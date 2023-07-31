k8s hello world cronjob with PVC
================================

A minimal k8s `CronJob` with a `pvc` on GKE.
* `templates/cronjob.yaml` - the cronjob itself which logs into a persistent volume
* `templates/pvc.yaml` - the persistent volume claim for getting a persistent volume on GKE
* `templates/deployment.yaml` - a _viewer_ pod for viewing the `pvc` contents

# Usage

## Deploy
```
cd cronjob
helm install hello .
```
## View PVC
```
kubectl exec -it hello-viewer -- tail -f /pvc/log
```