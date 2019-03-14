---
title: Collaborer à l’aide de Visual Studio - partage en direct de Visual Studio | Microsoft Docs
description: Un ensemble de procédures de collaboration pour Visual Studio et de partage en direct.
ms.custom: ''
ms.date: 04/25/2018
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
ms.openlocfilehash: 995c9e16d24328bb2680deb99cd7e7d421af945c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256132"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-collaborate-using-visual-studio"></a>Comment : Collaborer à l’aide de Visual Studio

Prêt à obtenir en collaboration avec Partage Live dans Visual Studio ? Si tel est le cas, vous êtes au bon endroit ! Dans cet article nous allons vous guider comment utiliser certaines des fonctionnalités spécifiques dans l’extension de le Partage Live Visual Studio pour Visual Studio.

Notez que toutes les activités de collaboration dans décrites ici impliquant un seul **hôte de session de collaboration** et un ou plusieurs **invités**. L’hôte est la personne qui a commencé la session de collaboration. Les personnes qui s’inscrivent sont des invités.

*Vous recherchez une synthèse abrégée ? Découvrez le [partager](../quickstart/share.md) ou [jointure](../quickstart/join.md) Démarrages rapides à la place.*

> [!TIP]
> Saviez-vous que vous pouvez *rejoindre votre propre session de collaboration* ? Cela vous permet d’essayer Live Share seul ou de faire fonctionner une instance de Visual Studio ou VS Code, et de vous y connecter à distance ! Vous pouvez même utiliser la même identité sur les deux instances. À tester dès maintenant !

## <a name="installation"></a>Installation

Avant de commencer, vous devrez installer **Visual Studio 2017 15.6 ou ultérieure** sur Windows 7, 8.1 ou 10. *Toutefois, Visual Studio 15.7 + est recommandé car cela permet la prise en charge de l’annulation/de rétablissement local.*

Obtention de va est simple :

1. Installer l’une édition quelconque de [Visual Studio 2017](https://visualstudio.microsoft.com/vs/) 15.6 +.
2. Installer un [pris en charge de la charge de travail](../reference/platform-support.md). (par exemple, ASP.NET, .NET Core, C++ et/ou Node.js)
3. [Télécharger](https://aka.ms/vsls-dl/vs) et installer l’extension de le Partage Live Visual Studio à partir de la place de marché.

En téléchargeant et en utilisant Visual Studio Live Share, vous acceptez les [termes du contrat de licence](https://aka.ms/vsls-license) et la [déclaration de confidentialité](https://www.microsoft.com/en-us/privacystatement/EnterpriseDev/default.aspx). Si vous rencontrez des problèmes, consultez la section [dépannage](../troubleshooting.md).

[![Téléchargement](../media/download.png)](https://aka.ms/vsls-dl/vs)

## <a name="sign-in"></a>Se connecter

Afin de collaborer, vous devez l’authentification dans le partage en direct de Visual Studio pour que tout le monde sache qui vous êtes. Cela est purement une mesure de sécurité et que vous ne **pas** vous opter pour n’importe quel marketing ou d’autres activités de recherche. Vous pouvez vous connecter avec un compte personnel Microsoft (par exemple, @outlook.com), appuyé par Microsoft compte professionnel ou scolaire (AAD) ou un compte GitHub. Il est facile de la connexion.

Par défaut, Visual Studio utilise le votre [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio) donc si vous êtes déjà connecté à Visual Studio, vous pourrez peut-être ignorer cette étape. Sinon, connectez-vous comme vous le feriez normalement.

![Bouton de connexion de Visual Studio](../media/vs-sign-in-button.png)

Si vous souhaitez utiliser une autre connexion par rapport à Visual Studio [compte de personnalisation](https://docs.microsoft.com/en-us/visualstudio/ide/signing-in-to-visual-studio), accédez à **outils &gt; Options &gt; Partage Live &gt; compte d’utilisateur** pour basculer informations d’identification.

![Options des outils de Visual Studio Live Share](../media/vs-tools-options.png)

En sélectionnant **compte externe** vous permet de sélectionner un compte non pris en charge par la fonctionnalité de personnalisation de Visual Studio comme GitHub. Un navigateur s’affiche automatiquement la première fois que vous utilisez une fonctionnalité de partage en direct afin de vous permettre d’effectuer de connexion.

Si vous rencontrez des problèmes, consultez [dépannage](../troubleshooting.md#sign-in) pour plus de conseils.

## <a name="share-a-project"></a>Partager un projet

Après le téléchargement et installation de partage en direct de Visual Studio, suivez ces étapes pour démarrer une session de collaboration et d’inviter un collègue à travailler avec vous.

1. **Connexion**

    Après avoir installé l’extension de partage en direct, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Par défaut Visual Studio utilise votre compte de personnalisation, donc vous pourrez peut-être ignorer cette étape entièrement.

    Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Ouvrir une solution, un projet ou un dossier**

    Utilisez votre flux de travail normal pour ouvrir un dossier, un projet ou une solution que vous aimeriez partager avec vos invités.

3. **[Facultatif] Mettre à jour les fichiers cachés ou exclus**

    Par défaut, Partage Live **masque** les fichiers/dossiers référencés dans les fichiers .gitignore dans votre projet d’invités. **Masquage** un fichier empêche d’apparaître dans l’arborescence des fichiers lors de la **à l’exclusion** il arrête la transmission même pendant les opérations telles que le débogage. Si vous souhaitez masquer/exclure des fichiers différents, un **. vsls.json** fichier peut être ajouté à votre projet avec ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

4. **Démarrer une session de collaboration**

    Maintenant, cliquez simplement sur le bouton « Partage » dans le coin supérieur droit.

    ![Bouton de partage de VS](../media/vs-share-button.png)

    > [!NOTE]
    > Vous pouvez être invité par votre logiciel de pare-feu de bureau pour permettre à l’agent Partage Live ouvrir un port de la première fois que vous partagez. Accepter ce est entièrement facultative mais permet un « mode direct » sécurisé pour améliorer les performances lorsque la personne que vous utilisez est sur le même réseau que vous êtes. Consultez [modifier le mode de connexion](../reference/connectivity.md#changing-the-connection-mode) pour plus d’informations.

    Un lien d’invitation est copié automatiquement dans le Presse-papiers. L’ouverture dans un navigateur, ce lien permet d’autres utilisateurs à joindre une nouvelle session de collaboration qui partage le contenu de ces dossiers avec eux.

    Vous verrez également la transition du bouton « Partage » pour transmettre un « état de Session ». Consultez [l’état de session](#session-states) informations ci-dessous sur quoi cela ressemble.

    Notez que si vous avez besoin obtenir le lien d’invitation à nouveau une fois que vous avez démarré le partage, vous pouvez y accéder en cliquant sur le partage / bouton et en sélectionnant « Copier le lien » d’état de session.

5. **[Facultatif] Activer le mode en lecture seule**

    Une fois que vous démarrez votre session de collaboration, vous pouvez définir la session peut être en lecture seule pour empêcher les invités d’apporter des modifications au code partagé.

    Après le partage, vous recevez une notification que le lien d’invitation a été copié dans le Presse-papiers. Vous pouvez ensuite sélectionner l’option pour que la session en lecture seule.

    ![Mode lecture seule de VS](../media/vs-read-only-notification.png)

6. **Envoyer le lien**

    Envoyez le lien par courrier électronique, Slack, Skype, etc. à ceux que vous souhaitez inviter. Notez que, étant donné le niveau d’accès de partage Live sessions peuvent fournir aux invités, **vous devez uniquement partager avec des personnes dignes de confiance** et réflexion via les implications de ce que vous partagez.

    > **Astuce de sécurité :** Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

    Si l’invité que vous avez invité a des questions, le «[Guide de démarrage rapide : Joindre votre première session](../quickstart/join.md)« article fournit des informations supplémentaires sur rendre opérationnel et en cours d’exécution en tant qu’invité.

7. **[Facultatif] Approuver l’invité**

    Par défaut, les invités joint automatiquement votre session de collaboration, et vous serez averti lorsque vous leur ont prêt à travailler avec vous. Bien que cette notification vous donne la possibilité pour les supprimer de la session, vous pouvez aussi pour exiger à la place une « approbation » explicite pour toute personne rejoindre.

    Modifiez simplement **Outils > Options > Partage Live > demander l’approbation invité** sur True pour activer la fonctionnalité. Une fois que vous avez ce paramètre est activé, une notification vous invitera à approuver l’invité avant de pouvoir participer.

    ![Demande d’approbation de jointure Visual Studio](../media/vs-join-approval.png)

    Consultez [invitations et accès de jointure](../reference/security.md#invitations-and-join-access) pour plus d’informations sur les considérations de sécurité d’invitation.

Voilà !!

### <a name="ending-the-collaboration-session"></a>Fin de la session de collaboration

En tant qu’hôte, vous pouvez arrêter le partage complètement et terminer la session de collaboration en cliquant sur le partage / bouton (dans le coin supérieur droit) et la Session de Collaboration de fin en sélectionnant « » d’état de session.

![Arrêter le partage](../media/vs-stop-sharing.png)

Tous les invités seront informées que la session est terminée. Une fois la session s’est terminée, les invités ne seront plus en mesure d’accéder au contenu et tous les fichiers temporaires sont automatiquement nettoyés.

Vous rencontrez des problèmes avec le partage ? Découvrez [dépannage](../troubleshooting.md#share-and-join).

## <a name="join-a-collaboration-session"></a>Rejoindre une session de collaboration

Après le téléchargement et installation de partage en direct de Visual Studio, invités suffit à prendre de quelques étapes pour rejoindre une session de collaboration hébergée. Il existe deux manières de joindre : [via le navigateur](#join-via-the-browser) et [manuellement](#join-manually).

> **Astuce de sécurité :** En tant qu’invité rejoindre une session de collaboration, il est important de comprendre que les hôtes peuvent restreindre votre accès à certains fichiers ou des fonctionnalités. Vous voulez comprendre les implications de sécurité de certaines des fonctionnalités et les paramètres du partage en direct ? Découvrez le [sécurité](../reference/security.md) article.

### <a name="join-via-the-browser"></a>Joindre via le navigateur

Rejoindre une session de collaboration, le plus simple consiste à simplement ouvrir le lien d’invitation dans un navigateur web. Voici ce que vous pouvez attendre quand vous suivez ce flux.

1. **Connexion**

    Après avoir installé l’extension de partage en direct, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Par défaut Visual Studio utilise votre compte de personnalisation, donc vous pourrez peut-être ignorer cette étape entièrement.

    Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Cliquez sur le lien d’invitation / ouvrir l’invitation dans votre navigateur**

    À présent, ouvrez simplement (ou ouvrez à nouveau) le lien d’invitation dans un navigateur.

    > **Remarque** : Si vous n’avez pas encore installé l’extension de partage en direct, s’affiche avec des liens vers la place de marché d’extension. Installer l’extension et redémarrez votre outil et réessayez.

    Vous devez averti que le navigateur souhaite lancer un outil de partage en direct est activé. Si vous la laissez lancer votre outil sélectionné, vous devez être connecté à la session de collaboration, une fois démarré.

    ![Joindre la page](../media/join-page.png)

    Si l’hôte est hors connexion, vous serez averti à ce stade au lieu de cela. Vous pouvez ensuite contacte l’ordinateur hôte et demandez-lui de le partager à nouveau.

    > [!NOTE]
    > Rencontrez encore des problèmes ? Consultez [joindre manuellement des](#join-manually).

3. **Collaborate**

    Voilà !! Dans quelques instants, vous êtes connecté et vous pouvez commencer à collaborer.

    Vous verrez la transition du bouton « Partage » pour transmettre un « état de Session ». Consultez [l’état de session](#session-states) informations ci-dessous pour quoi cela ressemble.

    Vous allez ensuite automatiquement dirigé vers le fichier de que l’hôte est en train de modifier une fois la jointure est terminée.

### <a name="join-manually"></a>Joindre manuellement

Vous pouvez joindre manuellement sans utiliser un navigateur web qui peut être utile dans les situations où l’outil que vous souhaitez utiliser est déjà en cours d’exécution, vous souhaitez utiliser un autre outil que vous le faites habituellement, ou si vous rencontrez des difficultés avec l’obtention inviter des liens de fonctionner pour une raison quelconque. Le processus est simple :

1. **Connexion**

    Après avoir installé l’extension de partage en direct, vous souhaitez vous connecter à informer autres collaborateurs qui vous êtes. Par défaut Visual Studio utilise votre compte de personnalisation, donc vous pourrez peut-être ignorer cette étape entièrement.

    Consultez [connectez-vous](#sign-in) pour plus d’informations.

2. **Utilisez la commande de jointure**

    Accédez simplement à **fichier > rejoindre une Session de Collaboration**

    ![Menu de jointure de VS](../media/vs-join.png)

3. **Collez le lien d’invitation**

    Collez l’URL de l’invitation vous ont été envoyés et confirmez.

4. **Collaborer !**

    C’est tout ! Vous devez être connecté à la session de collaboration momentanément.

    Vous verrez la transition du bouton « Partage » pour transmettre un « état de Session ». Consultez [l’état de session](#session-states) informations ci-dessous pour quoi cela ressemble.

    Vous allez ensuite automatiquement dirigé vers où l’hôte est en train de modifier une fois la jointure terminée.

### <a name="leave-the-collaboration-session"></a>Laissez la session de collaboration

En tant qu’invité, vous pouvez laisser la session de collaboration sans mettre fin pour d’autres en fermant simplement l’outil ou en cliquant sur le partage / bouton et en sélectionnant « Quitter la Session de Collaboration » d’état de session.

![Menu de jointure de VS](../media/vs-leave-session.png)

Tous les fichiers temporaires sont automatiquement nettoyés, aucune action supplémentaire n’est nécessaire.

Rencontre des problèmes de jointure ? Découvrez [dépannage](../troubleshooting.md#share-and-join).

## <a name="co-editing"></a>Coédition

Une fois qu’un invité a joint une session de collaboration, tous les collaborateurs seront immédiatement être en mesure de voir les modifications des autres et les sélections en temps réel. Il vous suffit de faire est de choisir un fichier à partir de l’Explorateur de fichiers et de commencer à modifier. Hôtes et invités affiche les modifications que peuvent contribuer eux-mêmes rend facile d’itérer et maîtriser rapidement pour réduire les solutions et faire.

> [!NOTE]
> Rejoindre une session de collaboration en lecture seule empêche les invités d’être en mesure d’apporter des modifications aux fichiers. Un hôte peut [activer le mode lecture seule quand ils partagent](#share-a-project). En tant qu’invité, vous pouvez indiquer si vous avez joint une session en lecture seule en examinant votre [l’état de session](#session-states).

![Capture d’écran affichant la même édition](../media/vs-coedit.png)

> [!NOTE]
> Même édition a quelques limitations pour certaines langues. Voir la section [plateforme prise en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités par langue.

Au-delà des curseurs et les modifications, vos sélections sont également visibles à tous les participants dans ce même fichier. Cela rend facile à mettre en surbrillance où des problèmes peuvent exister ou communiquer des idées.

![Capture d’écran affichant la mise en surbrillance](../media/vs-highlight.png)

Mieux encore, vous et les autres participants peuvent accéder à n’importe quel fichier dans le projet partagé. Vous pouvez soit modifier l’ensemble ou indépendamment de ce qui signifie que vous pouvez basculer en toute transparence entre l’enquête, ce qui rend petits ajustements et la modification collaborative complète.

> [!NOTE]
> Par défaut les partages de partage en direct les fichiers externes à la solution de partagé ouvrent. Si vous souhaitez désactiver cette fonctionnalité, mettez à jour le partage de fichiers externes dans les outils &gt; Options &gt; Partage Live sur False.

La modification qui en résulte est rendues persistantes sur l’ordinateur de l’hôte sur Enregistrer et il n’est pas nécessaire de synchroniser, push ou envoyer des fichiers une fois que vous avez terminé édition. Les modifications sont « juste there ».

> **Astuce de sécurité :** Étant donné tous les participants peuvent indépendamment accéder et modifier des fichiers, en tant qu’hôte, vous pouvez souhaiter limiter les fichiers invités peuvent accéder dans votre projet via un. vsls.json fichier. En tant qu’invité, il est également important de savoir que vous ne voyiez pas certains fichiers à la suite de ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

### <a name="changing-participant-flag-behaviors"></a>Modification des comportements de l’indicateur de participants

Par défaut, le partage en direct de Visual Studio affiche automatiquement un « indicateur » en regard de curseur d’un participant au pointage, ou quand ils le modifiez, mettez en surbrillance, ou déplacez le curseur. Dans certains cas, vous pouvez modifier ce comportement. Pour ce faire :

1. Accédez à **Outils > Options > Live partage**
2. Modifier le **indicateur de visibilité** option à une des opérations suivantes :

| Option | Comportement |
|--------|----------|
| OnHoverOnly | L’indicateur est visible uniquement lorsque vous pointez sur le curseur. |
| OnHoverOrActivity | Il s'agit de la valeur par défaut. L’indicateur est visible au pointage ou si le participant modifie, met en surbrillance, ou déplace le curseur. |
| Always | L’indicateur est toujours visible.

## <a name="following"></a>Suivant

Chaque fois que vous êtes dans une session de collaboration, vous pourrez peut voir les initiales de chaque participant dans le coin supérieur droit de l’éditeur à côté du bouton de connexion. Survole les initiales de l’affiche des informations complète du participant.

![Capture d’écran montrant utilisateur](../media/vs-person.png)

Parfois, vous devrez peut-être expliquer un problème ou une conception qui s’étend sur plusieurs fichiers ou les emplacements dans le code. Dans ces situations, peuvent être utiles pour temporairement suivent un collègue lorsqu’ils utilisent tout au long du projet. Pour cette raison, en tant qu’invité, lorsque vous joignez une session de collaboration vous serez automatiquement « suivre » l’hôte. Lorsque vous suivez un participant, votre éditeur reste synchronisée avec leurs fichiers actuellement ouverts, le curseur et la position de défilement.

> [!NOTE]
> Par défaut les partages de partage en direct les fichiers externes à la solution de partagé ouvrent. Si vous souhaitez désactiver cette fonctionnalité, mettez à jour le partage de fichiers externes dans les outils &gt; Options &gt; Partage Live sur False.

Pour faciliter l’extraire de « mode de suivi » et commencer à modifier vous-même, vous allez arrêter suivant si les éléments suivants se produit :

1. Vous modifiez, déplacez votre curseur ou effectuez une sélection
2. Vous sélectionnez un autre fichier

Vous pouvez également arrêter suivant à tout moment en cliquant sur les initiales de la personne que vous suivez dans le coin supérieur droit. Le cercle autour de vos initiales du participant qui indique que vous suivez les disparaîtra puis.

![Participant de Studio Visual suivi](../media/vs-pinned.png) ![Participant de Studio Visual ne pas suivi](../media/vs-pin-hover.png)

Vous pouvez cliquer sur n’importe quel initiales à ce même emplacement à suivre n’importe quel hôte ou invité dans la session de collaboration. Notez que si vous souhaitez simplement accéder à de quelqu'un emplacement plutôt que leur suite, double-cliquez simplement sur leurs initiales.

## <a name="focusing"></a>En mettant l’accent

Il peut arriver que vous souhaiterez peut-être tout le monde dans une session de collaboration et examinons quelque chose que vous effectuez. Partage en direct vous permet de demander que tout le monde » nous concentrer » leur attention sur vous avec une notification qui facilite leur permet de vous suivre de nouveau.

Simplement cliquer sur l’état de session / partager le bouton dans le coin supérieur droit et sélectionnez « Focus Participants ».

![Option de menu de focus](../media/vs-focus.png)

Tous les membres de la session de collaboration puis recevra une notification indiquant que vous avez demandé à leur attention

![Notification toast de focus](../media/vs-focus-toast.png)

Ils puis suffit de cliquer sur « Suivre » directement à partir de la notification quand ils sont prêts à mettre ses priorités sur vous.

## <a name="co-debugging"></a>Codébogage

Fonctionnalité de débogage collaboratif de Visual Studio Live du partage est un moyen puissant et unique pour déboguer un problème. Au-delà de l’activation de fonctionnalités de collaboration résoudre les problèmes, il également vous et les autres participants dans votre session, la possibilité d’examiner les problèmes qui peuvent être environnement spécifique en fournissant une session de débogage partagée sur l’ordinateur de l’hôte.

> **Astuce de sécurité :** Étant donné tous les participants peuvent indépendamment accéder et modifier des fichiers, en tant qu’hôte, vous pouvez souhaiter limiter les fichiers invités peuvent accéder dans votre projet via un. vsls.json fichier. Vous devez également connaître que les accès Console/REPL signifie que les participants peuvent exécuter des commandes sur votre ordinateur donc vous devez déboguer uniquement conjointement avec des personnes de que confiance. En tant qu’invité, il est également important de savoir que vous n’êtes peut-être pas en mesure de suivre le débogueur, comme détaillé dans certains fichiers restreint de fichiers à la suite de ces paramètres. Consultez [contrôlant l’accès aux fichiers et visibilité](../reference/security.md#controlling-file-access-and-visibility) pour plus d’informations.

À l’aide de simple. L’hôte de session de collaboration doit simplement démarrer le débogage via les moyens habituels dans Visual Studio.

![Bouton de débogage de Visual Studio](../media/vs-debug-button.png)

Une fois que le débogueur s’attache à côté de l’ordinateur hôte, tous les invités sont également attachées automatiquement également. Bien qu’un débogage « session » en cours d’exécution sur l’ordinateur de l’hôte, tous les participants sont connectés et ont leur propre affichage.

> [!TIP]
> Si vous souhaitez modifier quand et comment se produit même emplacement de débogage, vous pouvez modifier les comportements par défaut par le biais de paramètres dans **Outils > Options > Partage Live**.

![Débogueur de VS](../media/vs-debugger.png)

Tout le monde peut parcourir le processus de débogage qui permet une commutation transparente entre collaborateurs sans avoir à négocier le contrôle.

> [!NOTE]
> Consultez la section relative aux [plateformes prises en charge](../reference/platform-support.md) pour connaître l’état des fonctionnalités de débogage par langue ou plateforme.

Chaque collaborateur peut examiner les différentes variables, accéder à des fichiers différents dans la pile des appels, inspecter des variables et même ajouter ou supprimer des points d’arrêt. Fonctionnalités d’édition hébergé autorise alors chaque participant poête effectuer le suivi dans lequel les autres se trouvent pour fournir la capacité unique à basculer en toute transparence entre simultanément examen des différents aspects du problème et le débogage en collaboration.

> [!NOTE]
> Au cours d’une session de collaboration en lecture seule, un invité ne sera pas en mesure de parcourir le processus de débogage. Ils peuvent toutefois, toujours ajouter ou supprimer des points d’arrêt et inspecter les variables.

> [!TIP]
> Vous pouvez également participer à partir de Visual Studio et vice versa de sessions de débogage de VS Code ! Découvrez le [obtenir des instructions de Visual Studio](vscode.md#co-debugging) sur le même emplacement de débogage pour plus d’informations.

### <a name="automatic-web-app-sharing"></a>Partage d’application web automatique

Mieux encore, pour les projets d’application Web ASP.NET, par défaut si le projet de l’hôte est configuré pour démarrer automatiquement un navigateur web pour se connecter à l’application web en cours d’exécution lors du débogage, Partage Live effectuent automatiquement le même sur l’ordinateur de chaque invité ! Cette opération est effectuée de manière sécurisée et l’application web à distance est uniquement disponible pour les invités pendant la session de débogage par défaut.

Consultez [partager un serveur](#share-a-server) pour plus d’informations sur la façon de partager l’accès au serveur pour les autres types de projet et/ou pendant la durée de la session.

> [!TIP]
> Si vous ne telles que le comportement de partage de navigateur automatisé et souhaitez le modifier, vous pouvez mettre à jour des paramètres dans **Outils > Options > Partage Live**.

![Animation de débogage simultanées](../media/co-debug.gif)

### <a name="change-when-visual-studio-joins-debugging-sessions"></a>Quand modifier des jointures de Visual Studio sessions de débogage

Par défaut, en tant qu’invité, vous allez être automatiquement joint aux sessions quand ils sont partagés par l’hôte de débogage. Toutefois, dans certains cas vous souhaiterez ce comportement sans interruption. Heureusement, vous pouvez modifier comme suit :

1. Accédez à **Outils > Options > Live partage**
2. Modifier le **option de session de débogage de jointure** à une des opérations suivantes :

| Option | Comportement |
|--------|----------|
| Automatique | Valeur par défaut. En tant qu’invité, vous allez joindre automatiquement tout l’hôte démarre la session de débogage partagée. |
| Vous y êtes invité | En tant qu’invité, vous êtes invité à indiquer si vous souhaitez rejoindre une session de débogage partagée lorsqu’il est démarré par l’hôte. |
| Manuel | En tant qu’invité, vous devez joindre manuellement des sessions de débogage. Consultez [détachement et rattachement](#detaching-and-reattaching).|

### <a name="detaching-and-reattaching"></a>Détachement et rattachement

En tant qu’invité, vous pouvez souhaiter arrêter le débogage temporairement. Heureusement, vous pouvez simplement cliquer sur l’icône « Arrêter » dans la barre d’outils de débogage pour détacher le débogueur sans affecter l’hôte ou autres invités.

Si vous avez mis à jour les paramètres afin que vous n’avez plus l’attachement automatique ou si vous souhaitez simplement rattacher plus tard, il vous suffit de sélectionner l’exécution souhaitée, le débogage de session à partir de la « Select démarrage élément... » liste déroulante...

![Bouton de débogage de Visual Studio](../media/vs-select-reattach.png)

... et puis cliquez dessus pour attacher.

![Bouton de débogage de Visual Studio](../media/vs-reattach.png)

## <a name="share-a-server"></a>Partager un serveur

À partir de l’heure de temps, comme un hôte de session de collaboration vous constatiez que vous souhaitez partager des serveurs locaux supplémentaires ou des services avec les invités. Cela peut consister à partir d’autres points de terminaison RESTful pour les bases de données ou d’autres serveurs. Visual Studio Live partager vous permet de spécifier un numéro de port local, si vous le souhaitez lui donner un nom, puis le partager avec tous les invités.

Les invités pourront ensuite accéder au serveur que vous avez partagé sur ce port à partir de leur propre ordinateur local sur le même port exact. Par exemple, si vous avez partagé un serveur web **en cours d’exécution sur le port 3000**, l’invité peut accéder à ce même serveur web en cours d’exécution sur leur **propre machine** à http://localhost:3000! Cela est effectué via un tunnel SSH ou SSL sécurisé entre l’hôte et les invités et authentifié via le service afin de vous assurer que seules dans la session de collaboration ont accès.

> **Astuce de sécurité :** En tant qu’hôte, vous devez être très sélective avec les ports que vous partagez avec des invités et respectez les application ports (plutôt qu’un port de système de partage). Pour les invités, des ports partagés seront comportent exactement comme il le ferait si le service/serveur était en cours d’exécution sur leur propre ordinateur. Cela est très utile, mais si le port incorrect est partagé permettre également être à risque.

Pour des raisons de sécurité, seuls les serveurs en cours d’exécution sur les ports que vous spécifiez sont disponibles aux autres invités. Heureusement, son facile d’ajouter un en tant que la session de collaboration **hôte**. Voici comment :

1. Cliquez sur le partage / état de session situé dans le coin supérieur droit et sélectionnez « Gérer les serveurs locaux partagés »

    ![Gérer des serveurs locaux partagés](../media/vs-share-local-servers.png)

2. Dans la boîte de dialogue qui s’affiche, cliquez sur « Ajouter » et entrez le numéro de port que le serveur est en cours d’exécution sur localement, entrez un nom, appuyez sur entrée, puis OK.

    ![Gérer des serveurs locaux partagés](../media/vs-manage-local-shared-servers.png)

C’est tout ! Le serveur sur le port spécifié est maintenant mappé à localhost de chaque invité sur le même port (à moins que ce port est déjà occupé) !

Si le port est déjà en cours d’utilisation sur l’ordinateur d’un invité, une autre est automatiquement sélectionnée. Heureusement, comme un invité, vous pouvez voir une liste d’actuellement partagé ports (par nom si spécifié) en cliquant sur le partage / de l’état de session situé dans le coin supérieur droit et en sélectionnant « vue partagé Local serveurs ».

![Viw partagé des serveurs locaux](../media/vs-view-shared-servers.png)

Notez que *invités ne peuvent pas* contrôler quels ports sur l’ordinateur de l’hôte sont partagées pour des raisons de sécurité.

Pour **arrêter** partage un serveur local, l’hôte doit simplement cliquer sur le partage / état de session bouton en haut à droite comme ci-dessus, sélectionnez « Gérer partagé Local serveurs » et sélectionnez le port approprié et cliquez sur « Supprimer ».

## <a name="share-a-terminal"></a>Partager un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Partage Live vous permet, en tant qu’hôte, si vous le souhaitez « partager un terminal » avec les invités. Le terminal partagé peut être en lecture seule ou entièrement collaborative afin de vous et les invités peuvent exécuter des commandes et voir les résultats. Vous pouvez donner une visibilité des invités à la sortie de terminal ou de leur permettre de découvrir et exécuter des tests, builds ou triage même environnement des problèmes spécifiques qui se produisent uniquement sur votre ordinateur.

Toutefois, les terminaux sont **pas** partagé par défaut dans la mesure où ils donnent aux invités au moins un accès en lecture à la sortie des commandes que vous exécutez (si ce n’est pas la possibilité d’exécuter des commandes eux-mêmes). Cette façon d’exécuter des commandes dans des terminaux locales sans risque et de partager uniquement lorsque librement a réellement besoin de le faire. De plus, seuls les ordinateurs hôtes peuvent démarrer des terminaux partagées pour empêcher les invités à partir d’un démarrage et de faire quelque chose vous ne sont pas attendu ou l’observation des.

En tant qu’hôte, vous pouvez partager un terminal en cliquant sur l’état de session / partager le bouton dans le coin supérieur droit et en sélectionnant un des éléments de menu « Partager Terminal Server ».

![Menu Terminal](../media/vs-terminal-menu.png)

À ce stade, vous pouvez sélectionner en lecture seule ou lecture/écriture Terminal Server à partir du menu. Lorsque le terminal est en lecture/écriture, tout le monde peut taper dans le terminal, y compris l’hôte, ce qui facilite l’intervenir si un invité fait quelque chose que vous n’aimez pas. Toutefois, pour plus de sécurité, vous devez **donner uniquement un accès en lecture/écriture aux invités lorsque vous savez ils en ont réellement besoin** cap et gardez-le terminaux en lecture seule pour les scénarios où vous voulez juste l’invité pour voir le résultat de toutes les commandes que vous exécutez.

> [!NOTE]
> Si la session de collaboration est en mode lecture seule, terminaux en lecture seule peuvent être partagés par l’hôte.

Une fois que vous avez sélectionné le type de terminal partagé, que vous souhaitez démarrer, un nouveau terminal partagé s’affiche pour tous les participants avec les autorisations appropriées. Alors que Visual Studio Code a une prise en charge terminal intégré dans Visual Studio n’a pas un emploi. Par conséquent, par défaut, la nouvelle fenêtre qui contient le terminal s’affiche. Toutefois, si le [extension donnez un grand coup donnez un grand coup Terminal](https://marketplace.visualstudio.com/items?itemName=DanielGriffen.WhackWhackTerminal), Partage Live créera un terminal intégré à la place. Visual Studio vous donne un lien pour l’installer à la première fois que vous démarrez ou joindre un terminal partagé.

![Notification de toast installer Terminal Server](../media/vs-terminal-install.png)

Pour mettre fin à votre session de terminal, tapez simplement quitter ou fermer la fenêtre de terminal et tout le monde va être déconnectée.

## <a name="session-states"></a>États de session

Après avoir lancé ou rejoint la session de collaboration et avoir accès au contenu partagé, le bouton « Partager » dans le coin supérieur droit met à jour son apparence pour refléter l’état de la session de collaboration active.

Les États que vous verrez généralement sont les suivantes :

| État | Bouton | Description |
|-------|--------|-------------|
| inactif | ![État de Visual Studio : inactif](../media/vs-status-share.png) | Aucune session de collaboration active et que rien n’est partagé. |
| Hôte : Partage en cours d’exécution | ![État de Visual Studio : partager en cours](../media/vs-status-sharing.png) | Démarrage d’une session de collaboration et partage de contenu va bientôt commencer. |
| Hôte : Contrat de partage | ![État de Visual Studio : partage active ](../media/vs-status-active.png) | Une session de collaboration est active et le contenu est partagé. |
| Hôte : Partage en lecture seule | ![État de Visual Studio : partage en lecture seule](../media/vs-status-sharing-read-only.png)| Partage d’une session de collaboration en lecture seule. |
| Invités : Rejoindre la Session | ![État du Code VS : jointure](../media/vs-status-joining.png) | Rejoindre une session de collaboration existant. |
| Invités : Joint | ![État de Visual Studio : joint](../media/vs-status-joined.png) | Joint et connecté à une session de collaboration active et la réception de contenu partagé. |
| Invités : Joint en lecture seule | ![État de Visual Studio : jointe en lecture seule](../media/vs-status-joined-read-only.png) | Joint et connecté à une session active collaboration en lecture seule. |

## <a name="guest-limitations"></a>Limitations des invités

Bien qu’il existe actuellement des défauts invités seront confrontés lors de l’utilisation des fonctionnalités décrites ci-dessus, les hôtes de session de collaboration conservent une fonctionnalité complète de l’outil de leur choix. Pour plus d’informations, consultez :

- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Extensions prises en charge](../reference/extensions.md)
- [Tous les bogues majeurs, demandes de fonctionnalités et limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

## <a name="next-steps"></a>Étapes suivantes

Consultez ces articles supplémentaires pour plus d’informations.

- [Démarrage rapide : Partager votre premier projet](../quickstart/share.md)
- [Démarrage rapide : Joindre votre première session](../quickstart/join.md)
- [Comment : Collaborer à l’aide de Visual Studio Code](vscode.md)
- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
