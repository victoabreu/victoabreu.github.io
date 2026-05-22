---
title: Docker - Empacotando Aplicações e Sistemas
author: victoabreu
date: 2026-03-17 19:08:55 -0300
categories: [Docker]
tags: [docker, container, app]
image:
  path: /assets/img/posts/docker-empacotando-aplicacoes/docker_new.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

> **Você sabia que a [Docker, Inc.](https://en.wikipedia.org/wiki/Docker,_Inc.) não inventou os containers? E tampouco (a empresa) se chamava assim?**
{: .prompt-info }

A nossa história começa em **1979**, com o lançamento do [Unix](https://www.unix.org/about.html) versão 7 (marca registrada e por vezes denominado UNIX®). Trata-se de um sistema operacional multitarefa e multiusuário, escrito em C, altamente portável para diferentes hardwares. Sua versão original foi desenvolvida na [Bell Labs](https://en.wikipedia.org/wiki/Bell_Labs) pela AT&T. Com o passar dos anos a empresa licenciou para vários parceiros acadêmicos e comerciais. Isso gerou uma verdadeira família de sistemas chamada de unix-like. Exemplos: BSD (University of California, Berkeley); Xenix (Microsoft); Solaris/SunOS (Sun Microsystems); HP-UX (HP/HPE); AIX (IBM). Talvez os mais proeminentes e modernos sejam o Linux, macOS e Android.

Mas voltando ao Unix V7, o mesmo introduziu um sistema chamada [chroot](https://en.wikipedia.org/wiki/Chroot). Na prática ele permite ao kernel (núcleo) mudar o diretório raiz de um processo "pai" e seus "filhos" para outro completamente diferente. Ou seja, é como se o processo estivesse rodando sozinho na máquina. Tal recurso também foi adicionado ao BSD em **1982**.

Sem grandes avanços por quase duas décadas (no que hoje chamamos de isolamento de processos, ou virtualização de processos) foi somente em **2000** que um provedor de hospedagem web criou uma solução própria para gerenciamento de clientes, usando o FreeBSD, e batizando-a de [jails](https://en.wikipedia.org/wiki/FreeBSD_jail) (ou FreeBSD jails). Tendo em vista que até então os mesmos (clientes) disputavam por recursos no servidor, a partir daí o provedor conseguiu uma configuração exclusiva de IP e sistema por cliente. Na verdade, os créditos originais vão para o programador [Poul-Henning Kamp](https://people.freebsd.org/~phk/). E o nome da empresa (provedor) que o contratou era [R&D Associates, Inc](https://klarasystems.com/articles/freebsd-jails-the-beginning-of-freebsd-containers/).

Em **2006** outro marco. Engenheiros da Google desenvolvem um mecanismo para organizar, limitar e monitorar recursos (CPU, memória, disco) de um conjunto de processos. Inicialmente restrita ao uso interno, a ideia deu tão certo que dois anos mais tarde **(2008)** foi incorporada ao kernel do Linux na versão 2.6.24. A mesma ficou conhecida como [Control Groups](https://docs.kernel.org/admin-guide/cgroup-v1/cgroups.html) mas abreviada para [cgroups](https://docs.kernel.org/admin-guide/cgroup-v1/).

Ainda em **2008** é lançado o [LXC](https://linuxcontainers.org/lxc/introduction/) (LinuX Containers), o primeiro e mais completo sistema para gerenciamento de containers da época. O mesmo utilizava tecnologias como [namespaces](https://en.wikipedia.org/wiki/Linux_namespaces), o próprio `cgroups` e tantas outras. Tudo em um único kernel Linux, sem nenhum patch ou modificação, rodando nativamente.

## dotCloud e o início de tudo

O docker nasceu literalmente como uma ferramenta interna de um provedor de plataforma como serviço (PaaS) de segunda geração, chamado [dotCloud](https://www.infoq.com/news/2013/10/dotcloud-renamed-docker/). Diferente da primeira onda, onde manter várias versões de bibliotecas e ambientes de execução era muito difícil, quase impossível para novas linguagens de programação, aqui você facilmente provisionava seu(s) ambiente(s) num estalar de dedos. E tudo isso começou com [Solomon Hykes](https://www.docker.com/contributors/solomon-hykes/), [Sebastien Pahl](https://github.com/spahl) e [Kamel Founadi](https://www.linkedin.com/in/kamel-founadi-72a7b91/).

Filho de pai americano e mãe canadense, a família de Hykes imigrou para a França quando ele tinha quatro anos. Desde sempre interessou-se por computadores e portanto começou a programar aos sete. Após o ensino médio, Hykes entra para a [Epitech](https://international.epitech.eu/). Renomada escola de engenharia avançada, Hykes e Pahl se tornam colegas e grandes amigos.

Juntos fundam a dotCloud com Founadi, sediada em Paris. O ano era **2008** e concorrentes de grande peso já operavam no mercado, como [Google App Engine](https://cloud.google.com/appengine) e [Heroku](https://www.heroku.com/).

A grande sacada inicial foi construir todo o seu modelo de hospedagem baseado na recém-lançada tecnologia de contêineres, o LXC. Com isso eles foram capazes de popularizar e abstrair conceitos complexos do Linux e administração de sistemas, tornando-a assim amigável ao usuário. Desenvolvedores de forma geral passaram a focar mais nas aplicações e menos nos servidores.

Todavia, esse diferencial não estava se mostrando bom o suficiente para um meio cada vez mais acirrado e saturado de novos e velhos competidores. Por isso em **2013** houve uma mudança estratégica e de foco. Ao invés de continuar como um "mero" serviço de hospedagem web multilinguagem, agora todos os esforços iriam para o amadurecimento da plataforma de containers. Ou seja, melhorar cada vez mais a tecnologia por trás e "invisível". Na prática, a mesma ganhou status de produto e foi batizada oficialmente como Docker. Além disso, o código-fonte foi disponibilizado abertamente no [GitHub](https://github.com/shykes/docker/commit/a27b4b8cb8e838d03a99b6d2b30f76bdaf2f9e5d). No mesmo ano, durante a [PyCon](https://us.pycon.org/2013/), Hykes explica e apresenta o conceito de containers no Docker ao público presente. E finalmente, para coroar tal mudança de rumo, a própria dotCloud mudou de nome para Docker, Inc.

## 2014: Docker 0.9

A empresa troca o ambiente de execução da plataforma. Do LinuX Containers (LXC) para um novo chamado `'libcontainer'`. Escrito em [Go](https://go.dev/) e feito para melhor estabilidade.

## 2015: Open Container Initiative

A Docker auxilia na criação da [OCI](https://opencontainers.org/) como entidade responsável pelos padrões abertos para runtimes de contêineres e formatos de imagem, a serem adotados pela indústria.

## 2017: Moby Project

É criado um [projeto](https://mobyproject.org/) visando o desenvolvimento dos componentes gratuitos (open-source), distanciando um pouco da parte comercial.