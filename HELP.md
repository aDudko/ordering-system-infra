# Install Helm in OS
    https://helm.sh/ru/docs/intro/install/

## Work Kafka Helm cluster
### Install and start cluster
    helm install local-confluent-kafka helm/cp-helm-charts --version 0.6.0
Need choose *apiVersion: policy/v1beta1* on *apiVersion: policy/v1* 
in file: **helm/cp-helm-charts/charts/cp-zookeeper/templates/poddisruptionbudget.yaml**
### Stop cluster
    helm uninstall local-confluent-kafka

## Work with Pods
### Testing cluster
    kubectl get pods
### Create new Pod
    kubectl apply -f kafka-client.yml
    kubectl exec -it kafka-client -- /bin/bash
### Delete Pod
    kubectl delete -f kafka-client.yml