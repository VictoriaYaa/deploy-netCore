# Deploy netCore Web Application to K8S
This repo will deploy a Web Application (netCore) in two different NS.

Deployed Jenkins in Minikube via Helm in namespace devops:
_# kubectl create ns devops_
_# helm upgrade --install jenkins jenkins/jenkins -n devops_

_# helm list                                                                                                                   
NAME   	NAMESPACE	REVISION	UPDATED                             	STATUS  	CHART         	APP VERSION
jenkins	devops   	1       	2024-03-05 02:43:38.931938 +0200 IST	deployed	jenkins-5.0.17	2.440.1_



The Web Application was used from https://github.com/MicrosoftDocs/mslearn-dotnet-kubernetes
