---
title: Docker - Empacotando Aplicações e Sistemas
author: victoabreu
date: 2026-03-17 19:08:55 -0300
categories: [Docker]
tags: [docker, container, app]
image:
  path: /assets/img/posts/docker-empacotando-aplicacoes/docker_centered_optical.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

> **Você sabia que a [Docker, Inc.](https://en.wikipedia.org/wiki/Docker,_Inc.) não inventou os containers? E tampouco (a empresa) se chamava assim?**
{: .prompt-info }

A nossa história começa em **1979**, com o lançamento do [Unix](https://www.unix.org/about.html) versão 7 (marca registrada e por vezes denominado UNIX®). Trata-se de um sistema operacional multitarefa e multiusuário, escrito em C, altamente portável para diferentes hardwares. Sua versão original foi desenvolvida na [Bell Labs](https://en.wikipedia.org/wiki/Bell_Labs) pela AT&T. Com o passar dos anos a empresa licenciou para vários parceiros acadêmicos e comerciais. Isso gerou uma verdadeira família de sistemas chamada de unix-like. Exemplos: BSD (University of California, Berkeley); Xenix (Microsoft); Solaris/SunOS (Sun Microsystems); HP-UX (HP/HPE); AIX (IBM). Talvez os mais proeminentes e modernos sejam o Linux, macOS e Android.

Mas voltando ao Unix V7, o mesmo introduziu um sistema chamada [chroot](https://en.wikipedia.org/wiki/Chroot). Na prática ele permite ao kernel (núcleo) mudar o diretório raiz de um processo "pai" e seus "filhos" para outro completamente diferente. Ou seja, é como se o processo estivesse rodando sozinho na máquina. Tal recurso também foi adicionado ao BSD em **1982**.

Sem grandes avanços por quase duas décadas (no que hoje chamamos de isolamento de processos, ou virtualização de processos) foi somente em **2000** que um provedor de hospedagem web criou uma solução própria para gerenciamento de clientes, usando o FreeBSD, e batizando-a de [jails](https://en.wikipedia.org/wiki/FreeBSD_jail) (ou FreeBSD jails). Tendo em vista que até então os mesmos (clientes) disputavam por recursos no servidor, a partir daí o provedor conseguiu uma configuração exclusiva de IP e sistema por cliente. Na verdade, os créditos originais vão para o programador [Poul-Henning Kamp](https://people.freebsd.org/~phk/). E o nome da empresa (provedor) que o contratou era [R&D Associates, Inc](https://klarasystems.com/articles/freebsd-jails-the-beginning-of-freebsd-containers/).

Em **2006** outro marco. Engenheiros da Google desenvolvem um mecanismo para organizar, limitar e monitorar recursos (CPU, memória, disco) de um conjunto de processos. Inicialmente restrita ao uso interno, a ideia deu tão certo que dois anos mais tarde **(2008)** foi incorporada ao kernel do Linux na versão 2.6.24. A mesma ficou conhecida como [Control Groups](https://docs.kernel.org/admin-guide/cgroup-v1/cgroups.html) mas abreviada para [cgroups](https://docs.kernel.org/admin-guide/cgroup-v1/).