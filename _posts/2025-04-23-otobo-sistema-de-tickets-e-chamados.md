---
title: OTOBO - Sistema de Tickets e Chamados
author: victoabreu
date: 2025-04-23 16:33:00 -0300
categories: [OTOBO]
tags: [otobo, ticket, helpdesk, itsm, itil]
---

Em janeiro de **2021**, a versão gratuita do [OTRS](https://otrs.com/pt/home/) foi oficialmente descontinuada pelos criadores. Na prática, isso representa uma enorme brecha de segurança para ambientes de produção mundo afora. Com tal anúncio diversos forks ganharam força e destaque na comunidade de administradores. Dentre eles: [Znuny](https://www.znuny.org/en), [OFORK](https://o-fork.de/) e [OTOBO](https://otobo.io/en/).

A interface do Znuny é bastante parecida com o OTRS 6, sendo uma ótima escolha para aqueles que não querem assustar seus usuários e clientes com algo novo. Já o OFORK implementa alguns recursos novos, por exemplo na gestão de processos.

Escolhi o OTOBO como solução por se tratar de um visual totalmente repaginado e moderno, mais próximo dos aplicativos atuais. Além de claro uma boa documentação e cem por cento código aberto.

## OTRS, uma breve história

Tudo começa em **2001** como um projeto pessoal de [Martin Edenhofer](https://github.com/martini). O objetivo era criar um software de tickets para helpdesk. O mesmo publica e compartilha sob a condição de código aberto. Escrito na maior parte em [Perl](https://www.perl.org/), sua interface web conta com o [JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript) para tornar as coisas mais amigáveis possíveis.

Ganhando popularidade entre sysadmins, em **2003** é fundada a empresa OTRS GmbH (equivalente a Sociedade de Responsabilidade Limitada). Renomeada posteriormente para OTRS AG em **2007**.

Em **2015** uma nova versão chamada OTRS Business Solution é lançada. Essa seria a versão paga que contaria com suporte e recursos extras. A mesma foi rebatizada para simplesmente OTRS em **2018**.

Em dezembro de **2020**, o Grupo OTRS anuncia o EOL (fim da vida) da versão opensource: ((OTRS)) Community Edition.

Recentemente **(2024)** a [EasyVista](https://www.easyvista.com/pt-pt/) adquiriu a participação majoritária da OTRS AG.

## O criador do OTOBO

Coincidência ou não, a mente por trás do OTOBO trabalhou no OTRS liderando o suporte e a equipe interna de TI. O ano era **2004** e seu nome é [Stefan Rother](https://github.com/StefanRother-OTOBO). Acumulando expertise em sistemas de tickets e adepto da filosofia de código aberto, em **2011** Stefan funda sua própria empresa de nome Rother OSS. Especializada na implementação, personalização e operação do OTRS (até então gratuito).

Tudo muda em **2019** quando eles decidem desenvolver o OTOBO propriamente dito baseado na versão ((OTRS)) Community Edition 6. O mesmo é lançado em **2020** com um desenho de interface totalmente novo e moderno, seguindo as melhores práticas de [UX/UI](https://en.wikipedia.org/wiki/User_experience_design).