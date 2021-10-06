# SpringBoot-Helm-Chart-Example
SpringBoot-Helm-Chart-Example

kubectl --namespace kube-system create sa tiller

kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller

helm init --override spec.selector.matchLabels.'name'='tiller',spec.selector.matchLabels.'app'='helm' --output yaml | sed 's@apiVersion: extensions/v1beta1@apiVersion: apps/v1@' | kubectl apply -f -

https://www.katacoda.com/vikas-poddar-slalom/scenarios/session-03-lab1-helm-intro

helm install --name spring-boot-chart ./springSpringBoot-Helm-Chart-Example
