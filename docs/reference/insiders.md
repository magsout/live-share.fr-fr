---
title: Insiders - partage en direct de Visual Studio | Microsoft Docs
description: Description du canal « Initiés » au sein de partage en direct de Visual Studio.
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
ms.openlocfilehash: a79effc25c09851301bb2231511a8a9d8a9f549b
ms.sourcegitcommit: 6e84bf17eedd616417f474551344c2161700c4d3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67192724"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="insiders"></a>Membres du programme Insider

L’équipe le Partage Live Visual Studio essaie d’itérer rapidement dans l’ordre pour répondre aux besoins utilisateur, et ce cadre, nous proposons deux fonction distincte « canaux » vous permettent de déterminer la vitesse à laquelle vous recevez les nouvelles fonctionnalités. Par défaut, après avoir installé l’extension de le Partage Live Visual Studio, vous utilisez la `Stable` ensemble, ce qui inclut toutes les fonctionnalités de prêt pour la production (par exemple, même modification, partagé débogage, terminaux) des fonctionnalités. Toutefois, si vous souhaitez obtenir un accès précoce aux fonctionnalités que nous travaillons, vous pouvez participer à la `Insiders` ensemble de fonctionnalités en modifiant le paramètre suivant dans votre IDE :

* Visual Studio

    ![set-fonctionnalité-vs](../media/feature-set-vs.png)

* Visual Studio Code 

    ![feature-set-vscode](../media/feature-set-vscode.png)

Les sections suivantes décrivent l’ensemble de fonctionnalités qui se trouvent actuellement dans le `Insiders` ensemble de fonctionnalités et par conséquent, êtes prêt à évaluer une fois que vous modifiez le paramètre mentionnés ci-dessus :

## <a name="direct-user-invitations"></a>Invitations d’utilisateurs directe

Actuellement, Visual Studio et Visual Studio Code fournissent un `Contacts` volet, ce qui permet les deux fonctions principales :

1. Affiche une liste de `Suggested Contacts`, qui sont les développeurs qui ont contribué à votre projet actuellement ouvert dans les 30 derniers jours. Dans la pratique, il s’agit de l’équipe que vous êtes susceptible de vouloir collaborer avec, et par conséquent, nous vous suggérons les afin de faciliter la prise en main.

2. Fournir la liste des `Recent Contacts`, qui sont des développeurs avec lesquelles vous avez précédemment collaboré à l’aide de partage en direct. Dans la pratique, la plupart des développeurs collaborent souvent avec les mêmes personnes, et par conséquent, la liste des derniers permet un moyen plus répétable de travailler avec votre équipe/la classe/etc.

Toutefois, le `Contacts` liste actuellement uniquement vous permet d’inviter des contacts récents/suggérés par courrier électronique, ce qui nous en avons appris n’est pas aussi efficace que possible. Si vous installez la dernière mise à jour du partage Live et activez `Insiders` (comme décrit ci-dessus), vous allez maintenant être en mesure de **invitation de développeurs dans une session de collaboration directement à partir de l’IDE**! Notez que si vous utilisez Visual Studio Code, vous devez installer le [Insiders Build](https://code.visualstudio.com/insiders/) afin que cette fonctionnalité soit opérationnelle.

![Invitatiosn directe](https://user-images.githubusercontent.com/116461/59691804-7ece0c00-9198-11e9-94fb-99ec89df91c9.gif)

<em>Un hôte de partage en direct (à gauche) inviter directement un homologue (à droite) dans une session</em>

Une fois que les développeurs connectez-vous avec le partage en direct, leur état de disponibilité sera publiée à leurs homologues. Par conséquent, vous pouvez voir qu’une personne de votre équipe est en ligne et puis immédiatement commencer à collaborer avec eux. Ils obtiendront une notification toast qui leur donne la possibilité de participer la session ou non. Cette opération supprime le besoin d’échanger des URL de la session entièrement.

Après 5 minutes d’inactivité, votre statut passe automatiquement à `Away`, et lorsque vous êtes dans une session de partage en direct, votre état bascule automatiquement sur `Do not disturb` (notifications toast quels suprresses invitation). Une fois que vous redevient active ou quittez une session de partage en direct, votre état bascule automatiquement vers `Available`. Avec ce comportement, vous n’avez pas besoin de gérer l’état de votre partage Live. Il est simplement là pour activer les invitations directes et communiquer avec vos pairs si vous êtes disponible pour la collaboration ou non. Toutefois, vous pouvez définir toujours manuellement votre statut si vous préférez.

Si vous souhaitez refuser de cette fonctionnalité, vous pouvez simplement désactiver le `Presence` définissant les paramètres de partage en direct dans Visual Studio et Visual Studio Code. Une fois désactivé, vous serez toujours en mesure de voir l’état de l’autre et de les inviter, mais ne sera pas publié votre état, et d’autres utilisateurs ne peuvent pas directement vous inviter.

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](platform-support.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
