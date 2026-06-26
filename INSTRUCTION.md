## 2. Deploy the ToDo App Pod and Service

kubectl apply -f todoapp-pod.yaml

## 3. Deploy the DaemonSet and CronJob

kubectl apply -f daemonset.yml
kubectl apply -f cronjob.yml

## 4. Validation

### Check DaemonSet pods are running:
kubectl get pods -n mateapp -l app=todoapp-pinger

### Check DaemonSet pod logs:
kubectl logs -n mateapp -l app=todoapp-pinger

### Check CronJob and its triggered Jobs:
kubectl get cronjob -n mateapp
kubectl get jobs -n mateapp

### Check logs of a CronJob-triggered pod:
kubectl logs -n mateapp -l <label-matching-your-cronjob-pods>

### Verify the health endpoint is reachable from a DaemonSet pod:
kubectl exec -n mateapp <daemonset-pod-name> -- curl -s http://todoapp/api/health