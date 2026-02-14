---
title: VirtualBox - Virtualizando Hardware (Hipervisores)
author: victoabreu
date: 2026-02-10 04:45:01 -0300
categories: [VirtualBox]
tags: [virtualbox, hypervisor, vm, desktop]
image:
  path: /assets/img/posts/virtualbox-virtualizando-hardware-hipervisores/virtualbox_new.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

No início da computação tudo era mono. Monotarefa, monousuário, e por aí vai. Em outras palavras, você teria que esperar a sua vez para fazer algo. Foi somente a partir da década de 60 que tal cenário mudaria. Em **1966**, a [IBM](https://en.wikipedia.org/wiki/IBM) desenvolve o primeiro mainframe de tempo compartilhado da história, o [CP-40](https://www.techtarget.com/searchitoperations/feature/The-history-of-virtualization-and-its-mark-on-data-center-management). Tratava-se de um protótipo nunca comercializado, mas que no ano seguinte serviu de base para o [CP-67](https://inventivehq.com/blog/history-of-virtualization-from-1960s-mainframes-to-modern-cloud-computing). Ambos permitiam mais de um usuário simultâneo. Baixando os custos e democratizando o acesso de recursos computacionais. Depois finalmente veio o primeiro produto oficial de máquina virtual. Em **1972**, a marca lança o [VM/370](https://www.ibm.com/history/system-370), para a família de computadores System/370.

O principal ganho e diferencial foi o suporte a memória virtual, que agora permitia aos programas de serem executados em espaços de endereçamento diferentes, em vez de todos no mesmo espaço como no passado. Além disso, cada usuário poderia ter N máquina(s) virtual(is) rodando em paralelo a outras máquinas de outros usuários. O único limite era a capacidade do próprio hardware. Desde que ele aguentasse, estava tudo bem.

Em **1974**, Gerald Popek e Robert Goldberg publicam um [artigo](https://dl.acm.org/doi/10.1145/361011.361073) definindo e classificando hipervisores em dois tipos: 1 e 2. Simplificando, hipervisor é o software que cria e roda máquinas virtuais (VMs). O tipo 1, chamado de nativo ou bare metal, é executado diretamente sobre o hardware em questão. Ex: VMware ESXi. Já o tipo 2, denominado como hospedado ou hosted, é executado sobre um sistema operacional qualquer. Ex: Oracle VirtualBox.

Hipervisores tipo 1 são mais seguros pois sua localidade está no hardware em si. Portanto, sua superfície de ataque é bem menor que a de um SO tradicional. Em contrapartida, seus pré-requisitos para execução são bem maiores, como visto neste [exemplo](https://techdocs.broadcom.com/us/en/vmware-cis/vsphere/vsphere/8-0/esxi-hardware-requirements.html). Hipervisores tipo 2 estão mais relacionados ao começo da [virtualização](https://shakenfist.com/components/cloudgood/virtualization-history/) x86 e por isso normalmente são utilizados por clientes e usuários finais.

![Tipos de Hipervisores](/assets/img/posts/virtualbox-virtualizando-hardware-hipervisores/hypervisors.png)
_Tipo 1 e Tipo 2_

> **Para este post pretendo abordar o VirtualBox.** *No futuro, outros hipervisores (tanto do tipo 1 quanto do tipo 2) aparecerão aqui no blog.*
{: .prompt-info }

## Innotek Systemberatung GmbH, a origem

O [VirtualBox](https://www.oracle.com/br/virtualization/virtualbox/) foi criado pela Innotek GmbH, uma empresa alemã especializada em consultoria e suporte de sistemas legados, como o [OS/2](https://pt.wikipedia.org/wiki/OS/2) da IBM. Graças a essa vasta experiência, eles foram capazes de moldar uma plataforma de virtualização para arquiteturas x86 com foco em computadores pessoais comuns (Windows, Linux e macOS). Durante um período em que virtualizar era majoritariamente caro e restrito, a Innotek levou essa tecnologia para o desktop, tornando-a acessível a desenvolvedores, estudantes e pequenas organizações.

Em **2007**, a Innotek decide liberar o código do VirtualBox como software opensource sob a licença [GPL](https://pt.wikipedia.org/wiki/GNU_General_Public_License), mantendo apenas alguns componentes avançados sob licença comercial. Essa abordagem acelerou a adoção mundial da ferramenta, estimulou o surgimento de uma comunidade ativa e consolidou o VirtualBox como padrão em ambientes educacionais, laboratórios e times de desenvolvimento. A facilidade de uso, aliada a recursos como snapshots, clonagem e integração com o sistema hospedeiro, ajudou a popularizar conceitos que hoje são centrais na engenharia de software moderna.

O VirtualBox tornou-se a principal porta de entrada para a virtualização para milhões de profissionais, influenciando práticas que mais tarde evoluiriam para DevOps, infraestrutura como código e computação em nuvem. Em **2008**, a empresa foi adquirida pela [Sun Microsystems](https://pt.wikipedia.org/wiki/Sun_Microsystems), e em **2010**, com a aquisição da Sun pela [Oracle](https://www.oracle.com/br/), o legado da Innotek passou a integrar uma estratégia corporativa mais ampla.