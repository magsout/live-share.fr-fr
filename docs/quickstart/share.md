---
title: Partager le Guide de démarrage rapide - partage en direct de Visual Studio | Microsoft Docs
description: Une procédure pas à pas abrégées sur le partage de votre premier projet à l’aide d’une session de collaboration le Partage Live Visual Studio.
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
ms.openlocfilehash: 3596b25dc0d08962d7813f52549dbe6fef4f00a0
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255499"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Démarrage rapide : Partager votre premier projet

> **Remarque : Visual Studio Live Share est actuellement en préversion. L’expérience utilisateur et les fonctionnalités ne sont pas définitives.**

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Cette solution vous permet de partager instantanément et en toute sécurité votre projet en cours, puis de partager au besoin des sessions de débogage, des instances de terminal, des applications web localhost, des appels vocaux, etc.

Prêt pour le départ ?  Collaboration d’équipe doit être rapide et naturelle, qu’il devient plus difficile de ne pas le faire ! Pour cette raison, partage en direct de Visual Studio simplifie prise en main, afin que vous puissiez commencer en toute transparence votre travail et des idées de partage.

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité dans les deux instances. À tester dès maintenant !

Suivez ces étapes pour commencer à partager.

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
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
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

## <a name="2-sign-in"></a>2. Se connecter

Après l’installation de l’extension de partage en direct, redémarrer et attend les dépendances terminer l’installation (VS Code), vous souhaitez vous connecter à informer les autres participants qui vous êtes. Cliquez simplement sur l’élément de barre d’état « Live Share » (VS Code) / « Connexion » bouton (VS) pour commencer.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
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

## <a name="3-open-a-folder-project-or-solution"></a>3. Ouvrir un dossier, un projet ou une solution

Pour ouvrir un dossier, un projet ou une solution que vous souhaitez partager dans Visual Studio ou Visual Studio Code, utilisez votre flux de travail normal.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [mise à jour facultatif] masquée ou de fichiers exclus

Par défaut, Partage Live **masque** les fichiers/dossiers référencés dans les fichiers .gitignore dans vos dossiers partagés d’invités. **Masquage** un fichier empêche d’apparaître dans l’arborescence des fichiers de l’invité. **À l’exclusion** un fichier applique une règle plus stricte qui empêche le partage en direct de l’ouvrir pour l’invité dans des situations comme atteindre la définition ou si vous parcourez le fichier pendant le débogage, ou « suivi ». Si vous souhaitez masquer/exclure des fichiers différents, un **. vsls.json** fichier peut être ajouté à votre projet avec ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

## <a name="5-start-a-collaboration-session"></a>5. Démarrer une session de collaboration

Ensuite, cliquez simplement sur « Live Share » au sein de votre outil et un lien d’invitation est automatiquement copié dans le Presse-papiers.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Vous pouvez être invité par votre logiciel de pare-feu de bureau pour permettre à l’agent Partage Live ouvrir un port de la première fois que vous partagez. Accepter ce est entièrement facultative mais permet un « mode direct » sécurisé pour améliorer les performances lorsque la personne que vous utilisez est sur le même réseau que vous êtes. Consultez [modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode) pour plus d’informations.

## <a name="6-optional-enable-read-only-mode"></a>6. [facultatif] activer le mode en lecture seule

Une fois que vous démarrez votre session de collaboration, vous pouvez définir la session peut être en lecture seule pour empêcher les invités d’apporter des modifications au code partagé.

Après le partage, vous recevez une notification que le lien d’invitation a été copié dans le Presse-papiers. Vous pouvez ensuite sélectionner l’option pour que la session en lecture seule.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-read-only-toast.png" width="100%" alt="Visual Studio Code read-only option" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-read-only-notification.png" width="100%" alt="Visual Studio read-only option"/>
    </td>
</tr>
</table>

Dans **VS Code**, vous pouvez également démarrer une session en lecture seule à partir de l’onglet de vues font Live de partage.

![Notification toast vous demandant de se connecter à l’aide d’un navigateur web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Envoyer le lien d’invitation

Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Ouvrir le lien dans un navigateur leur permet de rejoindre la session de collaboration qui partage le contenu du dossier, du projet ou de la solution que vous avez ouvert. Notez que, étant donné le niveau d’accès de partage Live sessions peuvent fournir aux invités, **vous devez uniquement partager avec des personnes dignes de confiance** et réflexion via les implications de ce que vous partagez.

> **Astuce de sécurité :** Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

Si l’invité que vous avez invité a des questions, le [Guide de démarrage rapide : Joindre votre première session](join.md) article fournit des informations supplémentaires sur les rendre opérationnel et en cours d’exécution en tant qu’invité.

## <a name="8-optional-approve-the-guest"></a>8. [facultatif] approuver l’invité

Par défaut, les invités joint automatiquement votre session de collaboration, et vous êtes informé quand ils sont prêts à travailler avec vous.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Vous pouvez choisir d’exiger une « approbation » explicite pour toute personne joignant à la place. Si vous avez ce paramètre est activé, une notification vous invite à approuver l’invité lorsqu’ils tentent de joindre votre session.

Consultez [nécessitant une approbation de l’invité](../reference/security.md#requiring-guest-approval) pour plus d’informations sur la façon d’activer cette fonctionnalité.

## <a name="9-collaborate"></a>9. Collaborer !

C’est tout ! Voici quelques éléments à essayer une fois qu’un invité a joint à vous :

1. Déplacer à plusieurs fichiers dans le projet indépendamment et apporter des modifications
1. Suivez l’invité et observer lorsqu’ils faire défiler, apporter des modifications et accédez à différents fichiers
1. Démarrer une session de débogage conjointement avec eux
1. Partager un serveur pour vous pouvez de vérifier ressembler à une application web en cours d’exécution sur leur ordinateur
1. Partager un terminal et exécuter des commandes

Découvrez le [Visual Studio Code](../use/vscode.md) et [Visual Studio](../use/vs.md) docs d’extension pour plus d’informations sur comment effectuer ces actions et bien plus encore.

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).

## <a name="next-steps"></a>Étapes suivantes

Consultez ces articles supplémentaires pour plus d’informations.

- [Démarrage rapide : Joindre votre première session de collaboration](join.md)
- [Comment : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Comment : Collaborer à l’aide de Visual Studio](../use/vs.md)

Référence

- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
