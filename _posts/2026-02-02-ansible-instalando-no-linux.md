---
title: Ansible - Instalando no Linux
author: victoabreu
date: 2026-02-02 13:19:16 -0300
categories: [Ansible]
tags: [ansible, linux, ubuntu, debian, fedora, opensuse, archlinux, python, pip]
image:
  path: /assets/img/posts/ansible-instalando-no-linux/ansible_+_linux.png
  alt: Imagem meramente ilustrativa devido a direitos autorais
---

O [ansible](https://docs.ansible.com/) tornou-se tão popular entre a comunidade que a maioria das distros já disponibilizam por padrão o pacote nos repositórios oficiais. Além disso, também é possível instalá-lo pelo [pip](https://pypi.org/project/pip/). Trata-se de um gerenciador de pacotes feito para projetos em python e suas dependências.

Ressaltando que para ambientes críticos, onde cada KB conta e faz falta, o melhor é optar pela versão chamada `ansible-core`. A mesma apresenta uma linguagem minimalista e um pacote runtime contendo módulos e plugins embutidos.

Caso contrário, a versão `ansible` é a mais completa pois adiciona extras (playbooks, roles, etc) para automação de vários dispositivos.

Abra um terminal. Execute os comandos de acordo com a sua distro.

## Ubuntu

(Versões mais antigas)

```bash
sudo apt install ansible
```

(Última versão)

```bash
sudo apt update
sudo apt install software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install ansible
```

## Debian

```bash
$ UBUNTU_CODENAME=noble
$ wget -O- "https://keyserver.ubuntu.com/pks/lookup?fingerprint=on&op=get&search=0x6125E2A8C77F2818FB7BD15B93C4A3FD7BB9C367" | sudo gpg --dearmor -o /usr/share/keyrings/ansible-archive-keyring.gpg
$ echo "deb [signed-by=/usr/share/keyrings/ansible-archive-keyring.gpg] http://ppa.launchpad.net/ansible/ansible/ubuntu $UBUNTU_CODENAME main" | sudo tee /etc/apt/sources.list.d/ansible.list
$ sudo apt update && sudo apt install ansible
```

## Fedora

```bash
sudo dnf install epel-release
sudo dnf install ansible
```

## OpenSUSE

```bash
sudo zypper install ansible
```

## Arch Linux

```bash
sudo pacman -S ansible
```

## Genérica (Outras)

(Instalando)

```bash
python3 -m pip install --user ansible
```

(Atualizando)

```bash
python3 -m pip install --upgrade --user ansible
```

## Confirmando (Verificando)

```bash
ansible --version
```