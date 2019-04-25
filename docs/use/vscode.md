---
title: Travailler en collaboration à l’aide de Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Une série de guides pratiques de collaboration pour Visual Studio Code et Live Share.
ms.custom: ''
ms.date: 04/27/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: ed96ba572a58b8d3bfda7b634f1052a1b4e73051
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58853636"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio-code"></a>Guide pratique : Collaborer à l’aide de Visual Studio Code

Prêt à travailler en collaboration à l’aide de Live Share dans VS Code ?  Dans ce cas, vous êtes au bon endroit ! Cet article explique comment utiliser certaines des fonctionnalités propres de l’extension Visual Studio Live Share pour Visual Studio Code.

Sachez que toutes les activités de collaboration décrites ici impliquent un seul **hôte de session de collaboration** et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

*Vous recherchez une synthèse ? Consultez plutôt les guides de démarrage rapide [Partager](../quickstart/share.md) et [Rejoindre](../quickstart/join.md).*

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

## <a name="installation"></a>Installation

Avant de commencer, vous devez vous assurer que la version installée de Visual Studio Code est conforme aux exigences principales de Live Share. Vous avez besoin de **Visual Studio Code (1.22.0 ou une version ultérieure)** exécuté sous :

- **Windows** : 7, 8.1 ou 10

- **macOS** : Sierra (10.12) et versions ultérieures uniquement.
    - _El Capitan (10.11) et les versions antérieures ne sont actuellement pas pris en charge en raison de la [configuration requise de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872315)._

- **Linux** : Ubuntu Desktop 64 bits à partir de la version 16.04, Fedora Workstation à partir de la version 27, CentOS 7

    - Live Share requiert un certain nombre de [composants requis de Linux](#linux-install-steps) que vous pouvez être invité à installer.
    - _Linux 32 bits n’est pas pris en charge en raison de la [configuration requise de .NET Core 2.0](https://go.microsoft.com/fwlink/?linkid=872314)._
    - ARM n'est actuellement pas pris en charge.
    - Consultez l’article [Détails d’installation de Linux](../reference/linux.md) pour en savoir plus sur les distributions en aval et autres.

Ensuite, le téléchargement et l’installation de l’extension Visual Studio Live Share sont un jeu d’enfant :

1. Installez <a href="https://code.visualstudio.com/">Visual Studio Code</a>
2. [ Téléchargez](https://aka.ms/vsls-dl/vscode) et installez l’extension Visual Studio Live Share à partir du Marketplace.
3. Rechargez Visual Studio Code
4. Attendez que les dépendances soient téléchargées et installées (voir la barre d’état).<br/>
    ![Fin de l’installation](../media/vscode-finishing-install.png)
5. **Linux** : Si vous voyez une notification concernant l’installation de bibliothèques manquantes :
    1. Cliquez sur « Installer » dans la notification.
    2. Entrez votre mot de passe d’administrateur (sudo) lorsque vous y êtes invité.
    3. Redémarrez VS Code lorsque vous avez terminé.

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

[![Télécharger](../media/download.png)](https://aka.ms/vsls-dl/vscode)

### <a name="linux-install-steps"></a>Étapes d’installation pour Linux

Linux est un environnement très variable et le grand nombre d’environnements de bureau et de distributions peut compliquer le travail. Si vous vous en tenez aux versions prises en charge d’**Ubuntu Desktop** (à partir de la version 16.04), de **Fedora Workstation** (à partir de la version 27) ou de **CentOS 7** et utilisez uniquement des **distributions officielles de VS Code**, vous devriez trouver le processus simple. Toutefois, si vous utilisez une configuration non standard ou une distribution en aval, il n’est pas exclu que vous rencontriez des difficultés. Consultez [Détails d’installation de Linux](../reference/linux.md) pour plus d’informations.

#### <a name="install-linux-prerequisites"></a>Installer les composants requis pour Linux

Certaines distributions de Linux n’ont pas de bibliothèques dont Live Share a besoin pour fonctionner. Par défaut, Live Share tente de détecter et d’installer les composants requis pour Linux pour vous. Lorsque Live Share rencontre un problème pouvant être dû à des bibliothèques manquantes, vous voyez une notification toast qui vous demande l’autorisation de les installer.

![Notification toast montrant le message relatif aux composants requis manquants de Linux](../media/vscode-linux-prereq-missing.png)

Lorsque vous cliquez sur « Installer », une fenêtre de terminal s’affiche, dans laquelle vous devrez entrer votre mot de passe d’administrateur (sudo) pour continuer. Une fois l’installation terminée, redémarrez Visual Studio Code. Tout devrait être prêt ! Vous souhaitez également peut-être consulter **[Conseils par distribution](../reference/linux.md#tips-by-distribution)** pour voir d’autres conseils et des solutions de contournement s’il y en a.

Si vous voyez un message indiquant que le script ne prend pas en charge votre distribution, consultez **[Conseils pour les distributions de la communauté prises en charge](../reference/linux.md#tips-for-community-supported-distros)** pour lire les informations que la communauté a partagées avec nous.

Si vous **préférez que VS Code n’exécute pas la commande pour vous**, vous pouvez également choisir de réexécuter la toute dernière version de ce script manuellement à tout moment en exécutant la commande suivante à partir d’une fenêtre de terminal :

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

#### <a name="linux-browser-integration"></a>Intégration du navigateur Linux

Généralement, Visual Studio Live Share **ne nécessite pas d’étapes d’installation supplémentaires** pour activer l’intégration d’un navigateur sur Linux.

Même si ce n’est pas courant, certaines distributions **peuvent vous informer que votre mot de passe d’administrateur (sudo) est nécessaire** pour terminer le processus d’installation. Une fenêtre de terminal vous indiquant où le lanceur du navigateur sera installé s’affiche. Entrez simplement votre mot de passe lorsque vous y êtes invité et appuyez sur Entrée une fois l’installation terminée pour fermer la fenêtre de terminal.

Vous pouvez en apprendre plus sur la raison pour laquelle cela est nécessaire et sur l’endroit où Live Share place fichiers  **[ici](../reference/linux.md#linux-browser-integration)**. Notez que même si vous n’arrivez pas à faire fonctionner l’intégration du navigateur, vous pouvez toujours **[rejoindre les sessions de collaboration manuellement](../use/vscode.md#join-manually)**.

## <a name="sign-in"></a>Se connecter

Pour pouvoir collaborer, vous devez vous connecter à Visual Studio Live Share afin que tout le monde sache qui vous êtes. Cette simple mesure de sécurité ne vaut **pas** consentement à des actions marketing ou à d’autres activités de recherche. Vous pouvez utiliser un compte personnel Microsoft (par exemple, @outlook.com), un compte professionnel ou scolaire soutenu par Microsoft (AAD) ou un compte GitHub. Il est facile de se connecter.

**Cliquez** sur l’élément « Live Share » de la barre élément, ou appuyez sur **Ctrl+Maj+P/Cmd+Maj+ P** et sélectionnez la commande : « Live Share : se connecter avec le navigateur ».

![Bouton de connexion de VS Code](../media/vscode-sign-in-button.png)

Une notification vous demandant de vous connecter à l’aide de votre navigateur web s’affiche. En cliquant sur « lancer la connexion », vous ouvrez un navigateur à utiliser pour terminer le processus de connexion. Fermez le navigateur lorsque vous avez terminé.

![Notification toast demandant de se connecter à l’aide d’un navigateur Web](../media/vscode-sign-in-toast.png)

> **Utilisateurs Linux :** Vous pouvez être invité à entrer un code utilisateur si vous utilisez une version antérieure de Live Share (v0.3.295 ou postérieure). Mettez à jour vers la dernière version de l’extension ou cliquez sur le lien « Vous rencontrez des problèmes ? » après vous être connecté pour afficher le code. Consultez [ce qui suit pour plus d'informations](#sign-in-using-a-user-code).

Si Visual Studio Code ne reprend pas vos informations d’identification lorsque vous avez terminé le processus de connexion dans le navigateur, consultez [Connexion avec un code utilisateur](#sign-in-using-a-user-code). Vous pouvez également consulter la page [Résolution des problèmes](../troubleshooting.md#sign-in) pour plus de conseils.

### <a name="sign-in-using-a-user-code"></a>Connectez-vous à l’aide d’un code utilisateur

Si vous rencontrez des problèmes parce que VS Code ne reprend pas des informations d’identification renseignées, vous pouvez entrer un « code utilisateur » à la place.

1. Appuyez sur **Ctrl+Maj+P/Cmd+Maj+ P** et exécutez la commande « Live Share : se connecter avec un code utilisateur ».

2. Un navigateur doit apparaître pour vous permettre de terminer le processus de connexion.

    > [!NOTE]
    > Si un navigateur n’apparaît pas automatiquement, ouvrez [cet emplacement](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login) dans un navigateur et connectez-vous.

3. Quand vous avez terminé, cliquez sur « Vous rencontrez des problèmes ? Cliquez ici pour recevoir des instructions pour le code utilisateur » afin d’afficher le code utilisateur.

    ![Image du code utilisateur dans le navigateur](../media/vscode-user-code-browser.png)

4. Copiez le code utilisateur.

5. Enfin, collez le code utilisateur dans le champ d’entrée qui s’affiche lorsque vous avez exécuté la commande et appuyez sur Entrée pour terminer le processus de connexion.

    ![Image du champ d'entrée du code utilisateur](../media/vscode-user-code.png)

## <a name="using-the-live-share-viewlet"></a>Utilisation de la viewlet Live Share

Après l’installation de Visual Studio Live Share, un onglet personnalisé est ajouté à la barre d’activité de VS Code. Dans cet onglet, vous pouvez accéder à toutes les fonctions de Live Share pour collaborer. De plus, lorsque vous partagez ou rejoignez une session de collaboration, une vue apparaît également dans l’onglet Explorateur pour que vous puissiez également accéder à toutes ces fonctions.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-custom-tab.png" width="100%" alt="Live Share custom tab" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-explorer-view.png" width="100%" alt="Live Share explorer view"
</tr>
</table>

Ces vues vous permettent de voir l’emplacement d’un participant dans le code partagé, de cliquer sur un participant pour le suivre, de vous concentrer sur des participants, d’accéder à des serveurs et terminaux partagé, et bien plus encore.

## <a name="using-the-scoped-command-menu"></a>Utilisation du menu de commande étendue

De plus, toutes les fonctions de Visual Studio Live Share sont disponibles à partir de la « Palette de commandes » de Visual Studio Code, qui est accessible en appuyant sur Ctrl+Maj+P/Cmd+Maj+P ou sur F1. Vous pouvez trouver une liste complète des commandes en tapant « live share ».

Étant donné que cette liste peut être longue, vous trouverez peut-être plus simple d’utiliser le menu de commande étendue disponible à partir de la barre d’état. En cliquant sur l'icône de connexion/d’état de la session dans la barre d'état, vous obtiendrez immédiatement une liste contextualisée des commandes que vous pouvez utiliser.

![Icône d’état de la session VS Code](../media/vscode-share-state.png)

## <a name="share-a-project"></a>Partager un projet

Après avoir téléchargé et installé Visual Studio Live Share, suivez ces étapes pour lancer une session de collaboration et inviter un collègue à travailler avec vous.

1. **Se connecter**

    Une fois l’extension Live Share installée, après avoir rechargé et attendu la fin de l’installation des dépendances, vous devrez vous connecter pour vous identifier auprès des autres collaborateurs. Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Ouvrir un dossier**

    Suivez votre flux de travail habituel pour ouvrir le dossier, le projet ou la solution que vous souhaitez partager avec vos invités.

3. **[Facultatif] Mettre à jour des fichiers masqués ou exclus**

    Par défaut, Live Share **masque** tous les fichiers/dossiers référencés dans les fichiers .gitignore dans vos dossiers partagés. **Masquer** un fichier l’empêche d’apparaître dans l’arborescence des fichiers de l’invité. **L’exclusion** d’un fichier applique une règle plus stricte qui empêche Live Share de l’ouvrir pour l’invité dans des situations comme « Accéder à une définition », ou si vous parcourez le fichier pendant le débogage ou le « suivi ». Si vous souhaitez masquer/exclure plusieurs fichiers, un fichier **.vsls.json** peut être ajouté à votre projet avec ces paramètres. Consultez [Contrôler l’accès au fichier et la visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

4. **Démarrer une session de collaboration**

    Maintenant, il suffit de **cliquer** sur l’élément « Live Share » de la barre d’état ou d’appuyer sur **Ctrl+Maj+P/Cmd+Maj+P** et de sélectionner « Live Share : démarrer une session de collaboration (Share) ».

    ![Partager le bouton](../media/vscode-share-button.png)

    > [!NOTE]
    > Vous pouvez être invité par votre logiciel de pare-feu de bureau à autoriser l’agent Live Share à ouvrir un port lors du premier partage. Cette autorisation est entièrement facultative mais permet à un « mode direct » sécurisé d’améliorer les performances lorsque la personne avec laquelle vous travaillez se trouve sur le même réseau que vous. Pour plus d’informations, voir [Modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode).

    Un lien d’invitation est automatiquement copié dans votre Presse-papiers. Une fois ouvert dans un navigateur, il permet à d’autres utilisateurs de rejoindre une nouvelle session de collaboration qui partage le contenu de ces dossiers avec eux.

    Vous voyez également l’élément de barre d’état « Live Share » changer pour représenter l’état de session. Pour savoir à quoi cela ressemble, consultez les informations [État de session](#session-states) ci-dessous.

    Notez que pour accéder à nouveau au lien d'invitation après avoir commencé le partage, il suffit de cliquer sur l'icône de la barre d'état de la session et de sélectionner « Inviter d’autres personnes (Copier le lien) ».

5. **[Facultatif] Activer le mode lecture seule**

    Une fois la session de collaboration démarrée, vous pouvez configurer la session afin qu’elle soit en mode lecture seule, pour empêcher les invités d’apporter des modifications au code partagé.

    Après le partage, vous recevez une notification vous informant que le lien d’invitation a été copié dans le Presse-papiers. Vous pouvez ensuite sélectionner l’option pour que la session soit en lecture seule.

    ![Mode Lecture seule de VS Code](../media/vscode-read-only-toast.png)

6. **Envoyer le lien**

    Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Étant donné le niveau d’accès que les sessions Live Share peuvent offrir aux invités, **limitez les partages aux personnes de confiance** et pensez aux implications de ce que vous partagez.

    > **Conseil en sécurité :** Vous voulez comprendre les implications de sécurité de certaines fonctionnalités Live Share ? Consultez l’article [Sécurité](../reference/security.md).

    Si un invité a des questions, l’article « [Guide de démarrage rapide : Rejoindre votre première session](../quickstart/join.md) » fournit des informations supplémentaires sur la position d’invité.

7. **[Facultatif] Approuver l’invité**

    Par défaut, les invités rejoignent automatiquement la session de collaboration ; lorsqu’ils sont prêts à travailler avec vous, vous recevez une notification. qui vous offre la possibilité de les supprimer de la session. Cependant, vous pouvez exiger plutôt une « approbation » explicite pour chacun.

    Pour activer cette fonctionnalité, ajoutez simplement le code suivant à settings.json :

         "liveshare.guestApprovalRequired": true

    Lorsque ce paramètre est activé, une notification vous demande d’approuver chaque invité qui tente de rejoindre votre session.

    ![Demande d’approbation d’un invité Visual Studio Code](../media/vscode-join-approval.png)

    Pour plus d’informations sur la sécurité des invitations, voir [Invitations et accès aux sessions](../reference/security.md#invitations-and-join-access).

C'est tout !

### <a name="stop-the-collaboration-session"></a>Arrêter la session de collaboration

En tant qu’hôte, vous pouvez complètement arrêter le partage terminer la session de collaboration à tout moment en ouvrant la vue Live Share dans l’Explorateur ou dans l’onglet personnalisé Live Share et en sélectionnant l’icône « Arrêter la session de collaboration ».

![Arrêter la session de collaboration](../media/vscode-end-collaboration-viewlet.png)

Tous les invités reçoivent une notification les informant que la session est terminée.  Ils ne pourront plus accéder au contenu ; tous les fichiers temporaires sont automatiquement nettoyés.

En cas de problème de partage, voir [Résolution des problèmes](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Rejoindre une session de collaboration

Une fois Visual Studio Live Share téléchargé et installé, les invités peuvent rejoindre une session de collaboration hébergée en quelques étapes seulement. Deux solutions s’offrent à eux : [par le navigateur](#join-via-the-browser) et [manuellement](#join-manually).

> **Conseil de sécurité :** En tant qu’invité rejoignant une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou fonctionnalités. Vous voulez comprendre les implications de sécurité de certains paramètres et fonctionnalités Live Share ? Consultez l’article [Sécurité](../reference/security.md).

### <a name="join-via-the-browser"></a>Accès par le navigateur

Pour rejoindre une session de collaboration, le plus simple est d’ouvrir le lien d’invitation dans un navigateur web. Voici ce qui se passe alors.

1. **Se connecter**

    Une fois l’extension Live Share installée, après avoir rechargé et attendu la fin de l’installation des dépendances, vous devrez vous connecter pour vous identifier auprès des autres collaborateurs. Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Cliquer sur le lien d’invitation/ouvrir l’invitation dans le navigateur**

    À présent, ouvrez simplement (ou rouvrez) le lien d’invitation dans un navigateur.

    > **Remarque** : Si vous n’avez pas encore installé l’extension Live Share, des liens vers la Place de marché des extensions apparaîtront. Installez l’extension, redémarrez votre outil et réessayez.

    Vous devriez être averti que le navigateur souhaite lancer un outil Live Share activé. Si vous le laissez lancer l’outil sélectionné, vous serez connecté à la session de collaboration lors du démarrage.

    ![Page Rejoindre](../media/join-page.png)

    Si l’hôte est hors connexion, vous serez averti à ce moment-là. Vous pourrez ensuite contacter l’hôte et lui demander de partager à nouveau.

    > [!NOTE]
    > Vérifiez que vous avez **démarré l’outil au moins une fois** après l’installation de l’extension Visual Studio Live Share et laissé l’installation se terminer avant l’ouverture/la réouverture de la page d’invitation. Le problème persiste ? Consultez la section [Accès manuel](#join-manually).

3. **Collaborez**

    C’est tout ! Dans quelques instants, vous serez connecté et vous pourrez commencer à collaborer.

    Le bouton « Live Share » changera pour indiquer un « État de session ». Pour savoir à quoi cela ressemble, consultez les informations [État de session](#session-states) ci-dessous.

    Vous accédez alors automatiquement au fichier en cours de modification par l’hôte.

### <a name="join-manually"></a>Accès manuel

Vous pouvez également opter pour un accès manuel sans navigateur web, ce qui peut être utile dans différentes situations : l’outil que vous souhaitez utiliser est déjà en cours d’exécution, vous voulez recourir à un autre outil que d’habitude ou vous avez du mal à faire fonctionner les liens d’invitation. La procédure est simple :

1. **Se connecter**

    Une fois l’extension Live Share installée, après avoir rechargé et attendu la fin de l’installation des dépendances, vous devrez vous connecter pour vous identifier auprès des autres collaborateurs. Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Utiliser la commande d’accès**

    Ouvrez l’onglet personnalisé Live Share dans la barre d’activités de VS Code, puis sélectionnez l’icône et l’entrée « Accéder à la session de collaboration... ».

    ![Icône de la viewlet d’accès](../media/vscode-join-viewlet.png)

3. **Coller le lien d’invitation**

    Collez l’URL de l’invitation que vous avez reçue et tapez sur Entrée pour confirmer.

4. **Collaborez !**

    C’est tout ! Vous avez momentanément accès à la session de collaboration.

    Le bouton « Live Share » changera pour indiquer un « État de session ». Pour savoir à quoi cela ressemble, consultez les informations [État de session](#session-states) ci-dessous.

    Vous accédez alors automatiquement au fichier en cours de modification par l’hôte.

### <a name="leave-the-collaboration-session"></a>Quitter la session de collaboration

En tant qu’invité, vous pouvez quitter la session de collaboration sans y mettre fin pour d’autres en fermant simplement la fenêtre VS Code. Si vous préférez garder la fenêtre ouverte, vous pouvez ouvrir la vue de l’Explorateur Live Share ou l’onglet personnalisé Live Share et sélectionner l’icône « Quitter une session de collaboration ».

![Icône Quitter la session](../media/vscode-leave-session-viewlet.png)

Tous les fichiers temporaires étant automatiquement nettoyés, aucune action supplémentaire n’est nécessaire.

En cas de problème d’accès, voir [Résolution des problèmes](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coédition

Une fois qu’ils ont rejoint une session de collaboration, tous les collaborateurs voient immédiatement et en temps réel les modifications et les sélections des autres. Il vous suffit de choisir un fichier dans l’explorateur de fichiers et de l’éditer. Tant les hôtes que les invités voient vos modifications au fur et à mesure et peuvent y contribuer eux-mêmes, ce qui facilite les itérations et permet trouver rapidement des solutions concrètes.

> [!NOTE]
> Dans les sessions de collaboration en lecture seule, les invités ne peuvent pas apporter de modifications aux fichiers. L’hôte a la possibilité [d’activer le mode lecture seule lors du partage](#share-a-project). Pour savoir, en tant qu’invité, si vous avez rejoint une session en lecture seule, examinez votre [État de session](#session-states).

![Capture d’écran du travail en mode collaboratif](../media/vscode-coedit.png)

> [!NOTE]
> Le travail en mode collaboratif présente quelques limitations pour certains langages. Voir la section [plateforme prise en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

De même que les curseurs et les modifications, les sélections effectuées dans le fichier sont visibles par tous les participants, ce qui permet de surligner les endroits posant un problème ou de communiquer des idées.

![Capture d’écran du surlignement](../media/vscode-highlight.png)

Mieux encore, tous les participants peuvent accéder à chacun des fichiers du projet partagé. Vous pouvez les modifier ensemble ou indépendamment, et ainsi passer en toute simplicité de l’examen à de petits ajustements ou à des modifications totalement collaboratives.

Comme les modifications effectuées sont conservées sur l’ordinateur de l’hôte lors de l’enregistrement, il n’est pas nécessaire de synchroniser, de transmettre ou d’envoyer les fichiers une fois la modification terminée. Les modifications sont déjà prises en compte.

> **Conseil de sécurité :** étant donné que tous les participants peuvent accéder aux fichiers et les modifier de manière indépendante, vous pouvez, en tant qu’hôte, limiter les fichiers accessibles dans votre projet au moyen d’un fichier vsls.json. Les invités doivent bien comprendre que ces paramètres sont susceptibles de les empêcher de voir certains fichiers. Consultez [Contrôler l’accès au fichier et la visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

### <a name="changing-participant-flag-behaviors"></a>Modification du comportement de l’indicateur des participants

Par défaut, Visual Studio Live Share affiche automatiquement un « indicateur » à côté du curseur d’un participant au passage de la souris et lors de la modification et du surlignement. Dans certains cas, vous pouvez préférer modifier ce comportement.

Il suffit de **modifier settings.json** (Fichier > Préférences > Paramètres), d’ajouter une des lignes suivantes, puis de redémarrer VS Code :

| Paramètre | Comportement |
|---------|----------|
| ``"liveshare.nameTagVisibility":"Never"`` | L’indicateur n’est visible qu’au passage du curseur. |
| ``"liveshare.nameTagVisibility":"Activity"`` | Il s'agit de la valeur par défaut. L’indicateur est visible au passage du curseur ou si le participant effectue des modifications, surligne ou déplace son curseur. |
| ``"liveshare.nameTagVisibility":"Always"`` | L’indicateur est toujours visible. |

## <a name="following"></a>Suivant

Il est parfois nécessaire d’expliquer un problème ou une conception qui s’étend sur plusieurs fichiers ou emplacements dans le code. Dans ce cas, il peut être utile de suivre temporairement un collègue tandis qu’il parcourt le projet. Pour cette raison, lorsque vous rejoignez une session de collaboration, vous « suivez » automatiquement l’hôte. Lorsque vous suivez quelqu’un, votre éditeur reste synchronisé avec le fichier ouvert, le curseur et la position de défilement de ce participant.

> [!NOTE]
> Par défaut, Live Share partage également les fichiers ouverts extérieurs au dossier partagé. Si vous souhaitez désactiver cette fonctionnalité, mettez à jour `liveshare.shareExternalFiles` Live Share sur `false` dans settings.json.

Pour commencer à suivre un participant (comme hôte ou comme invité), cliquez sur son nom dans la liste des participants dans la vue de l’Explorateur Live Share ou dans l’onglet personnalisé. Le cercle en regard de son nom est rempli pour indiquer que vous le suivez.

![Suivre VS Code à partir d’une viewlet](../media/vscode-follow-multiple-viewlet.png)

Vous pouvez également cliquer sur l’icône en forme d’épingle en haut à droite du groupe de l’éditeur ou appuyer sur **Ctrl+Alt+F/Cmd+Alt+F**.

![Épingle VS Code](../media/vscode-pin.png)

> [!NOTE]
> Si plusieurs personnes participent à la session de collaboration, vous êtes invité à sélectionner le participant que vous souhaitez suivre.
>
>![Capture d’écran affichant la liste des collaborateurs](../media/vscode-list-collaborators.png)

Dans la mesure où le fait de suivre est lié à un groupe de l’éditeur, vous pouvez utiliser un mode fractionné (ou une disposition en grille !) pour avoir un groupe qui suit un participant et un groupe qui ne le fait pas. Ceci vous permet de suivre passivement quelqu’un tout en travaillant également sur quelque chose de manière indépendante. Lorsqu’un groupe d’éditeurs est sélectionné, vous pouvez choisir un participant dans la liste des participants pour que ce groupe le suive.

![Épingle VS Code en mode fractionné](../media/vscode-follow-split.png)

Pour faciliter la désactivation du « mode suivre « et commencer à apporter vous-même des modifications, le suivi s’arrête automatiquement dans l’un des cas suivants :

1. Vous commencez à modifier le fichier actif
1. Vous ouvrez un autre fichier
1. Vous fermez le fichier actif

Vous pouvez par ailleurs arrêter explicitement de suivre quelqu’un en cliquant sur l’icône d’épingle ou en tapant **Ctrl+Alt+F/Cmd+Alt+F**.

## <a name="listing-participants"></a>Liste des participants

Un moyen rapide de voir qui participe à la session de collaboration consiste à consulter la liste des participants dans la vue de l’Explorateur Live Share ou dans un onglet personnalisé. Les vues affichent tous les participants à votre session.

![Capture d’écran montrant l’icône de la barre d’état de l’utilisateur](../media/vscode-explorer-view.png)

Vous suivrez un participant de cette liste en cliquant dessus dans votre groupe d’éditeurs actif.

Vous pouvez également appuyer sur **Ctrl+Maj+P/Cmd+Maj+P** et sélectionner la commande « Live Share : faire une liste des participants », ou **cliquer** sur l’élément de barre d’état qui indique le nombre de participants à votre session.

![Capture d’écran montrant l’icône de la barre d’état de l’utilisateur](../media/vscode-user-status.png)

Une liste de tous les participants à la session s’affiche alors. Contrairement à ce qui est le cas lorsque vous cliquez sur l’icône d’épingle, cette liste s’affiche même s’il n’y a qu’une autre personne dans la session avec vous, afin que vous puissiez toujours voir rapidement où se trouve quelqu'un d’autre. Pour des raisons de commodité, telles que l’icône d’épingle, vous pouvez ensuite choisir un des participants dans la liste et le suivre. Appuyez sur ÉCHAP. pour quitter.

## <a name="focusing"></a>Effectuer un focus

Il est parfois utile de pouvoir inviter tous les participants d’une session de collaboration à examiner un point particulier. Live Share vous offre la possibilité de demander à tout le monde de faire un « focus » sur vous en envoyant une notification facilitant le suivi.

Ouvrez l’onglet personnalisé Live Share dans la barre d’activités de VS Code ou la vue de l’Explorateur Live Share, puis sélectionnez l’icône « Effectuer un focus sur les participants ».

![Icône de focus sur la viewlet](../media/vscode-focus-viewlet.png)

Une fois que vous exécutez la commande, tous les membres de la session de collaboration reçoivent alors une notification indiquant que vous réclamez leur attention.

![Notifications toast Focus](../media/vscode-focus-toast.png)

Il leur suffit de cliquer sur « Suivre » dans la notification pour placer le focus sur vous.

## <a name="co-debugging"></a>Codébogage

La fonctionnalité de débogage collaboratif de Visual Studio Live Share est un moyen puissant et unique de déboguer un problème. Au-delà de l’expérience collaborative de dépannage, elle offre également à vous et à tous les participants de la session la possibilité d’examiner des problèmes potentiellement propres à l’environnement en proposant une session de débogage partagée sur l’ordinateur de l’hôte.

> **Conseil de sécurité :** étant donné que tous les participants peuvent accéder aux fichiers et les modifier de manière indépendante, vous pouvez, en tant qu’hôte, limiter les fichiers accessibles dans votre projet au moyen d’un fichier vsls.json. Sachez également que l’accès Console/REPL permet aux participants d’exécuter des commandes sur votre ordinateur ; de ce fait, limitez le débogage collaboratif aux personnes de confiance. Les invités doivent aussi bien comprendre qu’ils ne pourront pas forcément suivre le débogueur s’il entre dans des fichiers restreints par ces paramètres. Consultez [Contrôler l’accès au fichier et la visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

Son utilisation est très simple.

1. Veillez à ce que l’hôte et tous les invités aient l’extension de débogage appropriée installée. (Techniquement, ça n’est pas toujours nécessaire, mais c’est généralement une bonne idée.)

2. En tant qu’hôte, si ça n’est pas encore configuré pour le projet, vous devez [configurer launch.json](https://code.visualstudio.com/Docs/editor/debugging#_launch-configurations) pour déboguer l’application à partir de VS Code comme vous le feriez normalement. Aucune configuration spéciale n’est requise.

3. Ensuite, l’hôte peut démarrer le débogage à l’aide du bouton dans l’onglet de débogage comme d’habitude.

    ![Bouton de débogage de VS Code](../media/vscode-debug-button.png)

    > [!TIP]
    > Vous pouvez également participer aux sessions de débogage de Visual Studio à partir de VS Code et vice versa ! Pour plus d’informations sur le débogage collaboratif, voir les [Instructions de Visual Studio](vs.md#co-debugging).

Une fois le débogueur attaché du côté de l’hôte, tous les invités sont également attachés automatiquement. Bien qu’il n’y ait qu’une seule « session » de débogage en cours d’exécution sur l’ordinateur de l’hôte, tous les participants y sont connectés et la visualisent.

![Débogueur de VS Code attaché](../media/vscode-debugger.png)

Comme tout le monde peut suivre le processus de débogage, il est facile de passer la main d’un collaborateur à l’autre sans avoir à négocier le contrôle.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

Chaque collaborateur peut examiner différentes variables, accéder à différents fichiers dans la pile des appels et même ajouter ou supprimer des points d’arrêt. Grâce aux fonctionnalités de travail en mode collaboratif, il a alors la possibilité de savoir où se trouvent les autres, ce qui permet d’inspecter simultanément différents aspects du problème et de rendre le débogage collaboratif.

> [!NOTE]
> Dans une session de collaboration en lecture seule, les invités ne peuvent pas parcourir le processus de débogage. Ils ont toutefois la possibilité d’ajouter ou de supprimer des points d’arrêt et d’inspecter les variables.

![Animation du débogage simultané](../media/co-debug.gif)

### <a name="change-when-vs-code-joins-debugging-sessions"></a>Changement lorsque VS Code rejoint des sessions de débogage

Par défaut, les invités sont automatiquement attachés aux sessions de débogage partagées par l’hôte. Toutefois, ce comportement peut être gênant dans certains cas. Pour le modifier :

Il suffit de **modifier settings.json** (Fichier > Préférences > Paramètres), d’ajouter une des lignes suivantes, puis de redémarrer VS Code :

| Paramètre | Comportement |
|---------|----------|
|``"liveshare.joinDebugSessionOption":"Automatic"`` | Valeur par défaut. Les invités rejoignent automatiquement toute session de débogage partagée lancée par l’hôte. |
| ``"liveshare.joinDebugSessionOption":"Prompt"`` | Il est demandé aux invités s’ils souhaitent rejoindre la session de débogage partagée lorsqu’elle est lancée par l’hôte. |
| ``"liveshare.joinDebugSessionOption":"Manual"`` | Les invités doivent pouvoir rejoindre manuellement les sessions de débogage. Voir [Détacher et rattacher](#detaching-and-reattaching). |

### <a name="detaching-and-reattaching"></a>Détacher et rattacher

Pour arrêter temporairement le débogage en tant qu’invité en détachant le débogueur sans affecter l’hôte et les autres invités, il suffit de cliquer sur l’icône « Arrêter » dans la barre d’outils de débogage.

![Bouton d’arrêt du débogueur de VS Code](../media/vscode-debug-stop.png)

Si vous avez mis à jour les paramètres afin de ne plus attacher automatiquement ou si vous souhaitez simplement rattacher ultérieurement, vous pouvez le faire en appuyant sur **Ctrl+Shift+P/Cmd+Shift+P**, ou **en cliquant** sur l’élément de barre d’état de session et en sélectionnant « Attacher à une session de débogage partagée ».

![Débogueur d’attachement de VS Code](../media/vscode-reattach.png)

### <a name="sharing-the-running-application-in-a-browser"></a>Partage de l’application en cours d’exécution dans un navigateur

Visual Studio Code n’a pas le concept d’un « port d’application web » connu, tel que Visual Studio, pour les types de projet tels que ASP.NET. Toutefois, si vous rejoignez une session de collaboration à partir d’un hôte Visual Studio, il se peut que votre navigateur par défaut apparaisse automatiquement lorsque le débogage commence et qu’il soit ensuite automatiquement connecté aux applications en cours d’exécution de l’hôte. Consultez [Fonctionnalités de Visual Studio](vs.md#automatic-web-app-sharing) pour plus d’informations.

En tant qu’hôte, vous pouvez obtenir quelque chose de similaire en partageant manuellement l’application ou d’autres points de terminaison tels que les services RESTful à l’aide de la fonctionnalité « Partager un serveur local ». Les invités de Visual Studio et de VS Code peuvent ensuite ouvrir un navigateur sur le même port localhost pour voir l’application en cours d’exécution.  Consultez [Partager un serveur](#share-a-server) pour plus d’informations.

## <a name="share-a-server"></a>Partager un serveur

De temps en temps, il peut être utile à un hôte de session de collaboration de pouvoir partager avec les invités une application web ou des serveurs ou services exécutés localement. Cela peut aller d’autres points de terminaison RESTful à des bases de données et à d’autres serveurs. Visual Studio Live Share offre la possibilité de spécifier un numéro de port local, de lui donner un nom (facultatif), puis de le partager avec tous les invités.

Les invités pourront alors accéder au serveur partagé sur ce même port, avec leur propre ordinateur local. Par exemple, si vous avez partagé un serveur web **qui s’exécute sur le port 3000**, l’invité peut y accéder sur son **propre ordinateur** à l’emplacement http://localhost:3000 ! La connexion est établie via un tunnel SSH ou SSL sécurisé entre l’hôte et les invités, et authentifiée via le service, ce qui garantit que seuls les participants de la session de collaboration y ont accès.

> **Conseil de sécurité :** en tant qu’hôte, choisissez soigneusement les ports que vous partagez avec les invités et tenez-vous-en aux ports d’application (par opposition aux ports système). Du côté des invités, les ports partagés se comportent exactement comme si le serveur/service était en cours d’exécution sur leur propre ordinateur. Cette fonction est très utile, mais il faut éviter tout risque de partager le mauvais port.

Pour des raisons de sécurité, seuls les serveurs qui s’exécutent sur les ports spécifiés sont accessibles aux autres invités. Heureusement, il est facile pour un **hôte** de session de collaboration d’en ajouter un. Voici comment :

1. Ouvrez l’onglet personnalisé Live Share dans la barre d’activités de VS Code ou la vue de l’Explorateur Live Share, puis sélectionnez l’entrée « Partager un serveur... », ou cliquez sur l’icône.

    ![Serveur local de partage de VS Code](../media/vscode-share-local-server-viewlet.png)<br />

1. Entrez le numéro de port que le serveur est en train d’exécuter et, éventuellement, un nom.

    ![Capture d’écran de l’invite à entrer un numéro de port](../media/vscode-enter-port.png)<br />

C’est tout ! Le serveur sur le port spécifié est alors mappé au localhost de chaque invité sur le même port (sauf si ce port est déjà occupé) !

Si le port est déjà utilisé sur l’ordinateur de l’invité, un autre est automatiquement sélectionné. Heureusement, en tant qu’invité, vous pouvez voir une liste des ports actuellement partagés (par nom si spécifié) dans la vue de l’Explorateur Live Share ou dans l’onglet personnalisé dans la barre d’activités de VS Code et consulter la liste des serveurs partagés. Lorsque vous sélectionnez une entrée, ce serveur s’ouvre dans votre navigateur. Vous pouvez également cliquer avec le bouton droit et sélectionner l’option pour copier le lien vers le serveur dans le Presse-papiers.

![Serveur local d’accès à Code VS](../media/vscode-access-shared-server-viewlet.png)<br />

Sachez que, pour des raisons de sécurité, les *invités ne peuvent pas* contrôler les ports partagés sur l’ordinateur de l’hôte.

Pour **arrêter** de partager un serveur local en tant qu’hôte, passez avec la souris sur l’entrée du serveur dans la liste des serveurs partagés dans la vue de l’Explorateur Live Share ou dans l’onglet personnalisé, puis cliquez sur l’icône « Annuler le partage de serveur ».

![Arrêt de partage de serveur VS Code](../media/vscode-stop-sharing-server-viewlet.png)<br />

## <a name="share-a-terminal"></a>Partager un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Live Share permet aux hôtes, s’ils le souhaitent, de « partager un terminal » avec les invités. Le terminal partagé peut fonctionner en lecture seule ou en collaboration totale, auquel cas tant l’hôte que les invités ont la possibilité d’exécuter des commandes et de voir les résultats. Vous pouvez offrir aux invités une visibilité sur la sortie de terminal ou les laisser exécuter des tests, des builds ou même catégoriser des problèmes propres à l’environnement de votre ordinateur.

Cependant, les terminaux ne sont **pas** partagés par défaut, dans la mesure où cela donnerait aux invités au moins un accès en lecture seule à la sortie des commandes exécutées (voire la possibilité d’exécuter des commandes eux-mêmes). Vous pouvez ainsi exécuter sans risque des commandes dans les terminaux locaux, en les partageant si nécessaire. Par ailleurs, seuls les hôtes (et non les invités) peuvent lancer des terminaux partagés, ce qui évite toute action inattendue ou inaperçue.

En tant qu’hôte, vous pouvez partager un terminal en ouvrant l’onglet personnalisé Live Share dans la barre d’activités de VS Code ou la vue de l’Explorateur Live Share, en sélectionnant l’entrée « Partager un serveur... », ou en cliquant sur l’icône.

![Terminal de partage de VS Code](../media/vscode-share-terminal-viewlet.png)<br />

Vous pouvez alors sélectionner un terminal en lecture seule ou en lecture/écriture dans le menu. Dans le deuxième cas, tout le monde, y compris l’hôte, peut taper dans le terminal, ce qui permet d’intervenir si un invité effectue une action indésirable. Dans un souci de sécurité toutefois, **ne donnez un accès en lecture/écriture qu’aux invités qui en ont réellement besoin** et tenez-vous-en aux terminaux en lecture seule si vous souhaitez simplement qu’ils voient le résultat des commandes exécutées.

> [!NOTE]
> Si la session de collaboration est en mode lecture seule, l’hôte ne peut partager les terminaux qu’en lecture seule.

![Sélection en lecture seule ou en lecture/écriture](../media/vscode-share-terminal-ro-rw.png)<br />

Une fois le type de terminal partagé sélectionné, un nouveau terminal partagé apparaît sous l’onglet des terminaux de VS Code.

![Exécution d’un terminal partagé](../media/vscode-share-terminal-up.png)<br />

Si plusieurs terminaux sont partagés, ou si votre focus se trouve dans un autre onglet, vous pouvez effectuer un focus sur un terminal spécifique en sélectionnant l’entrée dans la liste des terminaux partagés.

![Un terminal partagé permet de mettre en focus](../media/vscode-shared-terminal-focus.png)<br />

Pour terminer votre session de terminal, tapez simplement quitter, fermez la fenêtre du ou cliquez sur l’icône « Annuler le partage du terminal » dans la vue de l’Explorateur Live Share ou dans l’onglet personnalisé. Tout le monde sera déconnecté.

## <a name="session-states"></a>États de session

Lorsque vous lancez ou rejoignez une session de collaboration et que vous avez accès au contenu partagé, les éléments de la barre d’état Live Share se mettent à jour pour refléter l’état de la session de collaboration active.

Voici les états les plus courants :

| État | Barre d'état | Description |
|-------|--------------------|-------------|
| Inactif | ![État de VS Code : inactif](../media/vscode-status-share.png) | Aucune session de collaboration active ; pas de partage. |
| Hôte : Partage en cours | ![État de VS Code : partage en cours](../media/vscode-status-sharing.png)| Session de collaboration en cours de lancement, en attente du partage de contenu. |
| Hôte : Contrat de partage | ![État de VS Code : partage actif ](../media/vscode-status-active.png)| Session de collaboration active et partage de contenu. |
| Hôte : Partage en lecture seule | ![État de VS Code : partage en lecture seule](../media/vscode-status-sharing-read-only.png)| Partage d’une session de collaboration en lecture seule. |
| Invité : Accès en cours à la session | ![État de Visual Studio Code : accès en cours](../media/vscode-status-joining.png)| Accès en cours à une session de collaboration. |
| Invité : Accès réussi | ![État de VS Code : accès réussi](../media/vscode-status-active.png) | Accès et connexion réussis à une session de collaboration active ; réception de contenu partagé en cours. |
| Invité : Accès en lecture seule | ![État de VS Code : accès en lecture seule](../media/vscode-status-joined-read-only.png) | Accès et connexion réussis à une session de collaboration active en lecture seule. |

## <a name="guest-limitations"></a>Limitations portant sur les invités

Tandis que les invités risquent encore de rencontrer quelques défauts dans les fonctionnalités décrites ci-dessus, les hôtes de session de collaboration conservent toutes les fonctions de l’outil choisi. Pour plus d’informations, consultez :

- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)
- [Résolution des problèmes](../troubleshooting.md)

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations, voir ces articles complémentaires.

- [Démarrage rapide : Partager un projet](../quickstart/share.md)
- [Démarrage rapide : Rejoindre une session](../quickstart/share.md)
- [Guide pratique : Collaborer à l’aide de Visual Studio](vs.md)
- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Détails de l’installation de Linux](../reference/linux.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
