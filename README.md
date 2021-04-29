# Master Helm Chart For Spring Boot Application

You should helm v3 

You can use chart this command

helm upgrade  -i example-service ./ -n example-namespace --set ingress.path=example-service \
--set ingress.host=dev.example.com  --set image.repository=hub.docker.com/example/master-service \
--set image.tag=example-tag  --set image.env.ETCD_ENDPOINT=http://etcd.example-etcd.svc.cluster.local:2379 \
--set image.env.ETCD_NAMESPACE=/example/master-service  --set secret.enabled=false --set image.env.ortam=dev \
--set readinessProbe.initialDelaySeconds=90 --set livenessProbe.initialDelaySeconds=90

#Environments

image.env.ortam             environment for application branch specific configs
image.env.ETCD_ENDPOINT     ETCD uri for spring boot config backend
image.env.ETCD_NAMESPACE    ETCD tree path for app configs
secret.enabled              if true, you can use username password secret for docker image repository
