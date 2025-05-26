---
title: OTOBO - Hospedando Localmente com Docker
author: Victor Abreu
date: 2025-05-20 18:15:00 -0300
categories: [OTOBO]
tags: [otobo, docker, ticket, helpdesk]
---

Para conhecer o OTOBO leia esse [post](https://victoabreu.io/posts/otobo-sistema-de-tickets-e-chamados/). Nele explico como surgiu, qual a relação com o OTRS e afins.

Tendo em mente, agora precisamos rodá-lo localmente em nosso ambiente. Para isso vamos precisar de outra tecnologia chamada [conteinerização](https://www.ibm.com/br-pt/think/topics/containerization), ou simplesmente, contêineres.

## O que é Docker?

[Docker](https://www.docker.com/) é a maior plataforma para gerenciamento de containers da atualidade. Com ele somos capazes de empacotar, compartilhar e executar aplicações inteiras de forma simples. Para saber mais clique [aqui](https://www.redhat.com/pt-br/topics/containers/what-is-docker).

## Rodando no Windows ou Mac (Docker Desktop)

Inicialmente o Docker foi construído para ambientes Linux. O kernel do Linux apresenta particularidades como [cgroups](https://en.wikipedia.org/wiki/Cgroups) e [namespaces](https://en.wikipedia.org/wiki/Linux_namespaces) para separar processos uns dos outros. Felizmente o tempo passou e hoje temos versões para Windows e MacOS. Nomeada Docker Desktop podemos baixá-la [aqui](https://www.docker.com/products/docker-desktop/) de acordo com o sistema operacional preferido. Siga as instruções e ao final abra o programa para acessar a tela principal (dashboard).

![Docker Desktop](/assets/img/posts/otobo-hospedando-localmente-com-docker/docker-dashboard.png)

## Instalando com Docker e Docker Compose

Para instalar vamos precisar de alguns comandos via terminal. O Docker Desktop já vem com um integrado ao próprio ambiente. Para acessar localize o mesmo no canto inferior direito conforme a figura:

![Docker Terminal](/assets/img/posts/otobo-hospedando-localmente-com-docker/docker-terminal.png)

