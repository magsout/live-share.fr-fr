---
title: Vue d’ensemble - Visual Studio Live Share | Microsoft Docs
description: Vue d’ensemble de Visual Studio Live Share et de ses fonctionnalités.
ms.custom: ''
ms.date: 05/01/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: overview
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6097d94b83f3c2370c87f1d27ba9fd51f24c9896
ms.sourcegitcommit: cab8df5c29f9d91e702ef514def53944ee7701ba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "64987170"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Qu’est-ce que Visual Studio Live Share ?

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Cette solution vous permet de partager instantanément et en toute sécurité votre projet en cours, puis de partager au besoin des sessions de débogage, des instances de terminal, des applications web localhost, des appels vocaux, etc.

En outre, contrairement à la programmation en binôme traditionnelle, Visual Studio Live Share permet aux développeurs de collaborer tout en conservant leurs préférences personnelles en matière d’éditeur (par exemple, thème, clavier), ainsi qu’en disposant de leur propre curseur. Vous pouvez ainsi alterner de façon fluide entre vous suivre les uns les autres et parcourir vos propres idées et tâches. Concrètement, cette possibilité de travailler de façon conjointe _et_ indépendante permet de faciliter les collaborations dans de nombreux cas d’usage courants.

Prêt pour le départ ? Dans cet article, nous allons vous présenter quelques concepts et vous expliquer comment installer les extensions nécessaires. Si vous recherchez une version abrégée, consultez les démarrages rapides [partager](quickstart/share.md) et [rejoindre](quickstart/join.md).

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

## <a name="install-visual-studio-live-share"></a>Installation de Visual Studio Live Share

Avant de commencer, vous devez vous assurer que la version installée de Visual Studio ou Visual Studio Code est conforme aux exigences principales de Live Share.

- **Visual Studio Code 1.22.0 ou une version ultérieure** - Windows 7, 8.1 ou 10, macOS *(Sierra 10.12 et versions ultérieures uniquement)*, Linux 64 bits *(Ubuntu Desktop 64 bits 16.04+, Fedora 27+ recommandé - [afficher les détails](use/vscode.md#installation))*.
- **Visual Studio 2019** (toute édition) - Windows 7, 8.1 ou 10.
- **Visual Studio 2017 15.6 ou une version ultérieure** (toute édition) - Windows 7, 8.1 ou 10.

Ensuite, le téléchargement et l’installation de l’extension Visual Studio Live Share sont un jeu d’enfant :

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1.Installez <a href="https://code.visualstudio.com/">Visual Studio Code</a> pour Windows (7, 8.1 ou 10), macOS <b>(Sierra+)</b>, Linux 64 bits <b>(<a href="use/vscode.md#installation">détails</a>)</b><br />
        2. Téléchargez et installez l’extension Visual Studio Live Share depuis le Marketplace. <br />
        3. Rechargez et attendez que les dépendances soient téléchargées et installées (voir la barre d’état).<br />
        4. <strong>Linux</strong> : Si vous êtes invité à <a href="reference/linux.md#install-linux-prerequisites">installer les bibliothèques</a>, cliquez sur Installer, saisissez le mot de passe et redémarrez VS Code lorsque vous avez terminé.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.Installez <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Installez une <a href="reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++, Python et/ou Node.js)<br />
        3. Visual Studio Live Share est installé par défaut avec ces charges de travail. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 ou une version ultérieure</strong><br />
        1. Installez la dernière version de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a>. (15.6+) sous Windows (7, 8.1 ou 10).<br/>
        2. Installez une <a href="reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)<br />
        3. Téléchargez et installez l’extension Visual Studio Live Share depuis le Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](troubleshooting.md).

C’est aussi simple que cela ! Vous devez maintenant voir une barre d’état en bas à gauche dans VS Code et un bouton de partage en haut à droite dans Visual Studio. Consultez le reste de la documentation pour savoir que faire par la suite !

## <a name="concepts-and-features"></a>Concepts et fonctionnalités

Comme avec n’importe quel produit, Visual Studio Live Share fournit un ensemble de puissantes fonctionnalités développées à partir de quelques concepts principaux. Cette section vous présente quelques concepts et un bref aperçu des fonctionnalités.

### <a name="collaboration-sessions"></a>Sessions de collaboration

Toutes les activités de collaboration dans Visual Studio Live Share impliquent un **hôte de session de collaboration** unique et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

Les hôtes de sessions de collaboration peuvent utiliser l’ensemble de leurs outils et services, mais les invités n’ont accès qu’aux éléments spécifiques que l’hôte a partagés avec eux. Cela inclut le code, les serveurs en cours d’exécution, les sessions de débogage, les terminaux, etc. Actuellement, tout le contenu partagé est conservé sur la machine de l’hôte et n’est pas synchronisé avec le cloud ou sur la machine de l’invité, ce qui permet un _accès instantané_ et une _sécurité renforcée_. L’avantage est que la solution complète est disponible dès qu’un invité s’inscrit et le contenu n’est plus disponible dès qu’un hôte termine une session de collaboration. En outre, les fichiers temporaires créés par l’IDE/éditeur pour améliorer les performances de l’invité sont automatiquement nettoyés lorsque la session se termine.

#### <a name="sharing"></a>Contrat de partage

Lorsque vous effectuez un « partage » en tant qu’hôte, vous démarrez une session de collaboration qui partage le contenu d’un projet, d’une solution ou d’un dossier. Les invités ont accès à ce contenu à l’aide du lien d’invitation que vous leur envoyez. Le raccourci « partage » permet de « partager un projet ». Il permet également de partager d’autres fonctionnalités comme le débogage.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-project) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-project)

#### <a name="joining"></a>Jointure

Cliquez sur un lien d’invitation envoyé par un hôte vous permet de « rejoindre » une session de collaboration en tant qu’invité et d’accéder aux contenus ou fonctionnalités que l’hôte a choisi de partager avec vous. Le lien Web permet d’accéder rapidement à une session de collaboration si l’extension est déjà installée, et de configurer rapidement les informations si tel n’est pas le cas.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#join-a-collaboration-session) [![VS](media/vs-icon-15x15.png)](use/vs.md#join-a-collaboration-session)

### <a name="features"></a>Fonctionnalités

#### <a name="co-editing"></a>Coédition

Lorsque vous ouvrez le même fichier qu’un autre collaborateur, vous pouvez instantanément « éditer de façon collaborative » ou « coéditer » le contenu du fichier. Vous pouvez afficher les modifications, les curseurs et les sélections de chaque collaborateur, et bien plus encore. Encore mieux, vous n’êtes pas obligé de systématiquement éditer le même fichier. Vous pouvez donc choisir le bon moment pour collaborer ou agir de manière indépendante, comme il vous convient le mieux.

> [!NOTE]
> La coédition comporte quelques limites. Voir la section [plateforme prise en charge](reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-editing) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-editing)

#### <a name="following-and-focusing"></a>Suivi et focus

Il est parfois nécessaire d’expliquer un problème ou une conception qui s’étend sur plusieurs fichiers ou emplacements dans le code. Dans ce cas, il peut être utile de suivre temporairement un collègue tout au long du projet lorsqu’il est coédité. C’est pourquoi vous « suivez » automatiquement l’emplacement d’édition de l’hôte lorsque vous rejoignez une session collaborative en tant qu’invité. Les hôtes et les invités peuvent commencer ou arrêter de se suivre d’un simple clic de souris. De plus, il peut arriver que vous souhaitiez inviter tous les participants à vous suivre. Live Share vous permet de demander à tout le monde de faire un « focus » sur vous avec une notification leur permettant de vous suivre facilement.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#following) [![VS](media/vs-icon-15x15.png)](use/vs.md#following)

#### <a name="co-debugging"></a>Codébogage

Lorsque vous déboguez des problèmes de codage ou des bogues difficiles, il peut être très utile de disposer du regard de quelqu’un d’autre. En tant qu’hôte, Live Share active automatiquement le « débogage collaboratif » ou le « codébogage » en partageant la session de débogage avec tous les invités. Vous bénéficiez chacun de fonctions de coédition et de la possibilité d’effectuer des recherches de manière indépendante lors de votre parcours commun.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#co-debugging) [![VS](media/vs-icon-15x15.png)](use/vs.md#co-debugging)

#### <a name="share-server--share-port"></a>Partager le serveur/Partager le port

Lors du codébogage, il peut être très utile de pouvoir accéder aux différentes parties de l’application prise en charge par l’hôte pendant la session de débogage. Il se peut que vous souhaitiez accéder à l’application dans un navigateur, à une base de données locale ou à un terminal REST à partir de vos outils. Live Share vous permet de « partager un serveur » qui mappe un port local sur la machine de l’hôte vers exactement le même port sur chaque machine de l’invité. En tant qu’invité, vous pouvez alors interagir avec l’application exactement comme si elle s’exécutait localement sur votre machine (par exemple, l’hôte et l’invité peuvent tous les deux accéder à une application Web fonctionnant sur http://localhost:3000)).

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-server) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-server)

#### <a name="share-terminals"></a>Partager les terminaux

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Live Share vous permet de « partager un terminal » avec vos invités en tant qu’hôte. Le terminal partagé peut fonctionner en lecture seule ou en collaboration totale, de sorte que vous et vos invités puissiez exécuter des commandes et afficher les résultats. En tant qu’hôte, vous gardez toujours le contrôle et pouvez décider si d’autres collaborateurs peuvent exécuter les commandes eux-mêmes ou simplement visualiser la sortie des commandes. En fait, vous pouvez exécuter dans un terminal non partagé tout ce que vous souhaitez garder confidentiel.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](use/vscode.md#share-a-terminal) [![VS](media/vs-icon-15x15.png)](use/vs.md#share-a-terminal)

#### <a name="access-controls"></a>Contrôles d’accès

Visual Studio Live Share permet aux participants de collaborer de diverses manières très intéressantes. Cependant, avec le nombre d’options et la flexibilité dont disposent les invités pour interagir avec les hôtes, il se peut que vous souhaitiez approuver explicitement les invités qui vous rejoignent ou bloquer l’accès à certains fichiers ou répertoires. Live Share dispose d’un certain nombre de paramètres pouvant vous être utiles, notamment la lecture seule et l’acceptation des invités.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](reference/security.md) [![VS](media/vs-icon-15x15.png)](reference/security.md)

#### <a name="flexible-connection-modes"></a>Modes de connexion flexibles

Pour garantir des performances optimales, Visual Studio Live Share prend en charge deux « modes de connexion » principaux : « direct » et « relais ». En mode direct, les invités se connectent directement à l’hôte sans passer par le Web. En mode relais, les invités qui se trouvent sur un réseau complètement différent peuvent se connecter à l’hôte via un relais Internet. Dans tous les cas, les connexions sont chiffrées en SSH ou SSL pour s’assurer que seuls les collaborateurs ont accès à ce qui se passe sur le réseau. Par défaut, Live Share est en mode « auto ». Il tente d’abord une connexion directe, puis bascule en mode relais. Si vous préférez, vous pouvez verrouiller sur un seul mode.

**En savoir plus :** [![VS Code](media/vscode-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode) [![VS](media/vs-icon-15x15.png)](reference/connectivity.md#changing-the-connection-mode)

## <a name="see-also"></a>Voir aussi

Démarrages rapides

- [Partager votre premier projet](quickstart/share.md)
- [Rejoindre votre première session](quickstart/join.md)

Articles Comment faire

- [Collaborer à l’aide de Visual Studio Code](use/vscode.md)
- [Collaborer à l’aide de Visual Studio](use/vs.md)

Référence

- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](reference/security.md)
- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Extensions prises en charge](reference/extensions.md)
- [Notes de publication](https://aka.ms/vsls-releases)

Vous rencontrez des problèmes ? Voir la section [dépannage](troubleshooting.md) ou [fournir des commentaires](support.md).
