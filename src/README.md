## Ferramentas

### Windows
- [Docker Desktop](https://docs.docker.com/desktop/install/windows-install/)
    - Settings -> Kubernetes -> Enable Kubernetes

- `kubectl get nodes` informações do _cluster_ (conjunto de 1 ou mais máquinas)

    >Kubectl provê as funcionalidades de criar, ler, atualizar e remover os dados, componentes e recursos do cluster (gerenciado pelas máquinas **masters** (api, c-m, sched, etcd -> Control Plane) e cujas aplicações são executadas pelas máquinas **nodes** (kubelet, k-proxy -> Nodes)).

### Linux
- [Kubectl](https://kubernetes.io/pt-br/docs/tasks/tools/install-kubectl-linux/)
- [Minikube](https://kubernetes.io/fr/docs/tasks/tools/install-minikube/)
- [VirtualBox](https://www.virtualbox.org/)
    - `sudo dpkg –i XXXXX.deb` instala VirtualBox de acordo com arquivo especificado

- `kubectl version --client` versão instalada
- `kubectl cluster-info` estado do _cluster_
- `minikube start --vm-driver=virtualbox` cria um _cluster_ local do Kubernetes na máquina virtualizada

### Google Cloud Plataform
- Novo Projeto -> Kubernetes Engine -> Criar _cluster_

## Conceitos e resumos
- Pod é o conjunto de 1 ou mais containers
- Containers em um POD compartilham o mesmo IP, mas devem possuir portas diferentes
- Containers em um POD podem compartilhar volumes
- POD's são efêmeros, ou seja, ao criar um POD efetivamente trata-se um novo POD e não o POD anterior "renascido"
- _Labels_ são pares de `chave x valor` utilizadas para vincular `Service x POD`
- _Services_ (svc) (_ClusterIP_, _NodePort_, _LoadBalancer_) são abstrações para expor aplicações executando em um ou mais POD's, proveem IP's fixos, DNS e fazem balanceamento de carga
    - _ClusterIP_ faz a comunicação entre diferentes POD's dentro de um mesmo _cluster_ (unilateral, ou seja, apenas o POD com o _service_ implementado pode ser acessado de maneira estável, mas não fora do _cluster_)
    - _NodePort_ libera comunicação com o mundo externo. Também funciona como _ClusterIP_

        >Para acesso externo no Windows utilizar `localhost:<nodePort>`. No Linux (minikube) utilizar o `internal-ip` do node.

    - _LoadBalancer_ libera comunicação com o mundo externo automaticamente integrado ao _LoadBalancer_ do provedor (AWS, Azure, Google Cloud Plataform e etc)

## Comandos
- `kubectl run <nome-pod> --image=<nome-imagem>:<versão>` cria um POD com a imagem especificada de maneira imperativa
- `kubectl get pods` lista POD's
    - `kubectl get pods --watch` inicia monitoramento dos POD's
    - `kubectl get pods -o wide` | `kubectl get nodes -o wide` formata o output de maneira wide
- `kubectl describe pod <nome-pod>` detalhes do POD
- `kubectl edit pod <nome-pod>` edita o POD
- `kubectl apply -f <nome-arquivo>.yaml/.json` aplica arquivo para criar POD de maneira declarativa
- `kubectl delete pod <nome-pod>` deleta POD especificado
    - `kubectl delete -f <nome-arquivo>.yaml/.json` deleta POD definido pelo arquivo
    - `kubectl delete pods --all` | `kubectl delete svc --all` deleta todos os itens especificados
- `kubectl exec -it <nome-pod> -- <comando>` executa de maneira interativa o comando especificado (Ex.: _bash_). Para sair: `Ctrl + D`
- `kubectl get services` ou `kubectl get svc` lista serviços