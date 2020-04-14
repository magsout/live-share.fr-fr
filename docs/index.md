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
ms.openlocfilehash: e74268abd215fd17ec67028d94de69f18685f808
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2020
ms.locfileid: "79508557"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="what-is-visual-studio-live-share"></a>Qu’est-ce que Visual Studio Live Share ?

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Vous pouvez partager instantanément et de manière sécurisée votre projet actuel, démarrer une session de débogage conjointe, partager des instances de terminal, transférer des applications web localhost, passer des appels vocaux, etc.

 Contrairement à la programmation en binôme traditionnelle, Visual Studio Live Share permet aux développeurs de collaborer tout en conservant leurs préférences personnelles en matière d’éditeur (par exemple, thème, combinaisons de touches), ainsi qu’en disposant de leur propre curseur. Vous pouvez ainsi alterner de façon fluide entre vous suivre les uns les autres et parcourir vos propres idées et tâches. Cette capacité à travailler ensemble et de manière indépendante offre une expérience de collaboration qui s’apparente beaucoup à une collaboration _en personne_.

Prêt pour le départ ? Dans cet article, nous allons vous présenter quelques concepts et vous expliquer comment installer les extensions nécessaires. Si vous recherchez une version abrégée, consultez les démarrages rapides [partager](quickstart/share.md) et [rejoindre](quickstart/join.md).

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre une session Live Share à partir du navigateur* ? Cela signifie que vous n’avez plus besoin d’installer un client de bureau pour collaborer. Cliquez simplement sur le lien partagé avec vous pour bénéficier d’une expérience complète de l’éditeur VS Code dans le navigateur. Apprenez-en davantage [ici](quickstart/browser-join.md).

## <a name="install-visual-studio-live-share"></a>Installation de Visual Studio Live Share

Avant de commencer, vous devez vous assurer que la version installée de Visual Studio ou Visual Studio Code est conforme aux exigences principales de Live Share.

- **Visual Studio Code 1.22.0 ou une version ultérieure** - Windows 7, 8.1 ou 10, macOS *(High Sierra 10.13+ uniquement)* , Linux 64 bits *(Ubuntu Desktop 64 bits 16.04+, Fedora 27+ recommandé - [afficher les détails](use/vscode.md#installation))* .
- **Visual Studio 2019** (toute édition) - Windows 7, 8.1 ou 10.
- **Visual Studio 2017 15.6 ou une version ultérieure** (toute édition) - Windows 7, 8.1 ou 10.

Ensuite, le téléchargement et l’installation de l’extension Visual Studio Live Share sont un jeu d’enfant :

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1. Installez <a href="https://code.visualstudio.com/">Visual Studio Code</a> pour Windows (7, 8.1 ou 10), macOS <b>(High Sierra 10.13+)</b>, Linux 64 bits <b>(<a href="use/vscode.md#installation">détails</a>)</b><br />
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


## <a name="see-also"></a>Voir aussi

Démarrages rapides

- [Partager votre premier projet](quickstart/share.md)
- [Rejoindre votre première session](quickstart/join.md)

Articles Comment faire

- [Collaborer à l’aide de Visual Studio Code](use/vscode.md)
- [Collaborer à l’aide de Visual Studio](use/vs.md)

reference

- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](reference/security.md)
- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Extensions prises en charge](reference/extensions.md)
- [Notes de publication](https://aka.ms/vsls-releases)

Vous rencontrez des problèmes ? Voir la section [dépannage](troubleshooting.md) ou [fournir des commentaires](support.md).
