---
title: Rejoindre le démarrage rapide - Visual Studio Live Share | Microsoft Docs
description: Une procédure pas-à-pas abrégée pour rejoindre votre première session de collaboration Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1f62cf12797279cc7bcb1a7ee1273667618ab46
ms.sourcegitcommit: cab8df5c29f9d91e702ef514def53944ee7701ba
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/01/2019
ms.locfileid: "64987182"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Démarrage rapide : Rejoindre votre première session de collaboration

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Cette solution vous permet de rejoindre instantanément et en toute sécurité le projet en cours d’un collègue, puis, au besoin, d’entrer dans des sessions de débogage, afficher et modifier des instances de terminal, afficher des applications web localhost, rejoindre des appels vocaux, etc.

Prêt pour le départ ? La collaboration d’équipe doit être si rapide et naturelle, qu’il devient plus difficile de ne pas le faire ! C’est pour cette raison que Visual Studio Live Share simplifie la prise en main, afin que vous puissiez commencer en toute transparence à partager vos travaux et idées.

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

Suivez ces étapes pour rejoindre une session de collaboration.

## <a name="1-install-the-extension"></a>1. Installer l’extension

L’extension est facile à installer. Procédez comme suit :

<table style="width: 100%; border:none;">
<tr>
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-code.svg" width="128px" alt="Visual Studio Code logo"/></td>
    <td style="border:none;">
        <strong>Visual Studio Code (1.22.0+)</strong><br />
        1.Installez <a href="https://code.visualstudio.com/">Visual Studio Code</a> pour Windows (7, 8.1 ou 10), macOS <b>(Sierra+)</b>, Linux 64 bits <b>(<a href="../use/vscode.md#installation">détails</a>)</b><br />
        2. Téléchargez et installez l’extension Visual Studio Live Share depuis le Marketplace. <br />
        3. Rechargez et attendez que les dépendances soient téléchargées et installées (voir la barre d’état).<br />
        4. <strong>Linux</strong> : Si vous êtes invité à <a href="../reference/linux.md#install-linux-prerequisites">installer les bibliothèques</a>, cliquez sur Installer, saisissez le mot de passe et redémarrez VS Code lorsque vous avez terminé.<br />
        <a href="https://aka.ms/vsls-dl/vscode" alt="Download button"><img src="../media/download.png"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1.Installez <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
        2. Installez une <a href="../reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++, Python et/ou Node.js)<br />
        3. Visual Studio Live Share est installé par défaut avec ces charges de travail. <br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2017.svg" width="128px" alt="Visual Studio 2017 logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2017 15.6 ou une version ultérieure</strong><br />
        1. Installez la dernière version de <a href="https://visualstudio.microsoft.com/vs/older-downloads/">Visual Studio 2017</a>. (15.6+) sous Windows (7, 8.1 ou 10).<br/>
        2. Installez une <a href="../reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)<br />
        3. Téléchargez et installez l’extension Visual Studio Live Share depuis le Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button" ></a><br />
    </td>
</tr>
</table>

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [Facultatif] Rejoindre en tant qu’invité en lecture seule dans VS Code

Dans VS Code, une fois l’extension Live Share installée, après avoir redémarré et attendu la fin de l’installation des dépendances, vous devrez vous connecter et rejoindre une session de collaboration en tant qu’invité en lecture seule.

> [!NOTE]
> Si vous souhaitez apporter des modifications au code que vous rejoignez, vous devrez vous connecter.

Ouvrez (ou rouvrez) le lien d’invitation dans un navigateur, puis vous recevrez une notification vous indiquant que le navigateur souhaite lancer VS Code. Laissez-le lancer VS Code, et il démarrera la connexion à la session de collaboration.

Lors du lancement de VS Code, vous recevrez une notification toast vous demandant de vous connecter. Cliquez sur « Continuer en tant qu’invité en lecture seule » pour rejoindre la session.

![Notification toast « Rejoindre une session en tant qu’invité en lecture seule »](../media/vscode-read-only-guest.png)

Vous devrez entrer un nom d’affichage pour aider les participants à vous identifier durant la session.

![Nom d’invité en lecture seule](../media/vscode-read-only-guest-name.png)

Vous rejoindrez ensuite la session en tant qu’invité en lecture seule. Vous pourrez afficher et naviguer dans le code, codéboger, et afficher les serveurs et terminaux partagés (en lecture seule).

> [!NOTE]
> Si vous souhaitez accéder ultérieurement en lecture/écriture au code, vous pouvez vous connecter. Cliquez sur votre nom d’affichage sur la barre d’état et sélectionnez l’option « Se connecter ».
![Connexion d’invité en lecture seule](../media/vscode-read-only-guest-signin.png) Cette action lance votre navigateur, et vous pouvez choisir un compte Microsoft ou GitHub pour vous connecter.

## <a name="3-sign-in"></a>3. Se connecter

Une fois l’extension Live Share installée, après avoir redémarré et attendu la fin de l’installation des dépendances (VS Code), vous devrez vous connecter pour vous identifier auprès des autres participants. Si vous ignorez cette étape, vous serez invité à vous connecter pendant le processus de jonction, ou pourrez rejoindre la session en tant qu’un invité en lecture seule. Cliquez sur l’élément « Live Share » sur la barre d’état (VS Code) ou sur le bouton « Se connecter » (VS) pour commencer.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

Dans **VS Code**, votre navigateur se lance tandis qu’une notification s’affiche vous demandant de vous connecter. Terminez le processus de connexion dans votre navigateur, puis fermez simplement le navigateur.

![Notification toast demandant de se connecter à l’aide d’un navigateur Web](../media/vscode-sign-in-toast.png)

> **Utilisateurs Linux :** Vous pouvez être invité à entrer un code utilisateur si vous utilisez une version antérieure de Live Share (v0.3.295 ou postérieure). Mettez à jour vers la dernière version de l’extension ou cliquez sur le lien « Vous rencontrez des problèmes ? » une fois connecté pour afficher le code. Cliquez [ici pour plus de détails](../use/vscode.md#sign-in-using-a-user-code).

Dans **Visual Studio**, Live Share utilise automatiquement votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Par conséquent, vous pouvez simplement vous connecter comme vous le feriez normalement. Toutefois, si vous préférez utiliser d’autres informations d’identification que celles de votre compte de personnalisation Visual Studio, accédez à **Outils &gt; Options &gt; Live Share &gt; Compte d’utilisateur** et sélectionnez des informations d’identification différentes.

Consultez la section [Résolution des problèmes](../troubleshooting.md#sign-in) si vous rencontrez toujours des problèmes.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Ouvrir/rouvrir le lien d’invitation dans un navigateur

À présent, ouvrez simplement (ou rouvrez) le lien d’invitation dans un navigateur.

> **Remarque** : Si vous n’avez pas encore installé l’extension Live Share, des liens vers la Place de marché des extensions apparaîtront. Installez l’extension, redémarrez votre outil et réessayez.

Vous devriez être averti que le navigateur souhaite lancer un outil Live Share activé. Si vous le laissez lancer l’outil sélectionné, vous serez connecté à la session de collaboration lors du démarrage.

![Page Rejoindre](../media/join-page.png)

Si l’hôte est hors connexion, vous serez averti à ce moment-là. Vous pourrez ensuite contacter l’hôte et lui demander de partager à nouveau.

> **Conseils de dépannage :** Lorsque vous utilisez VS Code, veillez à avoir **démarrer l’outil au moins une fois** après l’installation de l’extension et à avoir attendu la fin de l’installation des dépendances (voir la barre d’état) avant d’ouvrir/de réouvrir la page d’invitation. Le problème persiste ? Consultez [Rejoindre manuellement](../reference/manual-join.md) pour plus d’informations.

## <a name="5-collaborate"></a>5. Collaborez !

C’est tout ! Dans quelques instants, vous serez connecté à la session de collaboration de votre collègue. Par défaut, l’hôte accepte automatiquement les personnes qui rejoignent la session, mais si l’hôte est configuré pour [demander l’approbation de l’invité](../reference/security.md#requiring-guest-approval), vous verrez une mention sur la barre d’état/dans la boîte de dialogue « Rejoindre » indiquant que Live Share attend que l’hôte approuve votre demande de participation.

> **Conseil en sécurité :** En tant qu’invité rejoignant une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou fonctionnalités. Vous voulez comprendre les implications de sécurité de certains paramètres et fonctionnalités Live Share ? Consultez l’article [Sécurité](../reference/security.md).

Voici quelques éléments à essayer :

1. Se déplacer dans le projet de manière indépendante et apporter des modifications
2. Vérifier que Intellisense fonctionne pour JavaScript, TypeScript, et/ou le code C#
3. Modifier un élément avec l’hôte
4. Suivre l’hôte et se déplacer avec lui tandis qu’il navigue dans les différents fichiers et apporte des modifications
5. Démarrer une session de codébogage avec l’hôte
6. Demander à l’hôte de partager un serveur pour vérifier une application Web en cours d’exécution sur leur machine
7. Demander à l’hôte de partager un terminal et d’exécuter des commandes

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations, voir ces articles complémentaires.

- [Démarrage rapide : Partager votre premier projet](share.md)
- [Guide pratique : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Guide pratique : Collaborer à l’aide de Visual Studio](../use/vs.md)

Référence

- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
