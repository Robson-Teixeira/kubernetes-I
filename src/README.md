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

### Google Cloud Plataform
- Novo Projeto -> Kubernetes Engine -> Criar cluster

## Conceitos e resumos
- Pod é o conjunto de 1 ou mais containers
- Containers em um POD compartilham o mesmo IP, mas devem possuir portas diferentes
- Containers em um POD podem compartilhar volumes
- POD's são efêmeros, ou seja, ao criar um POD efetivamente trata-se um novo POD e não o POD anterior "renascido"

## Comandos
- `kubectl run <nome-pod> --image=<nome-imagem>:<versão>` cria um POD com a imagem especificada de maneira imperativa
- `kubectl get pods` lista POD's
    - `kubectl get pods --watch` inicia monitoramento dos POD's
- `kubectl describe pod <nome-pod>` detalhes do POD
- `kubectl edit pod <nome-pod>` edita o POD
- `kubectl apply -f <nome-arquivo>.yaml/.json` aplica arquivo para criar POD de maneira declarativa