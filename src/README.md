## Ferramentas

### Windows
- [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)
    - Settings -> Kubernetes -> Enable Kubernetes

- `kubectl get nodes` informações do cluster (conjunto de 1 ou mais máquinas)

    >Kubectl provê as funcionalidades de criar, ler, atualizar e remover os dados, componentes e recursos do cluster (gerenciado pelas máquinas **masters** (api, c-m, sched, etcd -> Control Plane) e cujas aplicações são executadas pelas máquinas **nodes** (kubelet, k-proxy -> Nodes)).

### Linux

- [Kubectl](https://kubernetes.io/pt-br/docs/tasks/tools/install-kubectl-linux/)
- [Minikube](https://kubernetes.io/fr/docs/tasks/tools/install-minikube/)
- [VirtualBox](https://www.virtualbox.org/)
    - `sudo dpkg –i XXXXX.deb` instala VirtualBox de acordo com arquivo especificado

- `kubectl version --client` versão instalada
- `kubectl cluster-info` estado do cluster
- `minikube start --vm-driver=virtualbox` cria um cluster local do Kubernetes na máquina virtualizada