---
title: OTOBO - Hospedando Localmente com Docker
author: victoabreu
date: 2025-05-20 18:15:00 -0300
categories: [OTOBO]
tags: [otobo, docker, ticket, helpdesk]
---

Para conhecer o OTOBO leia esse [post](https://victoabreu.io/posts/otobo-sistema-de-tickets-e-chamados/). Nele explico como surgiu, qual a relação com o OTRS e afins.

Tendo em mente, agora precisamos rodá-lo localmente em nosso ambiente. Para isso vamos precisar de outra tecnologia chamada [conteinerização](https://www.ibm.com/br-pt/think/topics/containerization), ou simplesmente, contêineres.

## O que é Docker?

[Docker](https://www.docker.com/) é a maior plataforma para gerenciamento de **containers** da atualidade. Com ele somos capazes de empacotar, compartilhar e executar aplicações inteiras de forma simples. Para saber mais clique [aqui](https://www.redhat.com/pt-br/topics/containers/what-is-docker).

## Rodando no Windows ou Mac (Docker Desktop)

Inicialmente o Docker foi construído para ambientes Linux. O kernel do **Linux** apresenta particularidades como [cgroups](https://en.wikipedia.org/wiki/Cgroups) e [namespaces](https://en.wikipedia.org/wiki/Linux_namespaces) para separar processos uns dos outros. Felizmente o tempo passou e hoje temos versões para Windows e MacOS. Nomeada Docker Desktop podemos baixá-la [aqui](https://www.docker.com/products/docker-desktop/) de acordo com o sistema operacional preferido. Siga as instruções e ao final abra o programa para acessar a tela principal (dashboard).

![Docker Desktop](/assets/img/posts/otobo-hospedando-localmente-com-docker/docker-dashboard.png)

> No Linux é necessário instalar os pacotes manualmente. Para tal execute os seguintes comandos:
    **sudo apt-get install git docker docker-compose curl**
    **sudo systemctl enable docker**
{: .prompt-info }

## Instalando com Docker e Docker Compose

Para instalar o OTOBO vamos precisar de alguns comandos via **terminal**. O Docker Desktop já vem com um integrado ao próprio ambiente. Para acessar localize o mesmo no canto inferior direito conforme a figura:

![Docker Terminal](/assets/img/posts/otobo-hospedando-localmente-com-docker/docker-terminal.png)

Uma vez dentro, podemos clonar o repositório do GitHub. Escolha uma pasta para salvar o conteúdo e em seguida liste o mesmo para verificar se funcionou.

```bash
cd /opt
sudo git clone https://github.com/RotherOSS/otobo-docker.git --branch rel-10_1_10 --single-branch
cd otobo-docker
ls -la
```

Agora criamos um arquivo `.env` contendo variáveis de ambiente da nossa instalação. Quando executarmos o comando `docker compose` tal [arquivo](https://github.com/RotherOSS/otobo-docker/blob/rel-10_1/.docker_compose_env_http) define qual a [configuração](https://github.com/RotherOSS/otobo-docker/tree/rel-10_1/docker-compose) será carregada no formato YAML.

```bash
sudo cp -p .docker_compose_env_http .env
```

Edite o mesmo para adicionar uma senha ao banco de dados (a versão padrão é MariaDB). Procure a seguinte linha e defina uma password.

```bash
sudo vim .env
OTOBO_DB_ROOT_PASSWORD=<your_secret_password>
```

Chegou a hora de iniciarmos os containers!!! Simplesmente execute o comando:

```bash
sudo docker-compose up --detach
```

![Docker Compose](/assets/img/posts/otobo-hospedando-localmente-com-docker/docker-compose.png)

E para maiores detalhes, rode esses outros dois:

```bash
docker-compose ps
docker volume ls
```

## Acessando via WEB

Antes de começar a usá-lo de fato, primeiro temos que confirmar alguns dados. Faça isso através do instalador web do OTOBO. Abra um navegador e digite:

<http://localhost/otobo/installer.pl>

