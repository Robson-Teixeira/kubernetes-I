## Ferramentas

### Windows
- [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)
    - Settings -> Kubernetes -> Enable Kubernetes

- `kubectl get nodes` informações do cluster (conjunto de 1 ou mais máquinas)

    >Kubectl provê as funcionalidades de criar, ler, atualizar e remover os dados, componentes e recursos do cluster (gerenciado pelas máquinas **masters** (api, c-m, sched, etcd -> Control Plane) e cujas aplicações são executadas pelas máquinas **nodes** (kubelet, k-proxy -> Nodes)).