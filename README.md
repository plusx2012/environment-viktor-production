# default-environment-charts
The default git repository used when creating new GitOps based Environments

```bash
SLACK_WEBHOOK_URL=[...]

cat alertmanager.yaml \
    | sed -e "s@SLACK_WEBHOOK_URL@$SLACK_WEBHOOK_URL@g" \
    | tee alertmanager-secret.yaml

kubectl -n cd-production \
    apply -f alertmanager-secret.yaml

kubectl -n cd-production \
    apply -f k8s/issuer.yaml
```


