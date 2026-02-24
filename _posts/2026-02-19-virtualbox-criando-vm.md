---
title: VirtualBox - Criando VMs
author: victoabreu
date: 2026-02-19 18:22:06 -0300
categories: [VirtualBox]
tags: [virtualbox, ubuntu, hypervisor, vm, desktop, arm64, x86_64]
image:
  path: /assets/img/posts/virtualbox-criando-vm/virtualbox_plus_ubuntu.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

Para instalar o VirtualBox, clique no link abaixo e faça o download de acordo com o sistema operacional:

<https://www.virtualbox.org/wiki/Downloads>

Feito isso, execute o arquivo para iniciar o processo. Para a maioria das situações, o "bom" e velho padrão NEXT, NEXT, NEXT satisfaz muito bem os pré-requisitos. No caso do macOS é ainda mais fácil, dois cliques no ícone `.pkg` para adicionar na pasta ***Applications*** (confirme as instruções).

![Instalar no macOS](/assets/img/posts/virtualbox-criando-vm/virtualbox_install.png)
_Próximo, próximo, próximo `:)`_

Agora abra o programa e selecione o modo ***Expert*** para visualizar todas as opções disponíveis.

![Home do VirtualBox](/assets/img/posts/virtualbox-criando-vm/virtualbox_home.png)
_Página inicial_

Antes de prosseguir e criar qualquer VM, precisamos baixar a ISO oficial do sistema operacional em questão. Escolhi o [Ubuntu](https://ubuntu.com/) como teste apenas para fins didáticos. Acesse o site e escolha a versão desktop com interface GNOME.

<https://ubuntu.com/download/desktop>

Com tudo preparado, podemos começar. Clique no botão ***NOVO***. Escolha um nome para a máquina. Um padrão que vou adotar é: `Sistema Versão Propósito (Arquitetura)`. Caso queira mudar a localidade, crie uma nova pasta e aponte para a mesma. Selecione onde está a ISO baixada. Desmarque a opção `Unattended Installation`. Sem ela, o Ubuntu solicita dados (usuário, senha, hostname, etc) a serem definidos no primeiro setup. Com ela, a instalação se torna um pouco mais automatizada, "queimando" essas etapas.

![Nova Máquina](/assets/img/posts/virtualbox-criando-vm/virtualbox_new_machine.png)

Bloco um concluído, passando para o próximo. Defina aqui a quantidade de memória RAM e núcleos de CPU para a máquina virtual. O padrão está 2 GB, mas a Canonical recomenda 4, 6 ou 8 GB para desempenho satisfatório. Mas claro, vai muito da capacidade do seu hardware atual. Pra mim, 2GB é o mínimo aceitável. Quanto a CPU, aumentei para 2.

![RAM e CPU](/assets/img/posts/virtualbox-criando-vm/virtualbox_new_hardware.png)

Último bloco, disco virtual. 25 GB para uso demonstrativo está de bom tamanho. Mantenha o formato VDI (VirtualBox Disk Image). A ideia é usarmos apenas no VirtualBox mesmo.

![Disco](/assets/img/posts/virtualbox-criando-vm/virtualbox_new_disk.png)

Aperte ***FINALIZAR*** e veja os detalhes da nova VM.

![VM info](/assets/img/posts/virtualbox-criando-vm/virtualbox_vm_info.png)

Quase lá, clicamos em ***INICIAR***.