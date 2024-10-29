# dicaskubernetes
KUBERNETES IS EASY, IT'S HARD TO LIKE JAVA

# **Container Engine**

Antes de começar a falar um pouco mais sobre o Kubernetes, nós primeiro precisamos entender alguns componentes que são importantes no ecossistema do Kubernetes, um desses componentes é o Container Engine.

O *Container Engine* é o responsável por gerenciar as imagens e volumes, é ele o responsável por garantir que os os recursos que os containers estão utilizando está devidamente isolados, a vida do container, storage, rede, etc.

Hoje temos diversas opções para se utilizar como *Container Engine*, que até pouco tempo atrás tinhamos somente o Docker para esse papel.

Opções como o Docker, o CRI-O e o Podman são bem conhecidas e preparadas para o ambiente produtivo. O Docker, como todos sabem, é o Container Engine mais popular e ele utiliza como Container Runtime o containerd.

Container Runtime? O que é isso?

Calma que vou te explicar já já, mas antes temos que falar sobre a OCI. :)

# **OCI - Open Container Initiative**

A OCI é uma organização sem fins lucrativos que tem como objetivo padronizar a criação de containers, para que possam ser executados em qualquer ambiente. A OCI foi fundada em 2015 pela Docker, CoreOS, Google, IBM, Microsoft, Red Hat e VMware e hoje faz parte da Linux Foundation.

O principal projeto criado pela OCI é o *runc*, que é o principal container runtime de baixo nível, e utilizado por diferentes *Container Engines, como o Docker. O *runc* é um projeto open source, escrito em Go e seu código está disponível no GitHub.

Agora sim já podemos falar sobre o que é o Container Runtime.

# **O Container Runtime**

Para que seja possível executar os containers nos nós é necessário ter um *Container Runtime* instalado em cada um dos nós.

O *Container Runtime* é o responsável por executar os containers nos nós. Quando você está utilizando Docker ou Podman para executar containers em sua máquina, por exemplo, você está fazendo uso de algum *Container Runtime*, ou melhor, o seu Container Engine está fazendo uso de algum *Container Runtime*.

Temos três tipos de *Container Runtime*:

- Low-level: são os *Container Runtime* que são executados diretamente pelo Kernel, como o runc, o crun e o runsc.
- High-level: são os *Container Runtime* que são executados por um *Container Engine*, como o containerd, o CRI-O e o Podman.
- Sandbox: são os *Container Runtime* que são executados por um *Container Engine* e que são responsáveis por executar containers de forma segura em unikernels ou utilizando algum proxy para fazer a comunicação com o Kernel. O gVisor é um exemplo de *Container Runtime* do tipo Sandbox.
- Virtualized: são os *Container Runtime* que são executados por um *Container Engine* e que são responsáveis por executar containers de forma segura em máquinas virtuais. A performance aqui é um pouco menor do que quando temos um sendo executado nativamente. O Kata Containers é um exemplo de *Container Runtime* do tipo Virtualized.


# **O que é o Kubernetes?**

Kubernetes (ou k8s) é uma plataforma open-source criada pela Google em 2014 para orquestrar contêineres, ajudando a gerenciar e automatizar a execução de aplicativos em contêineres. Inspirado no projeto Borg da Google, o Kubernetes facilita o controle e a escalabilidade de ambientes complexos de contêineres, organizando-os para otimizar o uso de recursos e garantir alta disponibilidade.

**Aqui estão alguns dos conceitos fundamentais do Kubernetes (k8s) que ajudam a entender sua abordagem ao gerenciamento de contêineres:**

Pods: A menor unidade gerenciada pelo Kubernetes, consistindo em um ou mais contêineres que compartilham a mesma rede e armazenamento. O k8s organiza e controla os contêineres por meio de pods, que podem ser criados e removidos conforme as necessidades da aplicação.

Nodes: Máquinas, que podem ser físicas ou virtuais, responsáveis por hospedar e executar os pods. Um cluster Kubernetes é formado por vários nodes, que são gerenciados de maneira automática.

Cluster: Conjunto de nodes que trabalham em conjunto e formam a estrutura fundamental do Kubernetes para organizar e orquestrar os recursos de computação.
