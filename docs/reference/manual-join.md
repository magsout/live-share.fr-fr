---
title: Jointure manuelle-Visual Studio Live Share | Microsoft Docs
description: Informations sur la jointure manuelle d’une session de collaboration dans Visual Studio Live share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d46cb53a28bfac1c088371ff5eecdb6af0c8420
ms.sourcegitcommit: 3a1b22eac528b0f6a241f9fec7ec20264db24cfe
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74019793"
---
# <a name="join-a-session-manually"></a>Joindre une session manuellement

En plus d’ouvrir un lien dans un navigateur pour rejoindre une session de collaboration, vous pouvez effectuer une jointure manuelle en collant le lien dans un outil déjà en cours d’exécution. Cela peut être utile si vous souhaitez utiliser un autre outil que vous le faites habituellement ou si vous rencontrez des difficultés pour que l’obtention de liens d’invitation fonctionne pour une raison quelconque.

Les instructions exactes varient entre [Visual Studio](#join-from-visual-studio) et [Visual Studio code](#join-from-visual-studio-code), donc choisissez l’outil que vous souhaitez utiliser pour plus d’informations.

## <a name="join-from-visual-studio-code"></a>Joindre à partir de Visual Studio Code

### <a name="1-sign-in"></a>1. Connectez-vous

>**Remarque :** Si vous souhaitez joindre une session de collaboration en tant que guesasdsat en lecture seule, vous pouvez ignorer la connexion. Vous aurez accès à l’affichage et à la navigation dans le code partagé, mais vous ne pourrez pas apporter de modifications.

![Notification toast demandant de se connecter à l’aide d’un navigateur Web](../media/vscode-sign-in-toast.png)

Pour pouvoir travailler en collaboration, vous devez vous connecter à Visual Studio Live Share ; ainsi, tout le monde saura qui vous êtes. **Cliquez** sur l’élément de la barre d’état « Live share » ou appuyez sur **Ctrl + Maj + P/CMD + MAJ + P** , puis sélectionnez la commande « Live share : se connecter avec le navigateur ».

![Bouton de connexion de VS Code](../media/vscode-sign-in-button.png)

Votre navigateur est lancé alors qu’une notification s’affiche, vous invitant à vous connecter. Terminez le processus de connexion dans votre navigateur, puis fermez simplement le navigateur.

Si vous rencontrez des problèmes avec VS Code ne sélectionnez pas une connexion réussie, cliquez sur le lien « pose des problèmes » dans l’écran de réussite du navigateur et suivez les instructions. Pour plus d’informations, consultez [résolution des problèmes](../troubleshooting.md#sign-in) .

### <a name="2-use-the-join-command"></a>2. Utilisez la commande join

Ouvrez la Live Share Viewlet dans la barre d’activité VS Code, puis sélectionnez « joindre une session de collaboration... » icône ou entrée.

![Icône de la viewlet d’accès](../media/vscode-join-viewlet.png)

>**Remarque :** Si vous vous joignez en tant qu’invité en lecture seule, vous êtes invité à entrer un nom d’affichage pour aider les participants à vous identifier dans la session.

### <a name="3-paste-the-invite-link"></a>3. coller le lien d’invitation

Collez l’URL d’invitation que vous avez envoyée et appuyez sur entrée pour confirmer.

C’est tout ! Vous avez momentanément accès à la session de collaboration.

## <a name="join-from-visual-studio"></a>Joindre à partir de Visual Studio

### <a name="1-sign-in"></a>1. Connectez-vous

Une fois l’installation terminée, démarrez Visual Studio et connectez-vous si vous ne l’avez pas déjà fait. Si vous devez utiliser une connexion différente pour Visual Studio que votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), accédez à **outils &gt; Options &gt; Live share &gt; compte d’utilisateur**.

![Connexion VS](../media/vs-sign-in-button.png)

Si le problème persiste, Consultez [résolution des problèmes](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. Utilisez la commande join

Accédez simplement à **fichier > rejoindre une session de collaboration**.

![Menu Rejoindre de Visual Studio](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. coller le lien d’invitation

Collez l’URL d’invitation que vous avez envoyée et appuyez sur entrée pour confirmer.

C’est tout ! Vous avez momentanément accès à la session de collaboration.

## <a name="see-also"></a>Voir aussi

Guides de démarrage rapide

- [Démarrage rapide : partager votre premier projet](../quickstart/share.md)
- [Démarrage rapide : rejoindre votre première session](../quickstart/join.md)

Articles Comment faire

- [Comment : collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Comment : collaborer à l’aide de Visual Studio](../use/vs.md)
- [Comment : fournir des commentaires](../support.md)

Reference

- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Détails d’installation pour Linux](linux.md)
- [Prise en charge de langues et de plateformes](platform-support.md)
- [Extensions prises en charge](extensions.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
