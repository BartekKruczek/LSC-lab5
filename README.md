# Description of the project

## Used files

In order to complete the project, the following files were used:
- lscconfig.yaml (configuration file for kind cluster creation)
- lcspvc.yaml (persistent volume claim file)
- lscdeployment.yaml (deployment file)
- lscservice.yaml (service file)
- lsccopyjob.yaml (copy job file)

After that, we could have seen `Hello from Kubernetes!` under the `http://localhost:30000` address.

## Used commands in terminal

- kind create cluster --name lscdocker --config=lscconfig.yaml
- helm install nfs-server-provisioner nfs-ganesha-server-and-external-provisioner/nfs-server-provisioner --set=storageClass.name=lscdocker
- kubectl apply --context kind-lscdocker --filename=lscpvc.yaml
- kubectl apply --context kind-lscdocker --filename=lscdeployment.yaml
- kubectl apply --context kind-lscdocker --filename=lscservice.yaml
- kubectl apply --context kind-lscdocker --filename=lsccopyjob.yaml
