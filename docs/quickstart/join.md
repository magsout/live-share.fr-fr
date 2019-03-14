---
title: Joindre le Guide de démarrage rapide - partage en direct de Visual Studio | Microsoft Docs
description: Une procédure pas à pas abrégées sur la jonction de votre première session de collaboration le Partage Live Visual Studio.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: quickstart
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: d4280484aaa3fd4ac204588bf4aefc4e3ac51871
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255608"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-join-your-first-collaboration-session"></a>Démarrage rapide : Joindre votre première session de collaboration

> **Remarque : Visual Studio Live Share est actuellement en préversion. L’expérience utilisateur et les fonctionnalités ne sont pas définitives.**

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Il vous permet d’instantanément et en toute sécurité pour participer à projet en cours d’un collègue et si nécessaire, entrez dans les sessions de débogage, puis afficher et modifier des instances de terminal, voir les applications web de localhost, appels vocaux de jointure et bien plus encore !

Prêt pour le départ ? Collaboration d’équipe doit être rapide et naturelle, qu’il devient plus difficile de ne pas le faire ! Pour cette raison, partage en direct de Visual Studio simplifie prise en main, afin que vous puissiez commencer en toute transparence votre travail et des idées de partage.

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

Suivez ces étapes pour rejoindre une session de collaboration.

## <a name="1-install-the-extension"></a>1. Installer l’extension

Il est facile d’installer l’extension. Procédez simplement comme suit :

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
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide.svg" width="128px" alt="Visual Studio logo" /></td>
    <td style="border:none;">
        <strong>Visual Studio 2017 15.6 ou une version ultérieure</strong><br />
        1. Installez la dernière version de <a href="https://visualstudio.microsoft.com/vs/">Visual Studio 2017</a>. (15.6+) sous Windows (7, 8.1 ou 10).<br/>
        2. Installez une <a href="../reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)<br />
        3. Téléchargez et installez l’extension Visual Studio Live Share depuis le Marketplace. <br />
        <a href="https://aka.ms/vsls-dl/vs"><img style="padding: 0; spacing: 0;" src="../media/download.png" alt="Download button"></a><br />
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-preview.svg" width="128px" alt="Visual Studio Preview logo" /></td>
    <td  style="border:none;">
        <strong>Visual Studio 2019 </strong><br />
        1. Installez la dernière préversion de <a href="https://aka.ms/vs-preview">Visual Studio 2019</a>.<br/>
        2. Installez une <a href="../reference/platform-support.md">charge de travail prise en charge</a>. (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)<br />
        3. Visual Studio Live Share est installé par défaut avec ces charges de travail. <br />
    </td>
</tr>
</table>

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

## <a name="2-optional-join-as-a-read-only-guest-in-vs-code"></a>2. [jointure de facultatif] en tant qu’en lecture seule invité dans VS Code

Dans VS Code, après avoir installé l’extension de partage en direct, le redémarrage et en attente pour les dépendances pour terminer l’installation, vous pouvez lancer et de rejoindre une session de collaboration en tant qu’un invité en lecture seule.

> [!NOTE]
> Si vous souhaitez apporter des modifications au code que vous joignez, vous devrez [connectez-vous](../quickstart/join.md#3-Sign-in).

Ouvrez (ou ouvrez à nouveau) le lien d’invitation dans un navigateur, et vous recevrez une notification que le navigateur souhaite lancer VS Code. Laissez-le lancer, et il commencerons la connexion à la session de collaboration.

Lancement de VS Code, vous obtiendrez une notification toast vous demandant de vous connecter. Cliquez sur « Continuer en tant qu’invité en lecture seule » à la session.

![Joindre en tant que session sous la forme d’un toast invité en lecture seule](../media/vscode-read-only-guest.png)

Vous devrez entrer un nom d’affichage pour aider les participants à vous identifier dans la session.

![Nom de l’invité en lecture seule](../media/vscode-read-only-guest-name.png)

Par la suite, vous allez être joint dans la session en lecture seule. Vous serez en mesure d’afficher et naviguer dans le code, débogage copropriétaire et afficher partagé les serveurs et terminaux (en lecture seule).

> [!NOTE]
> Si vous souhaitez ultérieurement accéder en lecture/écriture pour le code, vous pouvez vous connecter. Cliquez sur votre nom d’affichage de l’état, barre et sélectionnez l’option « connexion ».
![Connexion en lecture seule invité](../media/vscode-read-only-guest-signin.png) cette action lance votre navigateur, et vous pouvez choisir un compte Microsoft ou GitHub pour vous connecter à l’aide.

## <a name="3-sign-in"></a>3. Se connecter

Après l’installation de l’extension de partage en direct, redémarrer et attend les dépendances terminer l’installation (VS Code), vous souhaitez vous connecter à informer les autres participants qui vous êtes. Si vous ignorez cette étape, vous êtes invité à se connecter pendant le processus de jonction ou pourrez rejoindre la session en tant qu’un invité en lecture seule. Cliquez sur l’élément de barre d’état « partage » (VS Code) / « connexion » bouton (VS) pour commencer.

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

Dans **VS Code**, votre navigateur s’ouvre pendant une notification s’affiche vous demandant de se connecter de lancement. L’inscription dans le processus dans votre navigateur, puis il suffit de fermer le navigateur lorsque vous avez terminé.

![Notification toast vous demandant de se connecter à l’aide d’un navigateur web](../media/vscode-sign-in-toast.png)

> **Utilisateurs Linux :** Vous pouvez être invité à entrer un code utilisateur si vous utilisez une version antérieure de partage en direct (v0.3.295 ou ci-dessous). Mettre à jour vers la dernière version de l’extension ou cliquez sur le « avoir problèmes ? » lien après connexion pour afficher le code. Consultez [ici pour plus d’informations](../use/vscode.md#sign-in-using-a-user-code).

Dans **Visual Studio**, Partage Live utilise automatiquement votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Par conséquent, vous pouvez simplement vous connecter comme vous le feriez normalement. Toutefois, si vous préférez utiliser un autre connectez-vous à votre compte de personnalisation de Visual Studio, accédez à **outils &gt; Options &gt; Partage Live &gt; compte d’utilisateur** et sélectionnez les informations d’identification différentes.

Consultez [dépannage](../troubleshooting.md#sign-in) si vous rencontrez toujours des problèmes.

## <a name="4-openre-open-the-invite-link-in-a-browser"></a>4. Open/ré-open lien de l’invitation dans un navigateur

À présent, ouvrez simplement (ou ouvrez à nouveau) le lien d’invitation dans un navigateur.

> **Remarque** : Si vous n’avez pas encore installé l’extension de partage en direct, s’affiche avec des liens vers la place de marché d’extension. Installer l’extension et redémarrez votre outil et réessayez.

Vous devez averti que le navigateur souhaite lancer un outil de partage en direct est activé. Si vous la laissez lancer votre outil sélectionné, vous devez être connecté à la session de collaboration, une fois démarré.

![Joindre la page](../media/join-page.png)

Si l’hôte est hors connexion, vous serez averti à ce stade au lieu de cela. Vous pouvez ensuite contacte l’ordinateur hôte et demandez-lui de le partager à nouveau.

> **Conseil de dépannage :** Lorsque vous utilisez VS Code, veillez à ce que vous avez **démarrer l’outil au moins une fois** après l’installation de l’extension et a attendu pour les dépendances terminer l’installation (voir la barre d’état) avant ouverture/ré-opening la page de l’invitation. Rencontrez encore des problèmes ? Consultez [joindre manuellement des](../reference/manual-join.md) pour plus d’informations.

## <a name="5-collaborate"></a>5. Collaborer !

C’est tout ! Dans quelques instants, vous vous connectez à la session de collaboration de votre collègue. Par défaut, l’hôte automatique-accepte les personnes qui joignent, mais si l’hôte est configuré pour [exiger l’approbation de l’invité](../reference/security.md#requiring-guest-approval) vous serez voir la barre d’état / joindre la mention de boîte de dialogue Partage Live est en attente sur l’hôte pour approuver votre demande de participation.

> **Astuce de sécurité :** En tant qu’invité rejoindre une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou des fonctionnalités. Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités et les paramètres du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

Voici quelques éléments à essayer :

1. Déplacer le projet indépendamment et apporter des modifications
2. Découvrez travail intellisense pour JavaScript, TypeScript, et/ou C# code
3. Modifier un élément avec l’hôte
4. Suivez l’hôte et vous déplacer dans avec eux lorsqu’ils accèdent et que vous apportez des modifications dans différents fichiers
5. Démarrer une session de débogage conjointement avec l’hôte
6. Demandez à l’hôte à un serveur pour vous pouvez de vérifier ressembler à une application web en cours d’exécution sur leur ordinateur
7. Demandez à l’hôte pour partager un terminal et exécuter des commandes

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).

## <a name="next-steps"></a>Étapes suivantes

Consultez ces articles supplémentaires pour plus d’informations.

- [Démarrage rapide : Partager votre premier projet](share.md)
- [Comment : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Comment : Collaborer à l’aide de Visual Studio](../use/vs.md)

Référence

- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
