---
title: Partager le démarrage rapide - Visual Studio Live Share | Microsoft Docs
description: Une procédure pas-à-pas abrégée sur le partage de votre premier projet à l’aide d’une session de collaboration Visual Studio Live Share.
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
ms.openlocfilehash: e65656c604a9dbc479a03a503fe01d7e2d938072
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2020
ms.locfileid: "73170015"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="quickstart-share-your-first-project"></a>Quickstart : Partagez votre premier projet

Bienvenue dans Visual Studio Live Share ! Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Cette solution vous permet de partager instantanément et en toute sécurité votre projet en cours, puis de partager au besoin des sessions de débogage, des instances de terminal, des applications web localhost, des appels vocaux, etc.

Prêt pour le départ ?  La collaboration d’équipe doit être si rapide et naturelle, qu’il devient plus difficile de ne pas le faire ! C’est pour cette raison que Visual Studio Live Share simplifie la prise en main, afin que vous puissiez commencer en toute transparence à partager vos travaux et idées.

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

Suivez ces étapes pour commencer le partage.
<!--
Change the instructions to Install extension for VS Code and in-tool for VS?
-->
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
        4. <strong>Linux</strong>: Si vous êtes invité à <a href="../reference/linux.md#install-linux-prerequisites">installer des bibliothèques,</a>cliquez sur installer, entrez mot de passe, redémarrez le code VS une fois terminé.<br />
        <a href="https://aka.ms/vsls-dl/vscode"><img src="../media/download.png" alt="Download button"></a>
    </td>
</tr>
<tr style="border:none;">
    <td width="128px" style="width: 128px; text-align: center; border:none;"><img src="../media/vs-ide-2019.svg" width="128px" alt="Visual Studio 2019 logo" /></td>
    <td  style="border:none;">
        <strong>Studio visuel 2019</strong><br />
        1.Installer <a href="https://visualstudio.microsoft.com/downloads/">Visual Studio 2019</a>.<br/>
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

## <a name="2-sign-in"></a>2. Connectez-vous

<!--
Re-write the grammar here- run on sentence does not make sense. Change screen shots. There is another way of signing in as well- what if a user goes directly to the start collaboration. 
-->
Une fois l’extension Live Share installée, après avoir redémarré et attendu la fin de l’installation des dépendances (VS Code), vous devrez vous connecter pour vous identifier auprès des autres participants. Cliquez simplement sur l’élément « Live Share » sur la barre d’état (VS Code) ou sur le bouton « Se connecter » (VS) pour commencer.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-sign-in-button-new.png" width="100%" alt="Visual Studio Code sign in status bar item"/>
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-sign-in-button.png" width="100%" alt="Visual Studio sign in button"/>
    </td>
</tr>
</table>

Dans **VS Code**, votre navigateur se lance tandis qu’une notification s’affiche vous demandant de vous connecter. Terminez le processus de connexion dans votre navigateur, puis fermez simplement le navigateur.

![Notification toast demandant de se connecter à l’aide d’un navigateur Web](../media/vscode-sign-in-toast.png)

> **Utilisateurs de Linux:** Vous pouvez être invité à entrer un code utilisateur si vous utilisez une ancienne version de Live Share (v0.3.295 ou ci-dessous). Mettez à jour vers la dernière version de l’extension ou cliquez sur le lien « Vous rencontrez des problèmes ? » après vous être connecté pour afficher le code. Voir [ici pour plus de détails](../use/vscode.md#sign-in-using-a-user-code).

Dans **Visual Studio**, Live Share utilise automatiquement votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio). Par conséquent, vous pouvez simplement vous connecter comme vous le feriez normalement. Toutefois, si vous préférez utiliser d’autres informations d’identification que celles de votre compte de personnalisation Visual Studio, accédez à **Outils &gt; Options &gt; Live Share &gt; Compte d’utilisateur** et sélectionnez des informations d’identification différentes.

Consultez la section [Résolution des problèmes](../troubleshooting.md#sign-in) si vous rencontrez toujours des problèmes.

## <a name="3-open-a-folder-project-or-solution"></a>3. Ouvrez un dossier, un projet ou une solution

Utilisez votre flux de travail habituel pour ouvrir un dossier, un projet ou une solution que vous souhaitez partager dans Visual Studio ou Visual Studio Code.

### <a name="4-optional-update-hidden-or-excluded-files"></a>4. [Facultatif] Mise à jour masquée ou fichiers exclus

Par défaut, Live Share **masque** tous les fichiers/dossiers référencés dans les fichiers .gitignore dans vos dossiers partagés. **Masquer** un fichier l’empêche d’apparaître dans l’arborescence des fichiers de l’invité. **L’exclusion** d’un fichier applique une règle plus stricte qui empêche Live Share de l’ouvrir pour l’invité dans des situations comme « Atteindre la définition » ou si vous parcourez le fichier pendant le débogage ou le « suivi ». Pour masquer/exclure différents fichiers, ajoutez à votre projet un fichier **.vsls.json** comportant ces paramètres. Pour plus d’informations, voir [Contrôler l’accès aux fichiers et leur visibilité](../reference/security.md#controlling-file-access-and-visibility).

## <a name="5-start-a-collaboration-session"></a>5. Démarrer une session de collaboration

<!--
-->
Ensuite, cliquez simplement sur « Live Share » dans l’outil et un lien d’invitation sera automatiquement copié dans votre Presse-papiers.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-share-button-new.png" width="100%" alt="Visual Studio Code share status bar item" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-share-button.png" width="100%" alt="Visual Studio share button"/>
    </td>
</tr>
</table>

> [!NOTE]
> Votre logiciel de pare-feu de bureau pourra vous demander d’autoriser l’agent Live Share à ouvrir un port lors du premier partage. Cette autorisation est entièrement facultative mais permet à un « mode direct » sécurisé d’améliorer les performances lorsque la personne avec laquelle vous travaillez se trouve sur le même réseau que vous. Consultez [Modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode) pour plus d’informations.

## <a name="6-optional-enable-read-only-mode"></a>6. [Facultatif] Activer le mode lecture seule

Une fois la session de collaboration démarrée, vous pouvez configurer la session afin qu’elle soit en mode lecture seule, pour empêcher les invités d’apporter des modifications au code partagé.

Après le partage, vous recevez une notification vous informant que le lien d’invitation a été copié dans le Presse-papiers. Vous pourrez alors sélectionner l’option permettant de passer la session en lecture seule.

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

Dans **VS Code**, vous pouvez également démarrer une session en lecture seule à partir de l’onglet d’affichage Live Share.

![Notification toast demandant de se connecter à l’aide d’un navigateur Web](../media/vscode-read-only-viewlet.png)

### <a name="7-send-someone-the-invite-link"></a>7. Envoyer à quelqu’un le lien d’invitation

Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Ouvrir le lien dans un navigateur leur permet de rejoindre la session de collaboration qui partage le contenu du dossier, du projet ou de la solution que vous avez ouvert. Étant donné le niveau d’accès que les sessions Live Share peuvent offrir aux invités, **limitez les partages aux personnes de confiance** et pensez aux implications de ce que vous partagez.

> **Conseil de sécurité:** Vous voulez comprendre les implications en matière de sécurité de certaines fonctionnalités de Live Share ? Consultez l’article [Sécurité](../reference/security.md).

Si l’invité que vous avez invité a des questions, le [Quickstart: Joignez-vous à votre](join.md) article de première session fournit quelques informations plus sur se lever et courir en tant qu’invité.

## <a name="8-optional-approve-the-guest"></a>8. [Facultatif] Approuver l’invité

Par défaut, les invités rejoignent automatiquement votre session de collaboration, et vous êtes averti lorsqu’ils sont prêts à travailler avec vous.

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

Vous pouvez également choisir d’exiger une « approbation » explicite pour toute personne rejoignant la session. Si ce paramètre est activé, une notification vous invite à approuver l’invité lorsqu’ils tentent de rejoindre votre session.

Consultez [Demande d’approbation de l’invité](../reference/security.md#requiring-guest-approval) pour plus d’informations sur la façon d’activer cette fonctionnalité.

## <a name="9-collaborate"></a>9. Collaborer!

Et voilà ! Voici quelques éléments à essayer une fois qu’un invité vous a rejoint :

1. Se déplacer dans plusieurs fichiers dans le projet de manière indépendante et leur apporter des modifications
1. Suivre l’invité et l’observer faire défiler, apporter des modifications et accéder à différents fichiers
1. Démarrer une session de codébogage
1. Partager un serveur pour vérifier une application Web en cours d’exécution sur leur machine
1. Partager un terminal et exécuter des commandes

Consultez les documents d’extension [Visual Studio Code](../use/vscode.md) et [Visual Studio](../use/vs.md) pour plus d’informations sur la manière d’effectuer ces actions et bien plus encore.

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations, voir ces articles complémentaires.

- [Quickstart : Joignez-vous à votre première session de collaboration](join.md)
- [Comment faire : Collaborer à l’aide du code Visual Studio](../use/vscode.md)
- [Comment faire : Collaborer à l’aide de Visual Studio](../use/vs.md)

Informations de référence

- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Soutien d’extension](../reference/extensions.md)
