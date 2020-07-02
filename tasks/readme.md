# Basis-Ansible-Konfiguration fuer Baikonur-Netzwerk
Rollen-Definitionen zum Einrichten des Heimnetzwerkes

## Rolle "kube_02_kubernetes_postinstall"
Einrichten des Kubernetes-Clusters (master und node) via k3s, rke, kubeadm oder minikube

## Verzeichnis "tasks"
Playbook-Tasks, welche in der Rolle durchgeführt werden

## Files:
* **initial/initial-host.yml:**
* **initial/main.yml:**
* **main.yml:**
* **postinstall/engine_kubeadm/install_rbac.yml:**
* **postinstall/engine_kubeadm/install_tiller.yml:**
* **postinstall/engine_kubeadm/install_weave.yml:**
* **postinstall/engine_kubeadm/main.yml:**
* **postinstall/install_helm.yml:**
* **postinstall/main.yml:**


#Todo:#
##Tasks to integrate:##
  kubectl create namespace cattle-system
  kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.6/deploy/manifests/00-crds.yaml
  helm install rancher rancher-stable/rancher --namespace cattle-system --set hostname=rancher.baikonur.at
  kubectl -n cattle-system rollout status deploy/rancher
