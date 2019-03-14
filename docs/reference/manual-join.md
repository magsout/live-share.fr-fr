---
title: Jointure manuelle - partage en direct de Visual Studio | Microsoft Docs
description: Partager des informations sur la jointure de manuellement une session de collaboration dans Visual Studio Live.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 57d26c2c63bd5b92e62a72368f97bb8aee63313c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255543"
---
# <a name="join-a-session-manually"></a>Rejoindre une session manuellement

En plus de l’ouverture d’un lien dans un navigateur pour rejoindre une session de collaboration, vous pouvez joindre manuellement en collant le lien dans un outil déjà en cours d’exécution. Cela peut être utile si vous souhaitez utiliser un autre outil que vous le faites habituellement, ou si vous rencontrez des problèmes avec l’obtention des liens d’invitation à fonctionner pour une raison quelconque.

Les instructions exactes varient entre [Visual Studio](#join-from-visual-studio) et [Visual Studio Code](#join-from-visual-studio-code), donc choisir l’outil que vous souhaitez utiliser pour plus d’informations.

## <a name="join-from-visual-studio-code"></a>Joindre à partir de Visual Studio Code

### <a name="1-sign-in"></a>1. Se connecter

>**Remarque :** Si vous souhaitez rejoindre une session de collaboration en tant qu’un invité en lecture seule, vous pouvez ignorer la connexion. Vous allez avoir accès à l’affichage et la navigation dans le code qui est partagé mais ne pas être en mesure d’apporter des modifications.

![Notification toast vous demandant de se connecter à l’aide d’un navigateur web](../media/vscode-sign-in-toast.png)

Afin de collaborer, vous devez l’authentification dans le partage en direct de Visual Studio pour que tout le monde sache qui vous êtes. **Cliquez sur** sur l’état « Live Share » élément ou appuyez sur la barre **Ctrl + Maj + P / Cmd + Maj + P** et sélectionnez le « partage en direct : Commande connectez-vous avec le navigateur ».

![Bouton de connexion Visual Studio Code](../media/vscode-sign-in-button.png)

Votre navigateur s’ouvre pendant une notification s’affiche vous demandant de se connecter de lancement. L’inscription dans le processus dans votre navigateur, puis il suffit de fermer le navigateur lorsque vous avez terminé.

Si vous rencontrez des problèmes avec VS Code ne pas reprenant une réussite de connexion à, cliquez sur le lien « Des difficultés à » sur l’écran de confirmation dans le navigateur et suivez les instructions. Découvrez [dépannage](../troubleshooting.md#sign-in) pour plus de conseils.

### <a name="2-use-the-join-command"></a>2. Utilisez la commande de jointure

Ouvrir le vues font Live de partage dans la barre d’activités de VS Code, puis sélectionnez la « jointure collaboration session... » icône ou entrée.

![Icône de vues font de jointure](../media/vscode-join-viewlet.png)

>**Remarque :** Si vous joignez tant qu’invité en lecture seule, vous puis demandera d’entrer un nom d’affichage pour aider les participants à vous identifier dans la session.

### <a name="3-paste-the-invite-link"></a>3. Collez le lien d’invitation

Collez l’URL de l’invitation vous ont été envoyés et que vous appuyez sur « ENTRÉE » pour confirmer.

C’est tout ! Vous devez être connecté à la session de collaboration momentanément.

## <a name="join-from-visual-studio"></a>Joindre à partir de Visual Studio

### <a name="1-sign-in"></a>1. Se connecter

Une fois installé, démarrez Visual Studio et connectez-vous si vous n’avez pas encore. Si vous devez utiliser une autre connexion à Visual Studio que votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), accédez à **outils &gt; Options &gt; Partage Live &gt; compte d’utilisateur**.

![Se connecter Visual Studio](../media/vs-sign-in-button.png)

Rencontrez encore des problèmes ? Consultez [dépannage](../troubleshooting.md#sign-in).

### <a name="2-use-the-join-command"></a>2. Utilisez la commande de jointure

Accédez simplement à **fichier > rejoindre une Session de Collaboration**.

![Menu de jointure de VS](../media/vs-join.png)

### <a name="3-paste-the-invite-link"></a>3. Collez le lien d’invitation

Collez l’URL de l’invitation vous ont été envoyés et que vous appuyez sur « ENTRÉE » pour confirmer.

C’est tout ! Vous devez être connecté à la session de collaboration momentanément.

## <a name="see-also"></a>Voir aussi

Démarrages rapides

- [Démarrage rapide : Partager votre premier projet](../quickstart/share.md)
- [Démarrage rapide : Joindre votre première session](../quickstart/join.md)

Articles Comment faire

- [Comment : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Comment : Collaborer à l’aide de Visual Studio](../use/vs.md)
- [Comment : Fournir des commentaires](../support.md)

Référence

- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Détails d’installation pour Linux](linux.md)
- [Prise en charge de langues et de plateformes](platform-support.md)
- [Extensions prises en charge](extensions.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
