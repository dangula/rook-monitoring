# rook-monitoring

After Rook Cluster is deployed, you can deploy Prometheus and Grafana to monitor it.
The `deploy-monitoring` script is provided to deploy both Prometheus and Grafana and have it monitor Rook.

After you have deployed it, you can run the following to get the URL to the grafana dashboard:

```console
$ echo "http://$(kubectl -n monitoring  get svc grafana -o jsonpath={.status.loadBalancer.ingress[0].ip}):3000"
```


To teardown Prometheus and Grafana run `teardown-monitoring`