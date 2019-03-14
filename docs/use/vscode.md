---
title: Collaborer à l’aide de Visual Studio Code - partage en direct de Visual Studio | Microsoft Docs
description: Un ensemble de procédures de collaboration pour Visual Studio Code et de partage en direct.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9285fef38fea9bb164892775521ed2a28fe9ef1b
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255556"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Comment : Collaborer à l’aide de Visual Studio Code

Prêt à obtenir en collaboration avec Partage Live dans VS Code ?  Si tel est le cas, vous êtes au bon endroit ! Dans cet article, nous allons vous guider comment utiliser certaines des fonctionnalités spécifiques dans l’extension de le Partage Live Visual Studio pour Visual Studio Code.

Notez que toutes les activités de collaboration décrites ici impliquent un seul **hôte de session de collaboration** et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

*Vous recherchez une synthèse abrégée ? Découvrez le [partager](../quickstart/share.md) ou [jointure](../quickstart/join.md) Démarrages rapides à la place.*

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité dans les deux instances. À tester dès maintenant !

## <a name="installation"></a>Installation

Avant de commencer, vous aurez besoin pour être sûr que vous avez une version de Visual Studio Code installé qui répond aux exigences de base du partage en direct. Vous devez **Visual Studio Code (1.22.0 ou une version ultérieure)** en cours d’exécution :

- **Windows**: 7, 8.1 ou 10

- **macOS**: Sierra (10.12) et versions ultérieures uniquement.
    - _EL Capitan (10.11) ci-dessous ne sont pas actuellement pris en charge en raison [configuration requise de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux** : Bureau d’Ubuntu 16.04 +, station de travail Fedora 27 +, CentOS 7 64 bits

    - Partage en direct requiert un nombre de [conditions préalables de Linux](#linux-install-steps) vous pouvez être invité à installer.
    - _Linux 32 bits n’est pas pris en charge en raison [configuration requise de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM est actuellement pas prise en charge.
    - Consultez le [Linux installer détails](../reference/linux.md) article pour plus d’informations sur l’utilisation en aval et d’autres distributions.

Ensuite, le téléchargement et l’installation de l’extension Visual Studio Live Share sont un jeu d’enfant :

1. Installer <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [Télécharger](https://aka.ms/vsls-dl/vscode) et installer l’extension de le Partage Live Visual Studio à partir de la place de marché.
3. Recharger le Code de Visual Studio
4. Attendez que les dépendances télécharger et installer (voir barre d’état).<br/>
    ![Terminer l’installation](../media/vscode-finishing-install.png)
5. **Linux** : Si vous voyez une notification sur l’installation des bibliothèques manquants :
    1. Cliquez sur « Installer » dans la notification.
    2. Entrez votre mot de passe administrateur (sudo) lorsque vous y êtes invité.
    3. Redémarrez VS Code lorsque vous avez terminé.

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

[![Téléchargement](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Procédure d’installation Linux

Linux est un environnement très variable et le nombre d’environnements de bureau et des distributions peut être compliqué à mettre en œuvre. Si vous respectez les versions prises en charge de **bureau Ubuntu** (16.04 +) ou **station de travail Fedora** (27 +), **CentOS 7** et utiliser uniquement **distributions officielles de VS Code**, vous devez rechercher le processus simple. Toutefois, dans le cas où vous utilisez une configuration non standard ou la distribution en aval, vous pouvez ou peut ne pas fonctionner dans certaines interruptions. Consultez [détails de l’installation Linux](../reference/linux.md) pour plus d’informations.

#### <a name="install-linux-prerequisites"></a>Installez les composants requis Linux

Certaines distributions de Linux n’ont pas de bibliothèques que Partage Live a besoin pour fonctionner. Par défaut, Partage Live tente de détecter et installer les composants requis Linux pour vous. Vous verrez une notification toast lorsque Partage Live rencontre un problème peut provenir de bibliothèques manquants demandant l’autorisation de les installer.

![Notification toast montrant le message que Linux, composants requis sont manquants](../media/vscode-linux-prereq-missing.png)

Lorsque vous cliquez sur « Installer », une fenêtre de terminal s’affiche où vous devrez entrer votre mot de passe administrateur (sudo) pour continuer. En supposant qu’il se termine correctement, redémarrez Visual Studio Code, vous devez être prêt ! Vous pouvez également extraire **[conseils par distribution](../reference/linux.md#tips-by-distribution)** pour d’autres indicateurs et les solutions de contournement s’il en existe.

Si vous voyez un message indiquant le script ne prend pas en charge votre distribution, consultez **[conseils pour les distributions de communauté pris en charge](../reference/linux.md#tips-for-community-supported-distros)** pour plus d’informations, la Communauté a partagé avec nous.

Si vous **pour ne plus avoir de VS Code, exécutez la commande pour vous**, vous pouvez aussi pour réexécuter la toute dernière version de ce script à tout moment manuellement en exécutant la commande suivante à partir d’une fenêtre de Terminal :

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Intégration de navigateur Linux

Visual Studio Live partagent généralement **ne nécessite pas d’étapes d’installation supplémentaires** pour activer l’intégration de navigateur sur Linux.

While rare sur certaines distributions vous **peut être averti que votre mot de passe administrateur (sudo) est nécessaire** pour terminer le processus d’installation. Une fenêtre de terminal s’affiche vous indiquant où le service de lancement du navigateur sera installée. Entrez simplement votre mot de passe lorsque vous y êtes invité et appuyez sur entrée une fois l’installation terminée pour fermer la fenêtre de terminal.

Vous pouvez en savoir plus sur quoi cela est nécessaire et partageons Live place les fichiers  **[ici](../reference/linux.md#linux-browser-integration)**. Notez, même si vous ne parvenez pas à faire fonctionner d’intégration de navigateur que vous pouvez toujours  **[joindre manuellement des sessions de collaboration](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Se connecter

Afin de collaborer, vous devez vous connecter à partage en direct de Visual Studio pour que tout le monde sache qui vous êtes. Cela est purement une mesure de sécurité et que vous ne **pas** vous opter pour n’importe quel marketing ou d’autres activités de recherche. Vous pouvez vous connecter avec un compte personnel Microsoft (par exemple, @outlook.com), appuyé par Microsoft compte professionnel ou scolaire (AAD) ou un compte GitHub. Il est facile de la connexion.

**Cliquez sur** sur l’état « Partage » de la barre élément ou appuyez sur **Ctrl + Maj + P / Cmd + Maj + P** et sélectionnez le « partage en direct : Commande connectez-vous avec le navigateur ».

![Bouton de connexion Visual Studio Code](../media/vscode-sign-in-button.png)

Une notification s’affiche vous demandant de se connecter à l’aide de votre navigateur web. En cliquant sur « connexion lancement » s’ouvre un navigateur que vous pouvez utiliser pour terminer le processus de connexion. Fermez le navigateur lorsque vous avez terminé.

![Notification toast vous demandant de se connecter à l’aide d’un navigateur web](../media/vscode-sign-in-toast.png)

> **Utilisateurs Linux :** Vous pouvez être invité à entrer un code utilisateur si vous utilisez une version antérieure de partage en direct (v0.3.295 ou ci-dessous). Mettre à jour vers la dernière version de l’extension ou cliquez sur le « avoir problèmes ? » lien après connexion pour afficher le code. Consultez [ci-dessous pour plus d’informations](#sign-in-using-a-user-code).

Si Visual Studio Code est reprenant pas vos informations d’identification après avoir terminé le processus de connexion dans le navigateur, consultez [connectez-vous à l’aide d’un code utilisateur](#sign-in-using-a-user-code). Dans le cas contraire, consultez [dépannage](../troubleshooting.md#sign-in) pour plus de conseils.

### <a name="sign-in-using-a-user-code"></a>Connectez-vous à l’aide d’un code utilisateur

Si vous rencontrez des problèmes avec VS Code ne pas reprenant un dans lequel l’authentification terminé, vous pouvez entrer un code « utilisateur » à la place.

1. Appuyez sur **Ctrl + Maj + P / Cmd + Maj + P** et exécuter le « partage en direct : Commande connectez-vous avec le code utilisateur ».

2. Un navigateur doit apparaître pour vous permet de terminer le processus de connexion.

    > [!NOTE]
    > Si un navigateur n’apparaît pas automatiquement, ouvrez [cet emplacement](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) dans un navigateur et de la connexion.

3. Une fois que vous avez terminé, cliquez sur « vous rencontrez des problèmes ? Cliquez ici pour des instructions de code utilisateur » pour afficher le code utilisateur.

    ![Image du code utilisateur dans le navigateur](../media/vscode-user-code-browser.png)

4. Copiez le code utilisateur.

5. Enfin, collez le code utilisateur dans le champ d’entrée qui s’affiche lorsque vous avez exécuté la commande et appuyez sur ENTRÉE pour terminer le processus de connexion.

    ![Image du champ d’entrée du code utilisateur](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>À l’aide du vues font Live de partage

Après avoir installé le partage en direct de Visual Studio, un onglet personnalisé figurera dans la barre d’activités de VS Code. Dans cet onglet, vous pouvez accéder à toutes les fonctions de partage en direct pour collaborer. En outre, lorsque vous partagez ou rejoignez une session de collaboration, une vue apparaîtra également dans l’onglet Explorateur pour pouvoir accéder à toutes ces fonctions.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Avec ces vues, vous pouvez voir l’emplacement d’un participant dans le code partagé, cliquez sur un participant à les suivre, concentrer participants, accéder à des serveurs partagés et les terminaux et bien plus encore.

## <a name="using-the-scoped-command-menu"></a>L’aide du menu de commande étendue

En outre, toutes les fonctions de le Partage Live Visual Studio sont disponibles à partir de Visual Studio Code « Palette de commandes » qui est accessible en appuyant sur Ctrl + Maj + P / Cmd + Maj + P ou sur F1. Vous trouverez une liste complète des commandes en tapant « partage en direct ».

Étant donné que cette liste peut devenir longue, il peut s’avérer plus facile de tirer parti d’un menu de commande étendue disponible à partir de la barre d’état. En cliquant sur la connexion / de l’icône d’état de session dans la barre d’état s’affiche immédiatement une liste contextualisée de commandes qui sont disponibles que vous pouvez utiliser.

![Icône d’état VS Code session](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Partager un projet

Après le téléchargement et installation de partage en direct de Visual Studio, suivez ces étapes pour démarrer une session de collaboration et d’inviter un collègue à travailler avec vous.

1. **Connexion**

    Après avoir installé l’extension de partage en direct, rechargement et attend les dépendances terminer l’installation, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Ouvrir un dossier**

    Utilisez votre flux de travail normal pour ouvrir un dossier, un projet ou une solution que vous aimeriez partager avec vos invités.

3. **[Facultatif] Mettre à jour les fichiers cachés ou exclus**

    Par défaut, Partage Live **masque** les fichiers/dossiers référencés dans les fichiers .gitignore dans vos dossiers partagés d’invités. **Masquage** un fichier empêche d’apparaître dans l’arborescence des fichiers de l’invité. **À l’exclusion** un fichier applique une règle plus stricte qui l’empêche Partage Live de l’ouvrir pour l’invité dans des situations comme accéder à une définition ou si vous parcourez le fichier pendant le débogage, ou « suivi ». Si vous souhaitez masquer/exclure des fichiers différents, un **. vsls.json** fichier peut être ajouté à votre projet avec ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

4. **Démarrer une session de collaboration**

    À présent, simplement **cliquez sur** la barre d’élément ou d’atteinte d’état « Partage » **Ctrl + Maj + P / Cmd + Maj + P** et sélectionnez « partage en direct : Démarrer une session de collaboration (partage) ».

    ![Bouton partager](../media/vscode-share-button.png)

    > [!NOTE]
    > Vous pouvez être invité par votre logiciel de pare-feu de bureau pour permettre à l’agent Partage Live ouvrir un port de la première fois que vous partagez. Accepter ce est entièrement facultative mais permet un « mode direct » sécurisé pour améliorer les performances lorsque la personne que vous utilisez est sur le même réseau que vous êtes. Consultez [modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode) pour plus d’informations.

    Un lien d’invitation est copié automatiquement dans le Presse-papiers. L’ouverture dans un navigateur, ce lien permet d’autres utilisateurs à joindre une nouvelle session de collaboration qui partage le contenu de ces dossiers avec eux.

    Vous verrez également la transition d’élément de barre d’état « Partage » pour représenter l’état de session. Consultez [l’état de session](#session-states) informations ci-dessous pour quoi cela ressemble.

    Notez que si vous avez besoin obtenir le lien d’invitation à nouveau une fois que vous avez démarré le partage, vous y accéder de nouveau en cliquant sur l’icône de barre du statut d’état de session et sélectionnez « Inviter d’autres personnes (copier le lien) ».

5. **[Facultatif] Activer le mode en lecture seule**

    Une fois que vous démarrez votre session de collaboration, vous pouvez définir la session peut être en lecture seule pour empêcher les invités d’apporter des modifications au code partagé.

    Après le partage, vous recevez une notification que le lien d’invitation a été copié dans le Presse-papiers. Vous pouvez ensuite sélectionner l’option pour que la session en lecture seule.

    ![Mode de lecture seule de Code Visual Studio](../media/vscode-read-only-toast.png)

6. **Envoyer le lien**

    Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Notez que, étant donné le niveau d’accès de partage Live sessions peuvent fournir aux invités, **vous devez uniquement partager avec des personnes dignes de confiance** et réflexion via les implications de ce que vous partagez.

    > **Astuce de sécurité :** Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

    Si l’invité que vous avez invité a des questions, le «[Guide de démarrage rapide : Joindre votre première session](../quickstart/join.md)« article fournit des informations supplémentaires sur rendre opérationnel et en cours d’exécution en tant qu’invité.

7. **[Facultatif] Approuver l’invité**

    Par défaut, les invités joint automatiquement votre session de collaboration, et vous serez averti quand ils sont prêts à travailler avec vous. Bien que cette notification vous donne la possibilité pour les supprimer de la session, vous pouvez aussi pour exiger à la place une « approbation » explicite pour toute personne rejoindre.

    Pour activer cette fonctionnalité, ajoutez simplement le code suivant à settings.json :

         "liveshare.guestApprovalRequired": true

    Une fois que vous avez ce paramètre est activé, une notification vous invitera à approuver l’invité avant de pouvoir participer.

    ![Demande d’approbation de jointure Visual Studio Code](../media/vscode-join-approval.png)

    Consultez [invitations et accès de jointure](../reference/security.md#invitations-and-join-access) pour plus d’informations sur les considérations de sécurité d’invitation.

Voilà !!

### <a name="stop-the-collaboration-session"></a>Arrêter la session de collaboration

En tant qu’hôte, vous pouvez arrêter le partage complètement et terminer la session de collaboration à tout moment en ouvrant la vue de partage en direct dans l’Explorateur ou dans l’onglet personnalisé de partage en direct et en sélectionnant l’icône « Arrêter la session de collaboration ».

![Arrêter la session de collaboration](../media/vscode-end-collaboration-viewlet.png)

Tous les invités seront informées que la session est terminée.  Une fois la session s’est terminée, les invités ne seront plus en mesure d’accéder au contenu et tous les fichiers temporaires sont automatiquement nettoyés.

Vous rencontrez des problèmes avec le partage ? Découvrez [dépannage](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Rejoindre une session de collaboration

Après le téléchargement et installation de partage en direct de Visual Studio, invités suffit à prendre de quelques étapes pour rejoindre une session de collaboration hébergée. Il existe deux manières de joindre : [via le navigateur](#join-via-the-browser) et [manuellement](#join-manually).

> **Astuce de sécurité :** En tant qu’invité rejoindre une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou des fonctionnalités. Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités et les paramètres du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

### <a name="join-via-the-browser"></a>Joindre via le navigateur

Rejoindre une session de collaboration, le plus simple consiste à simplement ouvrir le lien d’invitation dans un navigateur web. Voici ce que vous pouvez attendre quand vous suivez ce flux.

1. **Connexion**

    Après avoir installé l’extension de partage en direct, rechargement et attend les dépendances terminer l’installation, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Cliquez sur le lien d’invitation / ouvrir l’invitation dans votre navigateur**

    À présent, ouvrez simplement (ou ouvrez à nouveau) le lien d’invitation dans un navigateur.

    > **Remarque** : Si vous n’avez pas encore installé l’extension de partage en direct, s’affiche avec des liens vers la place de marché d’extension. Installer l’extension et redémarrez votre outil et réessayez.

    Vous devez averti que le navigateur souhaite lancer un outil de partage en direct est activé. Si vous la laissez lancer votre outil sélectionné, vous devez être connecté à la session de collaboration, une fois démarré.

    ![Joindre la page](../media/join-page.png)

    Si l’hôte est hors connexion, vous serez averti à ce stade au lieu de cela. Vous pouvez ensuite contacte l’ordinateur hôte et demandez-lui de le partager à nouveau.

    > [!NOTE]
    > Vérifiez que vous avez **démarrer l’outil au moins une fois** après l’installation de l’extension de le Partage Live Visual Studio et autorisé l’installation se termine avant ouverture/ré-opening la page de l’invitation. Rencontrez encore des problèmes ? Consultez [joindre manuellement des](#join-manually).

3. **Collaborate**

    C’est tout ! Dans quelques instants, vous êtes connecté et vous pouvez commencer à collaborer.

    Vous verrez la transition du bouton « Partage » pour transmettre un « état de Session ». Consultez [l’état de session](#session-states) informations ci-dessous pour quoi cela ressemble.

    Vous allez ensuite automatiquement dirigé vers le fichier de que l’hôte est en train de modifier une fois la jointure est terminée.

### <a name="join-manually"></a>Joindre manuellement

Vous pouvez joindre manuellement sans utiliser un navigateur web qui peut être utile dans les situations où l’outil que vous souhaitez utiliser est déjà en cours d’exécution, vous souhaitez utiliser un autre outil que vous le faites habituellement, ou si vous rencontrez des difficultés avec l’obtention inviter des liens de fonctionner pour une raison quelconque. Le processus est simple :

1. **Connexion**

    Après avoir installé l’extension de partage en direct, rechargement et attend les dépendances terminer l’installation, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Utilisez la commande de jointure**

    Ouvrez l’onglet personnalisé de partage en direct dans la barre d’activités de VS Code, puis sélectionnez la « jointure collaboration session... » icône ou entrée.

    ![Icône de vues font de jointure](../media/vscode-join-viewlet.png)

3. **Collez le lien d’invitation**

    Coller l’URL de l’invitation vous ont été envoyés et appuyez sur ENTRÉE pour confirmer.

4. **Collaborer !**

    C’est tout ! Vous devez être connecté à la session de collaboration momentanément.

    Vous verrez la transition du bouton « Partage » pour transmettre un « état de Session ». Consultez [l’état de session](#session-states) informations ci-dessous pour quoi cela ressemble.

    Vous allez ensuite automatiquement dirigé vers le fichier de que l’hôte est en train de modifier une fois la jointure est terminée.

### <a name="leave-the-collaboration-session"></a>Laissez la session de collaboration

En tant qu’invité, vous pouvez laisser la session de collaboration sans mettre fin pour d’autres en fermant simplement la fenêtre VS Code. Si vous préférez garder la fenêtre ouverte, vous pouvez ouvrir la vue Explorateur de partage en direct ou l’onglet personnalisé Partage Live et sélectionnez l’icône « Laisser une session de collaboration ».

![Icône de feuilles de session](../media/vscode-leave-session-viewlet.png)

Tous les fichiers temporaires sont automatiquement nettoyés, aucune action supplémentaire n’est nécessaire.

Rencontre des problèmes de jointure ? Découvrez [dépannage](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coédition

Une fois qu’un invité a joint une session de collaboration, tous les collaborateurs seront immédiatement être en mesure de voir les modifications et les sélections en temps réel entre eux. Il vous suffit de faire est de choisir un fichier à partir de l’Explorateur de fichiers et de commencer à modifier. Hôtes et invités affiche les modifications que peuvent contribuer eux-mêmes rend facile d’itérer et maîtriser rapidement pour réduire les solutions et faire.

> [!NOTE]
> Rejoindre une session de collaboration en lecture seule empêche les invités d’être en mesure d’apporter des modifications aux fichiers. Un hôte peut [activer le mode lecture seule quand ils partagent](#share-a-project). En tant qu’invité, vous pouvez indiquer si vous avez joint une session en lecture seule en examinant votre [l’état de session](#session-states).

![Capture d’écran affichant la même édition](../media/vscode-coedit.png)

> [!NOTE]
> Même modification présente des limites pour certaines langues. Voir la section [plateforme prise en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

Au-delà des curseurs et les modifications, vos sélections sont également visibles à tous les participants dans ce même fichier. Cela rend facile à mettre en surbrillance où des problèmes peuvent exister ou communiquer des idées.

![Capture d’écran affichant la mise en surbrillance](../media/vscode-highlight.png)

Mieux encore, vous et les autres participants peuvent accéder à n’importe quel fichier dans le projet partagé. Vous pouvez soit modifier l’ensemble ou indépendamment de ce qui signifie que vous pouvez basculer en toute transparence entre l’enquête, ce qui rend petits ajustements et la modification collaborative complète.

La modification qui en résulte est rendues persistantes sur l’ordinateur de l’hôte sur Enregistrer et il n’est pas nécessaire de synchroniser, push ou envoyer des fichiers une fois que vous avez terminé édition. Les modifications sont « juste there ».

> **Astuce de sécurité :** Étant donné tous les participants peuvent indépendamment accéder et modifier des fichiers, en tant qu’hôte, vous pouvez souhaiter limiter les fichiers invités peuvent accéder dans votre projet via un. vsls.json fichier. En tant qu’invité, il est également important de savoir que vous ne voyiez pas certains fichiers à la suite de ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

### <a name="changing-participant-flag-behaviors"></a>Modification des comportements de l’indicateur de participants

Par défaut, le partage en direct de Visual Studio affiche automatiquement un « indicateur » en regard de curseur d’un participant au pointage, ou quand ils le modifiez, mettez en surbrillance, ou déplacez le curseur. Dans certains cas, vous pouvez modifier ce comportement.

Simplement **modifier settings.json** (fichier > Préférences > Paramètres), ajoutez une des lignes suivantes, puis redémarrez VS Code :

| Paramètre | Comportement |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | L’indicateur est visible uniquement lorsque vous pointez sur le curseur. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Il s'agit de la valeur par défaut. L’indicateur est visible au pointage ou si le participant modifie, met en surbrillance, ou déplace le curseur. |
| ``"liveshare.nameTagVisibility":"Always"`` | L’indicateur est toujours visible. |

## <a name="following"></a>Suivant

Il est parfois nécessaire d’expliquer un problème ou une conception qui s’étend sur plusieurs fichiers ou emplacements dans le code. Dans ces situations, il peut être utile de temporairement suivent un collègue lorsqu’ils utilisent tout au long du projet. Pour cette raison, lorsque vous joignez une session de collaboration vous serez automatiquement « suivre » l’hôte. Lorsque vous suivez une personne, votre éditeur resteront synchronisé avec leur position de défilement et de fichier actuellement ouverte.

> [!NOTE]
> Par défaut, les partages de partage en direct les fichiers externes dans le dossier partagé ainsi ouvrent. Si vous souhaitez désactiver cette fonctionnalité, mettez à jour `liveshare.shareExternalFiles` Partage Live à `false` dans settings.json.

Pour commencer à suivre un participant (comme hôte ou invité), cliquez sur son nom dans la liste des participants dans la vue de l’Explorateur de partage en direct ou d’un onglet personnalisé. Le cercle en regard de leur nom remplira pour indiquer que les sont suivies.

![Suivez de VS Code à partir de vues font](../media/vscode-follow-multiple-viewlet.png)

Vous pouvez également cliquer sur l’icône d’épingle dans le coin supérieur droit du groupe de l’éditeur ou appuyez sur **Ctrl + Alt + F / Cmd + Alt + F**.

![Code confidentiel de VS Code](../media/vscode-pin.png)

> [!NOTE]
> Si plus d’une autre personne est dans la session de collaboration, vous allez être invité à sélectionner le participant que vous souhaitez suivre.
>
>![Capture d’écran affichant la liste des collaborateurs](../media/vscode-list-collaborators.png)

Dans la mesure où les éléments suivants est lié à un groupe de l’éditeur, vous pouvez utiliser le mode fractionné (ou mise en page de grille !) pour avoir un groupe qui suit un participant et un groupe qui n’est pas. Cela vous permet à une personne suivre passivement lorsque vous travaillez également sur quelque chose indépendamment. Avec un groupe de l’éditeur sélectionné, vous pouvez sélectionner un participant dans la liste de participants pour que ce groupe les suivre.

![Code confidentiel de Code de Visual Studio en mode fractionné](../media/vscode-follow-split.png)

Pour faciliter l’extraire de « mode de suivi » et commencer à modifier vous-même, vous arrêtez automatiquement suivant si un d'entre eux se produit :

1. Vous commencez à modifier le fichier actif
1. Vous ouvrez un fichier différent
1. Vous fermez le fichier actif

En outre, vous pouvez arrêter explicitement suivant une personne en cliquant de nouveau sur l’icône d’épingle ou les atteignent **Ctrl + Alt + F / Cmd + Alt + F**.

## <a name="listing-participants"></a>Liste des participants

Un moyen rapide de voir qui est dans la session de collaboration consiste à consulter la liste des participants dans la vue de l’Explorateur de partage en direct ou d’un onglet personnalisé. Les vues afficheront tous les participants dans votre session.

![Icône de barre état de capture d’écran montrant l’utilisateur](../media/vscode-explorer-view.png)

En cliquant sur n’importe quel participant dans cette liste suivra dans votre groupe Éditeur actif.

Vous pouvez également appuyer sur **Ctrl + Maj + P / Cmd + Maj + P** et sélectionnez le « partage en direct : Commande list Participants » ou **cliquez sur** sur l’élément de barre d’état qui indique le nombre de participants dans votre session.

![Icône de barre état de capture d’écran montrant l’utilisateur](../media/vscode-user-status.png)

Une liste de tous les participants de la session s’affiche alors. Contrairement à en cliquant sur l’icône d’épingle, cette liste s’affiche même s’il existe uniquement une autre personne dans la session avec vous, afin que vous puissiez voir toujours rapidement où quelqu'un d’autre se trouve. Pour des raisons de commodité, telles que l’icône d’épingle, vous pouvez ensuite choisir un des participants dans la liste les suivre. Si vous souhaitez quitter au lieu de cela, appuyez sur ÉCHAP.

## <a name="focusing"></a>En mettant l’accent

Il peut arriver que vous souhaiterez peut-être tout le monde dans une session de collaboration et examinons quelque chose que vous effectuez. Partage en direct vous permet de demander que tout le monde » nous concentrer » leur attention sur vous avec une notification qui facilite leur permet de vous suivre de nouveau.

Ouvrez l’onglet personnalisé de partage en direct dans la barre d’activités de VS Code ou la vue Explorateur de partage en direct et sélectionnez l’icône « Concentrer participants ».

![Icône de vues font de focus](../media/vscode-focus-viewlet.png)

Une fois que vous exécutez la commande, tous les membres de la session de collaboration puis recevez une notification que vous avez demandé à leur attention.

![Notification toast de focus](../media/vscode-focus-toast.png)

Ils puis suffit de cliquer sur « Suivre » directement à partir de la notification quand ils sont prêts à mettre ses priorités sur vous.

## <a name="co-debugging"></a>Codébogage

Fonctionnalité de débogage collaboratif de Visual Studio Live du partage est un moyen puissant et unique pour déboguer un problème. Au-delà de l’activation de fonctionnalités de collaboration résoudre les problèmes, il également vous et les autres participants dans votre session, la possibilité d’examiner les problèmes qui peuvent être environnement spécifique en fournissant une session de débogage partagée sur l’ordinateur de l’hôte.

> **Astuce de sécurité :** Étant donné tous les participants peuvent indépendamment accéder et modifier des fichiers, en tant qu’hôte, vous pouvez souhaiter limiter les fichiers invités peuvent accéder dans votre projet via un. vsls.json fichier. Vous devez également connaître que les accès Console/REPL signifie que les participants peuvent exécuter des commandes sur votre ordinateur donc vous devez déboguer uniquement conjointement avec des personnes de que confiance. En tant qu’invité, il est également important de savoir que vous n’êtes peut-être pas en mesure de suivre le débogueur comme il parcourt certains fichiers restreint de fichiers à la suite de ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

À l’aide de simple.

1. Veillez à ce que l’hôte et tous les invités ont l’extension de débogage appropriée installée. (Techniquement, cela n’est pas toujours nécessaire, mais il est généralement une bonne idée).

2. En tant que l’ordinateur hôte, si ce n’est pas déjà configuré pour le projet, vous devez [configurer launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) pour déboguer l’application à partir de Visual Studio Code comme vous le feriez normalement. Aucune configuration spéciale n’est requise.

3. Ensuite, l’hôte peut démarrer le débogage à l’aide du bouton dans l’onglet de débogage comme d’habitude.

    ![Bouton de débogage de VS Code](../media/vscode-debug-button.png)

    > [!TIP]
    > Vous pouvez également participer à partir de VS Code et vice versa de sessions de débogage de Visual Studio ! Découvrez le [obtenir des instructions de Visual Studio](vs.md#co-debugging) sur le même emplacement de débogage pour plus d’informations.

Une fois que le débogueur s’attache à côté de l’ordinateur hôte, tous les invités sont également automatiquement attachées. Bien qu’un débogage « session » en cours d’exécution sur l’ordinateur de l’hôte, tous les participants sont connectés et ont leur propre affichage.

![Débogueur de VS Code attaché](../media/vscode-debugger.png)

Tout le monde peut parcourir le processus de débogage qui permet une commutation transparente entre collaborateurs sans avoir à négocier le contrôle.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

Chaque collaborateur peut examiner les différentes variables, accéder à des fichiers différents dans la pile des appels, inspecter des variables et même ajouter ou supprimer des points d’arrêt. Fonctionnalités d’édition hébergé autorise alors chaque participant poête effectuer le suivi dans lequel les autres se trouvent pour fournir la capacité unique à basculer en toute transparence entre simultanément examen des différents aspects du problème et le débogage en collaboration.

> [!NOTE]
> Au cours d’une session de collaboration en lecture seule, un invité ne sera pas en mesure de parcourir le processus de débogage. Ils peuvent toutefois, toujours ajouter ou supprimer des points d’arrêt et inspecter les variables.

![Animation de débogage simultanées](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Quand modifier des jointures de VS Code sessions de débogage

Par défaut, en tant qu’invité, vous allez être automatiquement joint aux sessions quand ils sont partagés par l’hôte de débogage. Toutefois, dans certains cas, vous souhaiterez ce comportement sans interruption. Heureusement, vous pouvez modifier comme suit :

Simplement **modifier settings.json** (fichier > Préférences > Paramètres), ajoutez une des lignes suivantes, puis redémarrez VS Code :

| Paramètre | Comportement |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | Valeur par défaut. En tant qu’invité, vous allez joindre automatiquement tout l’hôte démarre la session de débogage partagée. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | En tant qu’invité, vous êtes invité à indiquer si vous souhaitez rejoindre une session de débogage partagée lorsqu’il est démarré par l’hôte. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | En tant qu’invité, vous devez joindre manuellement des sessions de débogage. Consultez [détachement et rattachement](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Détachement et rattachement

En tant qu’invité, vous pouvez souhaiter arrêter le débogage temporairement. Heureusement, vous pouvez simplement cliquer sur l’icône « Arrêter » dans la barre d’outils de débogage pour détacher le débogueur sans affecter l’hôte ou autres invités.

![Bouton d’arrêt débogueur VS Code](../media/vscode-debug-stop.png)

Si vous avez mis à jour les paramètres afin que vous n’avez plus l’attachement automatique ou si vous souhaitez simplement rattacher ultérieurement, vous pouvez le faire en appuyant sur **Ctrl + Maj + P / Cmd + Maj + P** ou **en cliquant sur** sur l’élément de barre d’état de session état et en sélectionnant « Attacher à un débogage Session partagée ».

![Attacher le débogueur VS Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Partage de l’application en cours d’exécution dans un navigateur

Visual Studio Code n’a pas le concept de « port de l’application web », tels que Visual Studio, pour les types de projet tels que ASP.NET connu. Toutefois, si vous joignez une session de collaboration à partir d’un ordinateur hôte Visual Studio, peuvent automatiquement apparaître votre navigateur par défaut lorsque le débogage commence, qui est ensuite automatiquement connectés aux applications en cours d’exécution de l’hôte. Consultez [les fonctionnalités de Visual Studio](vs.md#automatic-web-app-sharing) pour plus d’informations.

En tant qu’hôte, vous pouvez obtenir quelque chose de similaire en partageant manuellement l’application ou autres points de terminaison tels que les services RESTful à l’aide de la fonctionnalité « Partage le serveur Local ». Visual Studio et Visual Studio Code invités peuvent ensuite ouvrir un navigateur sur le même port localhost pour voir l’application en cours d’exécution.  Consultez [partager un serveur](#share-a-server) pour plus d’informations.

## <a name="share-a-server"></a>Partager un serveur

De temps à autre, comme un hôte de session de collaboration, vous constaterez que vous souhaitez partager une application web ou autre exécuté localement des serveurs ou services avec les invités. Cela peut consister à partir d’autres points de terminaison RESTful pour les bases de données et d’autres serveurs. Visual Studio Live partager vous permet de spécifier un numéro de port local, si vous le souhaitez lui donner un nom, puis le partager avec tous les invités.

Les invités pourront ensuite accéder au serveur que vous avez partagé sur ce port à partir de leur propre ordinateur local sur le même port exact. Par exemple, si vous avez partagé un serveur web **en cours d’exécution sur le port 3000**, l’invité peut accéder à ce même serveur web en cours d’exécution sur leur **propre machine** à http://localhost:3000! Cela est effectué via un tunnel SSH ou SSL sécurisé entre l’hôte et les invités et authentifié via le service afin de vous assurer que seules dans la session de collaboration ont accès.

> **Astuce de sécurité :** En tant qu’hôte, vous devez être très sélective avec les ports que vous partagez avec des invités et respectez les application ports (plutôt qu’un port de système de partage). Pour les invités, des ports partagés seront comportent exactement comme il le ferait si le service/serveur était en cours d’exécution sur leur propre ordinateur. Cela est très utile, mais si le port incorrect est partagé permettre également être à risque.

Pour des raisons de sécurité, seuls les serveurs en cours d’exécution sur les ports que vous spécifiez sont disponibles aux autres invités. Heureusement, il est facile d’ajouter un en tant que la session de collaboration **hôte**. Voici comment :

1. Ouvrez l’onglet personnalisé de partage en direct dans la barre d’activités de VS Code ou la vue Explorateur de partage en direct, puis sélectionnez le « serveur de partage... » entrée ou cliquez sur l’icône.

    ![Serveur local de partage de Code Visual Studio](../media/vscode-share-local-server-viewlet.png)<br />

1. Entrez le numéro de port que le serveur est en cours d’exécution et éventuellement un nom.

    ![Capture d’écran de l’invite de numéro de port](../media/vscode-enter-port.png)<br />

C’est tout ! Le serveur sur le port spécifié est maintenant mappé à localhost de chaque invité sur le même port (à moins que ce port est déjà occupé) !

Si le port est déjà en cours d’utilisation sur l’ordinateur de l’invité, une autre est automatiquement sélectionnée. Heureusement, en tant qu’invité, vous pouvez voir une liste des ports actuellement partagés (par nom si spécifié) dans la vue de l’Explorateur de partage en direct ou d’un onglet personnalisé dans la barre d’activités de VS Code et regardez dans la liste des serveurs partagés. Lorsque vous sélectionnez une entrée, ce serveur s’ouvre dans votre navigateur. Vous pouvez également cliquez droit et sélectionnez l’option pour copier le lien vers le serveur dans le Presse-papiers.

![Serveur local d’accès au Code VS](../media/vscode-access-shared-server-viewlet.png)<br />

Notez que *invités ne peuvent pas* contrôler quels ports sur l’ordinateur de l’hôte sont partagées pour des raisons de sécurité.

Pour **arrêter** partage un serveur local en tant que l’ordinateur hôte, pointez sur l’entrée de serveur dans la liste des serveurs partagés dans l’affichage de l’Explorateur de partage en direct ou d’un onglet personnalisé, puis cliquez sur l’icône « Annuler le partage de serveur ».

![VS Code arrêter le serveur de partage](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Partager un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Partage Live vous permet, en tant qu’hôte, si vous le souhaitez « partager un terminal » avec les invités. Le terminal partagé peut être en lecture seule ou entièrement collaborative afin de vous et les invités peuvent exécuter des commandes et voir les résultats. Vous pouvez donner une visibilité des invités à la sortie de terminal ou de leur permettre d’obtenir des ateliers pratiques et exécuter des tests, builds ou même de triage spécifiques à l’environnement des problèmes qui se produisent uniquement sur votre ordinateur.

Toutefois, les terminaux sont **pas** partagé par défaut dans la mesure où ils donnent aux invités au moins un accès en lecture à la sortie des commandes que vous exécutez (si ce n’est pas la possibilité d’exécuter des commandes eux-mêmes). Cette façon d’exécuter des commandes dans des terminaux locales sans risque et de partager uniquement lorsque librement a réellement besoin de le faire. De plus, seuls les ordinateurs hôtes peuvent démarrer des terminaux partagées pour empêcher les invités à partir d’un démarrage et de faire quelque chose vous ne sont pas attendu ou l’observation des.

En tant qu’hôte, vous pouvez partager un terminal en ouvrant l’onglet personnalisé Partage Live dans la barre d’activités de VS Code ou la vue Explorateur de partager en direct et en sélectionnant le « partage de serveur... » entrée ou en cliquant sur l’icône.

![Terminal de partage de Code de Visual Studio](../media/vscode-share-terminal-viewlet.png)<br />

À ce stade, vous pouvez sélectionner en lecture seule ou lecture/écriture Terminal Server à partir du menu. Lorsque le terminal est en lecture/écriture, tout le monde peut taper dans le terminal, y compris l’hôte, ce qui facilite l’intervenir si un invité fait quelque chose que vous n’aimez pas. Toutefois, pour plus de sécurité, vous devez **donner uniquement un accès en lecture/écriture aux invités lorsque vous savez ils en ont réellement besoin** cap et gardez-le terminaux en lecture seule pour les scénarios où vous voulez juste l’invité pour voir le résultat de toutes les commandes que vous exécutez.

> [!NOTE]
> Si la session de collaboration est en mode lecture seule, terminaux en lecture seule peuvent être partagés par l’hôte.

![En lecture seule ou lecture/écriture sélection](../media/vscode-share-terminal-ro-rw.png)<br />

Une fois que vous avez sélectionné le type de terminal partagé, que vous souhaitez démarrer, un nouveau terminal partagé s’affiche sous l’onglet de terminaux de VS Code.

![Partagé Terminal Server en cours d’exécution](../media/vscode-share-terminal-up.png)<br />

Si plusieurs terminaux sont partagés, ou si le focus se trouve dans un autre onglet, vous pouvez donner le focus à un terminal spécifique en sélectionnant l’entrée dans la liste des terminaux partagé.

![Terminal Server partagé donner le focus](../media/vscode-shared-terminal-focus.png)<br />

Pour mettre fin à votre session de terminal, tapez simplement la sortie, fermez la fenêtre de terminal ou cliquez sur l’icône « Annuler le partage Terminal Server » dans la vue Explorateur de partage en direct ou onglet personnalisé et tout le monde va être déconnectée.

## <a name="session-states"></a>États de session

Une fois que vous avez démarré ou rejoint la session de collaboration et ont accès au contenu partagé, la mise à jour des éléments de la barre d’état le Partage Live Visual Studio leur apparence pour refléter l’état de la session de collaboration active.

Les États que vous verrez généralement sont les suivantes :

| État | Barre d'état | Description |
|-------|--------------------|-------------|
| inactif | ![État du Code VS : inactif](../media/vscode-status-share.png) | Aucune session de collaboration active et que rien n’est partagé. |
| Hôte : Partage en cours d’exécution | ![État du Code VS : partager en cours](../media/vscode-status-sharing.png)| Démarrage d’une session de collaboration et partage de contenu va bientôt commencer. |
| Hôte : Contrat de partage | ![État du Code VS : partage active ](../media/vscode-status-active.png)| Une session de collaboration est active et le contenu est partagé. |
| Hôte : Partage en lecture seule | ![État du Code VS : partage en lecture seule](../media/vscode-status-sharing-read-only.png)| Partage d’une session de collaboration en lecture seule. |
| Invités : Rejoindre la Session | ![État du Code VS : jointure](../media/vscode-status-joining.png)| Rejoindre une session de collaboration existant. |
| Invités : Joint | ![État du Code VS : joint](../media/vscode-status-active.png) | Joint et connecté à une session de collaboration active et la réception de contenu partagé. |
| Invités : Joint en lecture seule | ![État du Code VS : jointe en lecture seule](../media/vscode-status-joined-read-only.png) | Joint et connecté à une session active collaboration en lecture seule. |

## <a name="guest-limitations"></a>Limitations des invités

Bien qu’il existe actuellement des défauts invités seront confrontés lors de l’utilisation des fonctionnalités décrites ci-dessus, les hôtes de session de collaboration conservent une fonctionnalité complète de l’outil de leur choix. Pour plus d’informations, consultez :

- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
- [Tous les bogues majeurs, demandes de fonctionnalités et limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)
- [Résolution des problèmes](../troubleshooting.md)

## <a name="next-steps"></a>Étapes suivantes

Consultez ces articles supplémentaires pour plus d’informations.

- [Démarrage rapide : Partager votre premier projet](../quickstart/share.md)
- [Démarrage rapide : Joindre votre première session](../quickstart/share.md)
- [Comment : Collaborer à l’aide de Visual Studio](vs.md)
- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Détails de l’installation Linux](../reference/linux.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
