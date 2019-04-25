---
title: Travailler en collaboration à l’aide de Visual Studio – Visual Studio Live Share | Microsoft Docs
description: Une série de guides pratiques de collaboration pour Visual Studio et Live Share.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 55eb4b0a5e819b00754d75e4682dd1aa97bbf576
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58853623"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Guide pratique : Travailler en collaboration à l’aide de Visual Studio

Vous voulez travailler en collaboration à l’aide de Live Share dans Visual Studio ? Dans ce cas, vous êtes au bon endroit ! Ct article explique comment utiliser certaines des fonctionnalités propres de l’extension Visual Studio Live Share pour Visual Studio.

Sachez que toutes les activités de collaboration décrites ici impliquent un seul **hôte de session de collaboration** et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

*Vous recherchez une synthèse ? Consultez plutôt les guides de démarrage rapide [Partager](../quickstart/share.md) et [Rejoindre](../quickstart/join.md).*

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

## <a name="installation"></a>Installation

Avant de commencer, il faut installer **Visual Studio 2019** ou **Visual Studio 2017 15.6 ou version ultérieure** sur Windows 7, 8.1 ou 10. *Toutefois, une version au moins égale à Visual Studio 15.7 est recommandée pour prendre en charge les annulations/restaurations locales.*

La procédure est simple :

Pour Visual Studio 2019
1. Installez une édition de [Visual Studio 2019](https://visualstudio.microsoft.com/vs/).
2. Installez une [charge de travail prise en charge](../reference/platform-support.md). (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)
3. Visual Studio Live Share est installé par défaut avec ces charges de travail.

Pour Visual Studio 2017
1. Installez une édition de [Visual Studio 2017](https://visualstudio.microsoft.com/vs/older-downloads/) au moins égale à la version 15.6.
2. Installez une [charge de travail prise en charge](../reference/platform-support.md). (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)
3. [Téléchargez](https://aka.ms/vsls-dl/vs) et installez l’extension Visual Studio Live Share sur la marketplace.

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

[![Télécharger](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Se connecter

Pour pouvoir travailler en collaboration, vous devez vous connecter à Visual Studio Live Share ; ainsi, tout le monde saura qui vous êtes. Cette simple mesure de sécurité ne vaut **pas** consentement à des actions marketing ou autres activités de recherche. Vous pouvez utiliser un compte personnel Microsoft (par exemple, @outlook.com), un compte professionnel ou scolaire soutenu par Microsoft (AAD) ou un compte GitHub. Il est facile de se connecter.

Par défaut, Visual Studio utilise votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) ; si vous avez déjà ouvert une session dans Visual Studio, vous pourrez peut-être ignorer cette étape. Sinon, connectez-vous normalement.

![Bouton de connexion de Visual Studio](../media/vs-sign-in-button.png)

Si vous souhaitez utiliser d’autres informations d’identification que votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) Visual Studio, accédez à **Outils &gt; Options &gt; Live Share &gt; Compte d’utilisateur** pour effectuer la modification.

![Options Visual Studio Tools Live Share](../media/vs-tools-options.png)

**Compte externe** permet de sélectionner un compte non pris en charge par la fonctionnalité de personnalisation de Visual Studio, comme GitHub. Un navigateur s’affiche automatiquement la première fois que vous utilisez une fonctionnalité Live Share pour vous permettre de vous connecter.

En cas de problème, voir [Résolution des problèmes](../troubleshooting.md#sign-in) pour obtenir des conseils.

## <a name="share-a-project"></a>Partager un projet

Après avoir téléchargé et installé Visual Studio Live Share, suivez ces étapes pour lancer une session de collaboration et inviter un collègue à travailler avec vous.

1. **Se connecter**

    Après avoir installé l’extension Live Share, connectez-vous pour indiquer qui vous êtes aux autres collaborateurs. Par défaut, Visual Studio utilise votre compte de personnalisation ; de ce fait, vous pourrez peut-être ignorer totalement cette étape.

    Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Ouvrir une solution, un projet ou un dossier**

    Suivez votre workflow habituel pour ouvrir le dossier, le projet ou la solution que vous souhaitez partager avec vos invités.

3. **[Facultatif] Mettre à jour des fichiers masqués ou exclus**

    Par défaut, Live Share **masque** aux invités tous les fichiers/dossiers auxquels font référence les fichiers .gitignore du projet. Un fichier **masqué** n’apparaît pas dans l’arborescence des fichiers, tandis qu’un fichier **exclu** n’est jamais transmis, même pendant des opérations comme le débogage. Pour masquer/exclure différents fichiers, ajoutez à votre projet un fichier **.vsls.json** comportant ces paramètres. Consultez [Contrôler l’accès au fichier et la visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

4. **Démarrer une session de collaboration**

    Maintenant, cliquez simplement sur le bouton « Live Share » en haut à droite.

    ![Bouton Partager de Visual Studio](../media/vs-share-button.png)

    > [!NOTE]
    > Votre logiciel de pare-feu de bureau pourra vous demander d’autoriser l’agent Live Share à ouvrir un port lors du premier partage. Cette autorisation est entièrement facultative mais permet à un « mode direct » sécurisé d’améliorer les performances lorsque la personne avec laquelle vous travaillez se trouve sur le même réseau que vous. Pour plus d’informations, voir [Modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode).

    Un lien d’invitation est automatiquement copié dans votre Presse-papiers. Une fois ouvert dans un navigateur, il permet à d’autres utilisateurs de rejoindre une nouvelle session de collaboration qui partage le contenu de ces dossiers avec eux.

    Le bouton « Live Share » change également pour indiquer un « État de session ». Pour savoir comment il se présente, voir les informations [État de session](#session-states) ci-dessous.

    Sachez que, pour accéder à nouveau au lien d’invitation après avoir commencé le partage, vous pouvez cliquer sur le bouton Partager/État de session et sélectionner « Copier le lien ».

5. **[Facultatif] Activer le mode lecture seule**

    Une fois la session de collaboration démarrée, vous pouvez configurer la session afin qu’elle soit en mode lecture seule, pour empêcher les invités d’apporter des modifications au code partagé.

    Après le partage, vous recevez une notification vous informant que le lien d’invitation a été copié dans le Presse-papiers. Vous pourrez alors sélectionner l’option permettant de passer la session en lecture seule.

    ![Mode Lecture seule de Visual Studio](../media/vs-read-only-notification.png)

6. **Envoyer le lien**

    Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Étant donné le niveau d’accès que les sessions Live Share peuvent offrir aux invités, **limitez les partages aux personnes de confiance** et pensez aux implications de ce que vous partagez.

    > **Conseil en sécurité :** Vous voulez comprendre les implications de sécurité de certaines fonctionnalités Live Share ? Consultez l’article [Sécurité](../reference/security.md).

    Si un invité a des questions, l’article « [Guide de démarrage rapide : Rejoindre votre première session](../quickstart/join.md) » fournit des informations supplémentaires sur la position d’invité.

7. **[Facultatif] Approuver l’invité**

    Par défaut, les invités rejoignent automatiquement la session de collaboration ; lorsqu’ils sont prêts à travailler avec vous, vous recevez une notification qui vous offre la possibilité de les supprimer de la session. Cependant, vous pouvez exiger plutôt une « approbation » explicite pour chacun.

    Il suffit de définir **Outils > Options > Live Share > Exiger l’approbation des invités** sur Oui pour activer la fonctionnalité. Lorsque ce paramètre est activé, une notification vous demande d’approuver chaque invité qui tente de rejoindre votre session.

    ![Demande d’approbation d’un invité Visual Studio](../media/vs-join-approval.png)

    Pour plus d’informations sur la sécurité des invitations, voir [Invitations et accès aux sessions](../reference/security.md#invitations-and-join-access).

C'est tout !

### <a name="ending-the-collaboration-session"></a>Mettre fin à la session de collaboration

En tant qu’hôte, vous pouvez arrêter complètement le partage et mettre fin à la session de collaboration en cliquant sur le bouton Partager/État de session (en haut à droite) et en sélectionnant « Mettre fin à la session de collaboration ».

![Arrêter le partage](../media/vs-stop-sharing.png)

Tous les invités recevront une notification les informant que la session est terminée. Ils ne pourront plus accéder au contenu ; tous les fichiers temporaires sont automatiquement nettoyés.

En cas de problème de partage, voir [Résolution des problèmes](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Rejoindre une session de collaboration

Une fois Visual Studio Live Share téléchargé et installé, les invités peuvent rejoindre une session de collaboration hébergée en seulement deux ou trois étapes. Deux solutions s’offrent à eux : [par le navigateur](#join-via-the-browser) et [manuellement](#join-manually).

> **Conseil de sécurité :** En tant qu’invité rejoignant une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou fonctionnalités. Vous voulez comprendre les implications de sécurité de certains paramètres et fonctionnalités Live Share ? Consultez l’article [Sécurité](../reference/security.md).

### <a name="join-via-the-browser"></a>Accès par le navigateur

Pour rejoindre une session de collaboration, le plus simple est d’ouvrir le lien d’invitation dans un navigateur web. Voici ce qui se passe alors.

1. **Se connecter**

    Après avoir installé l’extension Live Share, connectez-vous pour indiquer qui vous êtes aux autres collaborateurs. Par défaut, Visual Studio utilise votre compte de personnalisation ; de ce fait, vous pourrez peut-être ignorer totalement cette étape.

    Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Cliquer sur le lien d’invitation/ouvrir l’invitation dans le navigateur**

    À présent, ouvrez simplement (ou rouvrez) le lien d’invitation dans un navigateur.

    > **Remarque** : Si vous n’avez pas encore installé l’extension Live Share, des liens vers la Place de marché des extensions apparaîtront. Installez l’extension, redémarrez votre outil et réessayez.

    Vous devriez être averti que le navigateur souhaite lancer un outil Live Share activé. Si vous le laissez lancer l’outil sélectionné, vous serez connecté à la session de collaboration lors du démarrage.

    ![Page Rejoindre](../media/join-page.png)

    Si l’hôte est hors connexion, vous serez averti à ce moment-là. Vous pourrez alors le contacter et lui demander de relancer le partage.

    > [!NOTE]
    > Si le problème persiste, Consultez la section [Accès manuel](#join-manually).

3. **Travailler en collaboration**

    C'est tout ! Dans quelques instants, vous serez connecté et vous pourrez commencer à collaborer.

    Le bouton « Live Share » changera pour indiquer un « État de session ». Pour savoir à quoi cela ressemble, consultez les informations [État de session](#session-states) ci-dessous.

    Vous accédez alors automatiquement au fichier en cours de modification par l’hôte.

### <a name="join-manually"></a>Accès manuel

Vous pouvez également opter pour un accès manuel sans navigateur web, ce qui peut être utile dans différentes situations : l’outil que vous souhaitez utiliser est déjà en cours d’exécution, vous voulez recourir à un autre outil que d’habitude ou vous avez du mal à faire fonctionner les liens d’invitation. La procédure est simple :

1. **Se connecter**

    Après avoir installé l’extension Live Share, connectez-vous pour indiquer qui vous êtes aux autres collaborateurs. Par défaut, Visual Studio utilise votre compte de personnalisation ; de ce fait, vous pourrez peut-être ignorer totalement cette étape.

    Pour plus d'informations, voir [Se connecter](#sign-in).

2. **Utiliser la commande d’accès**

    Accédez à **Fichier > Rejoindre la session Live Share**

    ![Menu Rejoindre de Visual Studio](../media/vs-join.png)

3. **Coller le lien d’invitation**

    Collez l’URL de l’invitation que vous avez reçue et confirmez.

4. **Travailler en collaboration**

    C’est tout ! Vous avez momentanément accès à la session de collaboration.

    Le bouton « Live Share » changera pour indiquer un « État de session ». Pour savoir à quoi cela ressemble, consultez les informations [État de session](#session-states) ci-dessous.

    Vous accéderez automatiquement au document en cours de modification par l’hôte.

### <a name="leave-the-collaboration-session"></a>Quitter la session de collaboration

Les invités peuvent quitter la session de collaboration sans y mettre fin pour les autres en fermant simplement l’outil, ou en cliquant sur le bouton Partager/État de session et en sélectionnant « Quitter la session de collaboration ».

![Menu Rejoindre de Visual Studio](../media/vs-leave-session.png)

Tous les fichiers temporaires étant automatiquement nettoyés, aucune action supplémentaire n’est nécessaire.

En cas de problème d’accès, voir [Résolution des problèmes](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coédition

Une fois qu’ils ont rejoint une session de collaboration, tous les collaborateurs voient immédiatement et en temps réel les modifications et les sélections des autres. Il vous suffit de choisir un fichier dans l’Explorateur de fichiers et de l’éditer. Tant les hôtes que les invités voient vos modifications au fur et à mesure et peuvent y contribuer eux-mêmes, ce qui facilite les itérations et permet trouver rapidement des solutions concrètes.

> [!NOTE]
> Dans les sessions de collaboration en lecture seule, les invités ne peuvent pas apporter de modifications aux fichiers. L’hôte a la possibilité [d’activer le mode lecture seule lors du partage](#share-a-project). Pour savoir, en tant qu’invité, si vous avez rejoint une session en lecture seule, examinez votre [État de session](#session-states).

![Capture d’écran du travail en mode collaboratif](../media/vs-coedit.png)

> [!NOTE]
> Le travail en mode collaboratif présente quelques limitations pour certains langages. Voir la section [plateforme prise en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

De même que les curseurs et les modifications, les sélections effectuées dans le fichier sont visibles par tous les participants, ce qui permet de surligner les endroits posant un problème ou de communiquer des idées.

![Capture d’écran du surlignement](../media/vs-highlight.png)

Mieux encore, tous les participants peuvent accéder à chacun des fichiers du projet partagé. Vous pouvez les modifier ensemble ou indépendamment, et ainsi passer en toute simplicité de l’examen à de petits ajustements ou à une édition totalement collaborative.

> [!NOTE]
> Par défaut, Live Share partage également les fichiers ouverts extérieurs à la solution partagée. Si vous souhaitez désactiver cette fonctionnalité, définissez Partager les fichiers externes dans Outils &gt; Options &gt; Live Share sur Non.

Comme les modifications effectuées sont conservées sur l’ordinateur de l’hôte à l’enregistrement, il n’est pas nécessaire de synchroniser, de transmettre ou d’envoyer les fichiers une fois l’édition terminée. Les modifications sont déjà prises en compte.

> **Conseil de sécurité :** étant donné que tous les participants peuvent accéder aux fichiers et les modifier de manière indépendante, vous pouvez, en tant qu’hôte, limiter les fichiers accessibles dans votre projet au moyen d’un fichier vsls.json. Les invités doivent bien comprendre que ces paramètres sont susceptibles de les empêcher de voir certains fichiers. Consultez [Contrôler l’accès au fichier et la visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

### <a name="changing-participant-flag-behaviors"></a>Modification du comportement de l’indicateur des participants

Par défaut, Visual Studio Live Share affiche automatiquement un « indicateur » à côté du curseur d’un participant au passage de la souris et lors de l’édition et du surlignement. Il est possible de modifier ce comportement. Pour ce faire :

1. Accédez à **Outils > Options > Live Share**.
2. Modifiez l’option **Visibilité de l’indicateur** :

| Option | Comportement |
|--------|----------|
| OnHoverOnly | L’indicateur n’est visible qu’au passage du curseur. |
| OnHoverOrActivity | Il s'agit de la valeur par défaut. L’indicateur est visible au passage du curseur et lors de l’édition et du surlignement. |
| Always | L’indicateur est toujours visible.

## <a name="following"></a>Suivre

Dans une session de collaboration, les initiales de chacun des participants apparaissent en haut à droite de l’éditeur, à côté du bouton de connexion. Survolez-les pour afficher les informations complètes du participant.

![Capture d’écran montrant l’utilisateur](../media/vs-person.png)

Il est parfois nécessaire d’expliquer un problème ou une conception qui couvre plusieurs fichiers ou emplacements dans le code. Dans ce cas, il peut être utile de suivre temporairement un collègue tandis qu’il parcourt le projet. C’est pourquoi les invités qui rejoignent une session de collaboration « suivent » automatiquement l’hôte. Leur éditeur reste alors synchronisé avec le fichier ouvert, le curseur et la position de défilement de ce participant.

> [!NOTE]
> Par défaut, Live Share partage également les fichiers ouverts extérieurs à la solution partagée. Si vous souhaitez désactiver cette fonctionnalité, définissez Partager les fichiers externes dans Outils &gt; Options &gt; Live Share sur Non.

Le « mode suivi » s’arrête pour laisser place à l’édition individuelle dans les situations suivantes :

1. Modification, déplacement du curseur ou sélection.
2. Sélection d’un autre fichier.

Vous pouvez également arrêter le suivi à tout moment en cliquant sur les initiales de la personne suivie en haut à droite. Le cercle qui les entoure, indiquant que vous suivez ce participant, disparaît alors.

![Participant de Visual Studio suivi](../media/vs-pinned.png) ![Participant de Visual Studio non suivi](../media/vs-pin-hover.png)

À cet endroit, vous pouvez cliquer sur les initiales d’un hôte ou d’un invité pour le suivre dans la session de collaboration. Sachez que, pour accéder à l’emplacement de quelqu'un sans pour autant le suivre, il suffit de double-cliquer sur ses initiales.

## <a name="focusing"></a>Effectuer un focus

Il est parfois utile de pouvoir inviter tous les participants d’une session de collaboration à examiner un point particulier. Live Share vous offre la possibilité de demander à tout le monde de faire un « focus » sur vous en envoyant une notification facilitant le suivi.

Cliquez sur le bouton Partager/État de session en haut à droite et sélectionnez « Focus des participants ».

![Option de menu Focus](../media/vs-focus.png)

Tous les membres de la session de collaboration reçoivent alors une notification indiquant que vous réclamez leur attention.

![Notifications toast Focus](../media/vs-focus-toast.png)

Il leur suffit de cliquer sur « Suivre » dans la notification pour placer le focus sur vous.

## <a name="co-debugging"></a>Codébogage

La fonctionnalité de débogage collaboratif de Visual Studio Live Share est un moyen puissant et unique de déboguer un problème. Au-delà de l’expérience collaborative de dépannage, elle offre également à tous les participants de la session la possibilité d’examiner des problèmes potentiellement propres à l’environnement en proposant une session de débogage partagée sur l’ordinateur de l’hôte.

> **Conseil de sécurité :** étant donné que tous les participants peuvent accéder aux fichiers et les modifier de manière indépendante, vous pouvez, en tant qu’hôte, limiter les fichiers accessibles dans votre projet au moyen d’un fichier vsls.json. Sachez également que l’accès Console/REPL permet aux participants d’exécuter des commandes sur votre ordinateur ; de ce fait, limitez le débogage collaboratif aux personnes de confiance. Les invités doivent aussi bien comprendre qu’ils ne pourront pas forcément suivre le débogueur s’il effectue un pas à pas détaillé dans des fichiers restreints par ces paramètres. Pour plus d’informations, voir [Contrôler l’accès aux fichiers et leur visibilité](../reference/security.md#controlling-file-access-and-visibility).

La procédure est simple. Il suffit à l’hôte de session de collaboration de lancer le débogage comme d’habitude dans Visual Studio.

![Bouton Déboguer de Visual Studio](../media/vs-debug-button.png)

Une fois le débogueur attaché du côté de l’hôte, tous les invités sont également attachés automatiquement. Bien qu’il n’y ait qu’une seule « session » de débogage en cours d’exécution sur l’ordinateur de l’hôte, tous les participants y sont connectés et la visualisent.

> [!TIP]
> Pour modifier les comportements par défaut du débogage collaboratif, utilisez les paramètres qui se trouvent dans **Outils > Options > Live Share**.

![Débogueur de Visual Studio attaché](../media/vs-debugger.png)

Comme tout le monde peut suivre le processus de débogage, il est facile de passer la main d’un collaborateur à l’autre sans avoir à négocier le contrôle.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

Chaque collaborateur peut examiner différentes variables, accéder à différents fichiers dans la pile des appels et même ajouter ou supprimer des points d’arrêt. Grâce aux fonctionnalités de travail en mode collaboratif, il a alors la possibilité de savoir où se trouvent les autres, ce qui permet d’inspecter simultanément différents aspects du problème et de rendre le débogage collaboratif.

> [!NOTE]
> Dans une session de collaboration en lecture seule, les invités ne peuvent pas parcourir le processus de débogage. Ils ont toutefois la possibilité d’ajouter ou de supprimer des points d’arrêt et d’inspecter les variables.

> [!TIP]
> Vous pouvez également participer aux sessions de débogage de Visual Studio Code dans Visual Studio et vice versa ! Pour plus d’informations sur le débogage collaboratif, voir les [Instructions de Visual Studio](vscode.md#co-debugging).

### <a name="automatic-web-app-sharing"></a>Partage automatique d’application web

Mieux encore, dans les projets d’application web ASP.NET, si par défaut le projet de l’hôte est configuré de manière à lancer automatiquement un navigateur web pour se connecter à l’application web en cours d’exécution lors du débogage, Live Share fait de même sur l’ordinateur de chaque invité ! Cette opération est sécurisée, et l’application web à distance n’est par défaut accessible aux invités que pendant la session de débogage.

Pour plus d’informations sur le partage de l’accès au serveur pour d’autres types de projets ou pendant toute la durée de la session, voir [Partager un serveur](#share-a-server).

> [!TIP]
> Si le comportement de partage automatique du navigateur ne vous convient pas et que vous souhaitez le modifier, vous pouvez mettre à jour les paramètres dans **Outils > Options > Live Share**.

![Animation du débogage simultané](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Modifier le comportement d’accès aux sessions de débogage de Visual Studio

Par défaut, les invités sont automatiquement attachés aux sessions de débogage partagées par l’hôte. Toutefois, ce comportement peut être gênant dans certains cas. Pour le modifier :

1. Accédez à **Outils > Options > Live Share**.
2. Modifiez l’option **Rejoindre la session de débogage** :

| Option | Comportement |
|--------|----------|
| Automatique | Valeur par défaut. Les invités rejoignent automatiquement toute session de débogage partagée lancée par l’hôte. |
| Invite | Il est demandé aux invités s’ils souhaitent rejoindre la session de débogage partagée lorsqu’elle est lancée par l’hôte. |
| Manuel | Les invités doivent rejoindre manuellement les sessions de débogage. Voir [Détacher et rattacher](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Détacher et rattacher

Pour arrêter temporairement le débogage en tant qu’invité en détachant le débogueur sans affecter l’hôte et les autres invités, il suffit de cliquer sur l’icône « Arrêter » dans la barre d’outils de débogage.

Si vous avez mis à jour les paramètres de façon à empêcher l’attachement automatique ou que vous souhaitez simplement effectuer le rattachement par la suite, il vous suffit de sélectionner la session de débogage en cours d’exécution souhaitée dans le menu déroulant « Sélectionner l’élément de démarrage »…

![Bouton Déboguer de Visual Studio](../media/vs-select-reattach.png)

… puis de cliquer dessus pour l’attacher.

![Bouton Déboguer de Visual Studio](../media/vs-reattach.png)

## <a name="share-a-server"></a>Partager un serveur

De temps en temps, il peut être utile à un hôte de session de collaboration de pouvoir partager avec les invités des services ou des serveurs locaux supplémentaires : autres points de terminaison RESTful, bases de données, autres serveurs, etc. Visual Studio Live Share offre la possibilité de spécifier un numéro de port local, de lui donner un nom (facultatif), puis de le partager avec tous les invités.

Les invités pourront alors accéder au serveur partagé sur ce même port, avec leur propre ordinateur local. Par exemple, si vous avez partagé un serveur web **qui s’exécute sur le port 3000**, l’invité peut y accéder sur son **propre ordinateur** à l’emplacement http://localhost:3000 ! La connexion est établie via un tunnel SSH ou SSL sécurisé entre l’hôte et les invités, et authentifiée via le service, ce qui garantit que seuls les participants de la session de collaboration y ont accès.

> **Conseil de sécurité :** en tant qu’hôte, choisissez soigneusement les ports que vous partagez avec les invités et tenez-vous-en aux ports d’application (par opposition aux ports système). Du côté des invités, les ports partagés se comportent exactement comme si le serveur/service était en cours d’exécution sur leur propre ordinateur. Cette fonction est très utile, mais il faut éviter tout risque de partager le mauvais port.

Pour des raisons de sécurité, seuls les serveurs qui s’exécutent sur les ports spécifiés sont accessibles aux autres invités. Il est facile pour un **hôte** de session de collaboration d’en ajouter un. Voici comment :

1. Cliquez sur le bouton Partager/État de session en haut à droite et sélectionnez « Gérer les serveurs locaux partagés ».

    ![Gérer les serveurs locaux partagés](../media/vs-share-local-servers.png)

2. Dans la boîte de dialogue qui s’affiche, cliquez sur « Ajouter » et entrez le numéro de port sur lequel le serveur s’exécute localement, entrez un nom et appuyez sur Entrée, puis sur OK.

    ![Gérer les serveurs locaux partagés](../media/vs-manage-local-shared-servers.png)

C’est tout ! Le serveur sur le port spécifié est alors mappé au localhost de chaque invité sur le même port (sauf si ce port est déjà occupé) !

Si le port est déjà utilisé sur l’ordinateur d’un invité, un autre est automatiquement sélectionné. Pour voir la liste des ports actuellement partagés (par nom le cas échéant) en tant qu’invité, cliquez sur le bouton Partager/État de session en haut à droite et sélectionnez « Afficher les serveurs locaux partagés ».

![Afficher les serveurs locaux partagés](../media/vs-view-shared-servers.png)

Sachez que, pour des raisons de sécurité, les *invités ne peuvent pas* contrôler les ports partagés sur l’ordinateur de l’hôte.

Pour **arrêter** le partage d’un serveur local, il suffit à l’hôte de cliquer comme tout à l’heure sur le bouton Partager/État de session en haut à droite, de sélectionner « Gérer les serveurs locaux partagés », de sélectionner le port concerné et de cliquer sur « Supprimer ».

## <a name="share-a-terminal"></a>Partager un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Live Share permet aux hôtes, s’ils le souhaitent, de « partager un terminal » avec les invités. Le terminal partagé peut fonctionner en lecture seule ou en collaboration totale, auquel cas tant l’hôte que les invités ont la possibilité d’exécuter des commandes et de voir les résultats. Vous pouvez offrir aux invités une visibilité sur la sortie de terminal ou les laisser exécuter des tests, des builds ou même catégoriser des problèmes propres à l’environnement de votre ordinateur.

Cependant, les terminaux ne sont **pas** partagés par défaut, dans la mesure où cela donnerait aux invités au moins un accès en lecture seule à la sortie des commandes exécutées (voire la possibilité d’exécuter des commandes eux-mêmes). Vous pouvez ainsi exécuter sans risque des commandes dans les terminaux locaux, en les partageant si nécessaire. Par ailleurs, seuls les hôtes (et non les invités) peuvent lancer des terminaux partagés, ce qui évite toute action inattendue ou inaperçue.

Pour partager un terminal en tant qu’hôte, cliquez sur le bouton Partager/État de session et sélectionnez un des éléments de menu « Partager le terminal ».

![Menu Terminal](../media/vs-terminal-menu.png)

Vous pouvez alors sélectionner un terminal en lecture seule ou en lecture/écriture dans le menu. Dans le deuxième cas, tout le monde, y compris l’hôte, peut taper dans le terminal, ce qui permet d’intervenir si un invité effectue une action indésirable. Dans un souci de sécurité toutefois, **ne donnez un accès en lecture/écriture qu’aux invités qui en ont réellement besoin** et tenez-vous-en aux terminaux en lecture seule si vous souhaitez simplement qu’ils voient le résultat des commandes exécutées.

> [!NOTE]
> Si la session de collaboration est en mode lecture seule, l’hôte ne peut partager les terminaux qu’en lecture seule.

Une fois le type de terminal partagé sélectionné, un nouveau terminal partagé apparaît avec les autorisations correspondantes pour tous les participants. À la différence de Visual Studio Code, Visual Studio ne comporte pas de terminal intégré prêt à l’emploi. C’est pourquoi, par défaut, une nouvelle fenêtre contenant le terminal s’affiche. Si en revanche [l’extension Whack Whack Terminal](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal) est installée, Live Share crée un terminal intégré. Visual Studio vous envoie un lien d’installation la première fois que vous lancez ou rejoignez un terminal partagé.

![Notification de toast d’installation du terminal](../media/vs-terminal-install.png)

Pour mettre fin à votre session de terminal, tapez simplement exit ou fermez la fenêtre du terminal ; tout le monde sera alors déconnecté.

## <a name="session-states"></a>États de session

Lorsque vous lancez ou rejoignez une session de collaboration et que vous avez accès au contenu partagé, le bouton « Live Share » en haut à droite se met à jour pour refléter l’état de la session de collaboration active.

Voici les états les plus courants :

| État | Bouton | Description |
|-------|--------|-------------|
| Inactif | ![État de Visual Studio : inactif](../media/vs-status-share.png) | Aucune session de collaboration active ; pas de partage. |
| Hôte : Partage en cours | ![État de Visual Studio : partage en cours](../media/vs-status-sharing.png) | Session de collaboration en cours de lancement, en attente du partage de contenu. |
| Hôte : Contrat de partage | ![État de Visual Studio : partage actif ](../media/vs-status-active.png) | Session de collaboration active et partage de contenu. |
| Hôte : Partage en lecture seule | ![État de Visual Studio : partage en lecture seule](../media/vs-status-sharing-read-only.png)| Partage d’une session de collaboration en lecture seule. |
| Invité : Accès en cours à la session | ![État de Visual Studio Code : accès en cours](../media/vs-status-joining.png) | Accès en cours à une session de collaboration. |
| Invité : Accès réussi | ![État de Visual Studio : accès réussi](../media/vs-status-joined.png) | Accès et connexion réussis à une session de collaboration active ; réception de contenu partagé en cours. |
| Invité : Accès en lecture seule | ![État de Visual Studio : accès en lecture seule](../media/vs-status-joined-read-only.png) | Accès et connexion réussis à une session de collaboration active en lecture seule. |

## <a name="guest-limitations"></a>Limitations portant sur les invités

Tandis que les invités risquent encore de rencontrer quelques défauts dans les fonctionnalités décrites ci-dessus, les hôtes de session de collaboration conservent toutes les fonctions de l’outil choisi. Pour plus d’informations, consultez :

- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Étapes suivantes

Pour plus d’informations, voir ces articles complémentaires.

- [Démarrage rapide : Partager un projet](../quickstart/share.md)
- [Démarrage rapide : Rejoindre une session](../quickstart/join.md)
- [Guide pratique : Travailler en collaboration à l’aide de Visual Studio Code](vscode.md)
- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
