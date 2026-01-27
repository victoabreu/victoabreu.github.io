---
title: Ansible - Automatizando Infraestrutura
author: victoabreu
date: 2026-01-26 20:55:30 -0300
categories: [Ansible]
tags: [ansible, sysadmin, devops, iac, yaml, ssh]
image:
  path: /assets/img/posts/ansible-automatizando-infraestrutura/ansible_by_redhat.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

Gerenciar centenas de servidores, dezenas de aplicações, e uma dúzia de tarefas complexas todos os dias, não é nada fácil para um sysadmin ou time devops. Não importando o tamanho da empresa, tais desafios são oportunidades para testar ferramentas que auxiliem a implantação e manutenção em massa à nível de software.

Uma delas com certeza será o [Ansible](https://www.ansible.com/). Trata-se de uma plataforma de código-aberto para automação de sistemas Linux, macOS e Windows.

Para ilustrar o seu potencial, a mesma necessita apenas de [Python](https://www.python.org/), [SSH](https://www.openssh.org/) e [YAML](https://yaml.org/) para funcionar.

## História

### ANTES: CFEngine, Puppet e Chef

No passado, propostas similares ao Ansible, principalmente para gerenciamento de configuração, necessitavam de agentes em cada nó. Isso acabava consumindo recursos (memória, armazenamento, processsamento, rede) dos hospedeiros. Os resultados muitas vezes eram arquiteturas master-slave enormes e complexas, dificultando o entendimento e expansão.

Bons exemplos são [CFEngine](https://cfengine.com/), [Puppet](https://www.puppet.com/) e [Chef](https://www.chef.io/).

### CRIADOR: Michael DeHaan

O autor do Ansible trabalhou na [Red Hat](https://www.redhat.com/pt-br) e criou o [Cobbler](https://cobbler.github.io/). Um servidor de provisionamento de múltiplos sistemas operacionais por meio da rede. Ele também foi co-autor do "Fedora Unified Network Controller" a.k.a FUNC. Sendo esse um framework para administração remota. Na prática, outro sistema de automação.

Com todo esse conhecimento, em 2012, [Michael DeHann](https://opensource.com/users/mpdehaan) escreve o Ansible e compartilha no [GitHub](https://github.com/ansible/ansible).

### 2013: Ansible, Inc. (originalmente AnsibleWorks, Inc.)

É fundada a empresa para suporte comercial e patrocínio da ferramenta. Por DeHaan, Timothy Gerla, and Saïd Ziouani.

### 2015: Red Hat

Compra do Ansible pela Red Hat por aproxidamente 150 milhões de dólares americanos. Com a promessa de manter a natureza opensource, expandir o desenvolvimento e preservar a comunidade existente.

