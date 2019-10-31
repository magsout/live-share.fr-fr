---
title: Vue d’ensemble - Visual Studio Live Share | Microsoft Docs
description: Vue d’ensemble de Visual Studio Live Share et de ses fonctionnalités.
ms.custom: ''
ms.date: 10/30/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: fubaduba
ms.author: fubaduba
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 8091a7ba5cf1f57f192ecea18da4473c8fdd99f7
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179868"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->
# <a name="live-share-features-and-concepts"></a>Fonctionnalités et concepts de Live Share 

Live Share est créée à l’aide d’une architecture révolutionnaire et de concepts qui se manifestent comme des fonctionnalités puissantes pour nos utilisateurs. Vous trouverez ci-dessous toutes les fonctionnalités distinctives de Live Share et ce qui en fait un leader dans l’espace de collaboration. 

### <a name="collaboration-sessions"></a>Sessions de collaboration

Toutes les activités de collaboration dans Visual Studio Live Share impliquent un **hôte de session de collaboration** unique et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

Les hôtes de sessions de collaboration peuvent utiliser l’ensemble de leurs outils et services, mais les invités n’ont accès qu’aux éléments spécifiques que l’hôte a partagés avec eux. Cela inclut le code, les serveurs en cours d’exécution, les sessions de débogage, les terminaux, etc. Actuellement, tout le contenu partagé est conservé sur la machine de l’hôte et n’est pas synchronisé avec le cloud ou sur la machine de l’invité, ce qui permet un _accès instantané_ et une _sécurité renforcée_. L’avantage est que la solution complète est disponible dès qu’un invité s’inscrit et le contenu n’est plus disponible dès qu’un hôte termine une session de collaboration. En outre, les fichiers temporaires créés par l’IDE/éditeur pour améliorer les performances de l’invité sont automatiquement nettoyés lorsque la session se termine.

#### <a name="sharing"></a>Contrat de partage

Lorsque vous effectuez un « partage » en tant qu’hôte, vous démarrez une session de collaboration qui partage le contenu d’un projet, d’une solution ou d’un dossier. Les invités ont accès à ce contenu à l’aide du lien d’invitation que vous leur envoyez. Le raccourci « partage » permet de « partager un projet ». Il permet également de partager d’autres fonctionnalités comme le débogage.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

#### <a name="joining"></a>Jointure

Cliquez sur un lien d’invitation envoyé par un hôte vous permet de « rejoindre » une session de collaboration en tant qu’invité et d’accéder aux contenus ou fonctionnalités que l’hôte a choisi de partager avec vous. Le lien Web permet d’accéder rapidement à une session de collaboration si l’extension est déjà installée, et de configurer rapidement les informations si tel n’est pas le cas.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#join-a-collaboration-session) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#join-a-collaboration-session)

### <a name="features"></a>Fonctionnalités

#### <a name="co-editing"></a>Coédition

Lorsque vous ouvrez le même fichier qu’un autre collaborateur, vous pouvez instantanément « éditer de façon collaborative » ou « coéditer » le contenu du fichier. Vous pouvez afficher les modifications, les curseurs et les sélections de chaque collaborateur, et bien plus encore. Encore mieux, vous n’êtes pas obligé de systématiquement éditer le même fichier. Vous pouvez donc choisir le bon moment pour collaborer ou agir de manière indépendante, comme il vous convient le mieux.

> [!NOTE]
> La coédition comporte quelques limites. Voir la section [plateforme prise en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-editing) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Suivi et focus

Il est parfois nécessaire d’expliquer un problème ou une conception qui s’étend sur plusieurs fichiers ou emplacements dans le code. Dans ce cas, il peut être utile de suivre temporairement un collègue tout au long du projet lorsqu’il est coédité. C’est pourquoi vous « suivez » automatiquement l’emplacement d’édition de l’hôte lorsque vous rejoignez une session collaborative en tant qu’invité. Les hôtes et les invités peuvent commencer ou arrêter de se suivre d’un simple clic de souris. De plus, il peut arriver que vous souhaitiez inviter tous les participants à vous suivre. Live Share vous permet de demander à tout le monde de faire un « focus » sur vous avec une notification leur permettant de vous suivre facilement.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#following) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#following)

#### <a name="co-debugging"></a>Codébogage

Lorsque vous déboguez des problèmes de codage ou des bogues difficiles, il peut être très utile de disposer du regard de quelqu’un d’autre. En tant qu’hôte, Live Share active automatiquement le « débogage collaboratif » ou le « codébogage » en partageant la session de débogage avec tous les invités. Vous bénéficiez chacun de fonctions de coédition et de la possibilité d’effectuer des recherches de manière indépendante lors de votre parcours commun.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Partager le serveur/Partager le port

Lors du codébogage, il peut être très utile de pouvoir accéder aux différentes parties de l’application prise en charge par l’hôte pendant la session de débogage. Il se peut que vous souhaitiez accéder à l’application dans un navigateur, à une base de données locale ou à un terminal REST à partir de vos outils. Live Share vous permet de « partager un serveur » qui mappe un port local sur la machine de l’hôte vers exactement le même port sur chaque machine de l’invité. En tant qu’invité, vous pouvez alors interagir avec l’application exactement comme si elle s’exécutait localement sur votre machine (par exemple, l’hôte et l’invité peuvent tous les deux accéder à une application Web fonctionnant sur http://localhost:3000) ).

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

#### <a name="share-terminals"></a>Partager les terminaux

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Live Share vous permet de « partager un terminal » avec vos invités en tant qu’hôte. Le terminal partagé peut fonctionner en lecture seule ou en collaboration totale, de sorte que vous et vos invités puissiez exécuter des commandes et afficher les résultats. En tant qu’hôte, vous gardez toujours le contrôle et pouvez décider si d’autres collaborateurs peuvent exécuter les commandes eux-mêmes ou simplement visualiser la sortie des commandes. En fait, vous pouvez exécuter dans un terminal non partagé tout ce que vous souhaitez garder confidentiel.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Contrôles d’accès

Visual Studio Live Share permet aux participants de collaborer de diverses manières très intéressantes. Cependant, avec le nombre d’options et la flexibilité dont disposent les invités pour interagir avec les hôtes, il se peut que vous souhaitiez approuver explicitement les invités qui vous rejoignent ou bloquer l’accès à certains fichiers ou répertoires. Live Share dispose d’un certain nombre de paramètres pouvant vous être utiles, notamment la lecture seule et l’acceptation des invités.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../reference/security.md) [![et](../media/vs-icon-15x15.png)](../reference/security.md)

#### <a name="flexible-connection-modes"></a>Modes de connexion flexibles

Pour garantir des performances optimales, Visual Studio Live Share prend en charge deux « modes de connexion » principaux : « direct » et « relais ». En mode direct, les invités se connectent directement à l’hôte sans passer par le Web. En mode relais, les invités qui se trouvent sur un réseau complètement différent peuvent se connecter à l’hôte via un relais Internet. Dans tous les cas, les connexions sont chiffrées en SSH ou SSL pour s’assurer que seuls les collaborateurs ont accès à ce qui se passe sur le réseau. Par défaut, Live Share est en mode « auto ». Il tente d’abord une connexion directe, puis bascule en mode relais. Si vous préférez, vous pouvez verrouiller sur un seul mode.

**En savoir plus :** [![vs code](../media/vscode-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode) [![et](../media/vs-icon-15x15.png)](../reference/connectivity.md#changing-the-connection-mode)
