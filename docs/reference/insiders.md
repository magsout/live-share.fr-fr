---
title: Insiders-Visual Studio Live Share | Microsoft Docs
description: Description du canal «Insiders» dans Visual Studio Live Share.
ms.custom: ''
ms.date: 04/02/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 04bfb314ebae711566a8bab8b0ada8f2fbd2e940
ms.sourcegitcommit: 6b46e300d76eda661ab34c67a3b909d5c162cd9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2019
ms.locfileid: "70062278"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Membres du programme Insider

L’équipe Visual Studio Live Share est l’itération rapide, l’essai de nouvelles idées et l’écoute de nos clients. Les insiders offrent à nos utilisateurs la possibilité de tester toutes nos nouvelles fonctionnalités tout d’abord et d’apporter leurs précieux commentaires! Découvrez comment [devenir un](#BecomeanInsider) Insider ci-dessous et aidez-nous à mettre l’avenir en collaboration avec les développeurs. 

## <a name="new-to-insiders"></a>✨ Les nouvelles ✨


### <a name="reusable-sessions-vs-code"></a>**Sessions réutilisables (VS Code)**

Live Share pouvez désormais héberger des sessions réutilisables! Les sessions réutilisables vous permettent de réutiliser une session Live Share pour différents scénarios. Cela signifie que vous pouvez planifier une session Live Share à l’avance pour vos entretiens techniques, la session hebdomadaire de programmation Mob, utiliser la même session tout en parrainant un ami, et bien plus encore.

Pour créer une session réutilisable, procédez comme suit:
1. Accédez à l' `Command Palette` utilisation`Ctrl+Shift+P`
1. Tapez «SHA Live...» et cliquez sur le **_Live share: Commande de création d’une_liaison**de session réutilisable».

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Cette opération crée une session réutilisable et un lien vers celle-ci est copié dans le presse-papiers. Une fenêtre contextuelle de notification s’affiche dans l’angle inférieur droit de votre éditeur.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Votre session réutilisable a été créée. Partagez le lien avec votre session et utilisez-le chaque fois pour accéder à la session!

> [!TIP] 
>Un lien de session réutilisable est persistant et dure 30 jours à partir de sa date de création ou de la date de dernière utilisation. Cela signifie que si vous continuez à utiliser votre session au moins une fois tous les 30 jours, vous n’avez pas à vous soucier de son expiration. Enregistrez simplement le lien dans un endroit sûr où vous pouvez y accéder facilement!
 

### <a name="direct-user-invitations"></a>**Invitations de l’utilisateur direct**

À l’heure actuelle, Visual Studio et Visual Studio code `Contacts` fournissent un volet, qui active deux fonctions clés:

1. Affichage d’une liste `Suggested Contacts`de, qui sont des développeurs qui ont contribué à votre projet actuellement ouvert au cours des 30 derniers jours. Dans la pratique, il s’agit des personnes avec lesquelles vous êtes susceptible de vouloir collaborer. par conséquent, nous vous suggérons de les suggérer afin de faciliter la prise en main.

2. En fournissant la liste `Recent Contacts`des, qui sont les développeurs avec lesquels vous avez déjà collaboré avec Live share. Dans la pratique, la plupart des développeurs collaborent souvent avec les mêmes personnes et, par conséquent, la liste récente permet un moyen plus reproductible de travailler avec votre équipe/salle de classe/etc.

Toutefois, la `Contacts` liste vous permet uniquement d’inviter des contacts récents/suggérés par courrier électronique, ce que nous avons appris n’est pas aussi efficace que possible. Si vous installez la dernière mise à jour de Live share `Insiders` et que vous activez (comme décrit ci-dessus), vous pourrez désormais **inviter des développeurs dans une session de collaboration directement à partir de l’IDE**. Notez que si vous utilisez Visual Studio Code, vous devez installer la [Build](https://code.visualstudio.com/insiders/) Insiders pour que cette fonctionnalité fonctionne.

![Invitatiosn directe](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Un hôte de Live Share (à gauche) qui invite directement un homologue (à droite) dans une session</em>

Une fois que les développeurs se connectent avec Live Share, leur état de disponibilité est publié sur leurs pairs. Par conséquent, vous pouvez voir que quelqu’un de votre équipe est en ligne, puis commencer immédiatement à collaborer avec eux. Ils recevront une notification de Toast qui leur donne la possibilité de rejoindre la session. Cela élimine la nécessité d’échanger des URL de session entièrement.

Après 5 minutes d’inactivité, votre état passe automatiquement à `Away`et, lorsque vous êtes dans une session de Live Share, votre état passe automatiquement à `Do not disturb` (les notifications de Toast suprresses invitation). Une fois que vous êtes à nouveau actif et/ou que vous laissez une session Live Share, votre état `Available`repasse automatiquement à. Avec ce comportement, vous n’avez pas besoin de gérer réellement l’état de votre Live Share. C’est simplement là pour activer les invitations directes et communiquer avec vos pairs, que vous soyez ou non en collaboration. Toutefois, vous pouvez toujours définir manuellement votre état si vous préférez.

Si vous souhaitez refuser cette fonctionnalité, vous pouvez simplement désactiver le `Presence` paramètre dans les paramètres de Live share dans Visual Studio et Visual Studio code. Une fois désactivée, vous pouvez toujours voir l’état de l’autre et l’inviter, mais votre état n’est pas publié et d’autres personnes ne peuvent pas vous inviter directement.

 

## Devenez un Insider <a name="BecomeanInsider"></a>

Par défaut, après l’installation de l’extension Visual Studio Live Share, vous utilisez `Stable` l’ensemble de fonctionnalités, qui comprend toutes les fonctionnalités prêtes pour la production (par exemple, le co-édition, le débogage partagé, les terminaux). Toutefois, si vous souhaitez accéder en avant-première aux fonctionnalités sur lesquelles nous travaillons, vous pouvez vous abonner à l' `Insiders` ensemble de fonctionnalités en modifiant le paramètre suivant dans votre IDE:

* Visual Studio

    ![ensemble de fonctionnalités-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![Feature-Set-vscode](../media/feature-set-vscode.png)

Les sections suivantes décrivent l’ensemble des fonctionnalités qui se trouvent actuellement `Insiders` dans l’ensemble de fonctionnalités et sont donc prêtes à être évaluées une fois que vous avez modifié le paramètre susmentionné:



## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](platform-support.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
