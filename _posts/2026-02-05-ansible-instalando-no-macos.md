---
title: Ansible - Instalando no macOS
author: victoabreu
date: 2026-02-05 18:37:02 -0300
categories: [Ansible]
tags: [ansible, mac, bsd, unix, homebrew, python, pip]
image:
  path: /assets/img/posts/ansible-instalando-no-macos/ansible_plus_finder.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

O [macOS](https://en.wikipedia.org/wiki/MacOS) é o atual sistema operacional dos computadores da [Apple](https://en.wikipedia.org/wiki/Apple_Inc.). Tendo como antecessor o [NeXTSTEP](https://en.wikipedia.org/wiki/NeXTSTEP), um sistema unix-like com partes derivadas do [FreeBSD](https://www.freebsd.org/) e outros BSDs, o mesmo foi comprado pela Apple em **1997**, renomeado para OPENSTEP, e finalmente lançado em **2001** como Mac OS X.

Sendo assim, e dada a sua natureza, o macOS é tão personalizável quanto qualquer outro "Linux". Por esse e [outros](https://blog.rolpdog.com/2020/03/why-no-ansible-controller-for-windows.html) motivos, o [ansible](https://docs.ansible.com/projects/ansible/latest/getting_started/index.html) também é suportado na plataforma da maçã. Para instalá-lo, antes precisamos de outra ferramenta chamada [Homebrew](https://brew.sh/). Este nada mais é do que um gerenciador de pacotes para macOS (e Linux). Ele funciona como um [apt](https://wiki.debian.org/pt_BR/Apt), [dnf](https://docs.fedoraproject.org/pt_BR/quick-docs/dnf/), [pacman](https://wiki.archlinux.org/title/Pacman), etc.

Para instalar o Homebrew rode o seguinte comando:

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

Depois instale o ansible:

```bash
brew install ansible
```

Finalmente valide a instalação com:

```bash
ansible --version
```

## Modo pip (python)

- instalar/atualizar o pip:

```bash
sudo easy_install pip
# ou
sudo python3 -m ensurepip --upgrade
```

- instalar o ansible:

```bash
pip3 install ansible
```