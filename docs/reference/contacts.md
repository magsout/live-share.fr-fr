---
title: Présence-Visual Studio Live Share | Microsoft Docs
description: Informations sur le service de présence pour les contacts pour Visual Studio Live Share.
ms.custom: ''
ms.date: 10/08/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: b95e5f837d044b2b069f73478da40461268bdf3d
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170002"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="contacts-in-live-share"></a>Contacts dans Live Share 

Vous avez donc utilisé Live Share et vous remarquez que l’envoi de liens par le biais d’une application externe (par exemple, conversation ou courrier électronique) peut devenir l’ancien vraiment rapide ? Nous savons que si nous souhaitons encourager la collaboration, vous devez avoir le moins de frottement possible pour que vous l’aimeriez. C’est pour cette raison que Live Share a maintenant des **contacts** avec l' **État** .

>Les contacts seront automatiquement activés pour toutes les versions de **Live share v 1.0.950** .

Les contacts s’affichent dans la fenêtre de Live Share sous la forme d’un volet distinct, comme illustré dans l’image ci-dessous : 

![Contacts](../media/vscode-contacts-intro.png)

<em>Indication du volet contacts dans la fenêtre Live Share</em>
## <a name="who-shows-up-in-my-contacts"></a>Qui apparaît dans mes contacts ?

Le volet contacts affiche deux types de contacts qui prennent en charge les flux de travail naturels des développeurs.
### <a name="1-recent-contacts"></a>1. contacts récents  
 Il s’agit des développeurs que vous avez déjà collaboré avec Live Share. Dans la pratique, la plupart des développeurs collaborent souvent avec les mêmes personnes et, par conséquent, la liste récente permet un moyen plus reproductible de travailler avec votre équipe/salle de classe/etc.
### <a name="2-suggested-contacts"></a>2. contacts suggérés
Il s’agit de développeurs qui ont contribué à votre projet actuellement ouvert au cours des 30 derniers jours. Dans la pratique, il s’agit des personnes avec lesquelles vous êtes susceptible de vouloir collaborer. par conséquent, nous vous suggérons de les suggérer afin de faciliter la prise en main.

## <a name="direct-user-invitations"></a>Invitations de l’utilisateur direct 
Tous vos contacts peuvent être invités directement dans une session de Live Share à partir de votre éditeur. Ils recevront une notification de Toast qui leur donne la possibilité de rejoindre la session. Cela élimine la nécessité d’échanger des URL de session entièrement.
![DirectInvitationVSCode](https://user-images.githubusercontent.com/51928518/66443914-e59c5d00-e9f5-11e9-957a-b1a92949d660.gif)
<em>un hôte Live Share (à gauche) qui invite directement un homologue (à droite) dans une session</em>

## <a name="how-does-status-for-contacts-work"></a>Comment le statut des contacts fonctionne-t-il ?
Une fois que les développeurs se connectent avec Live Share, **leur état de disponibilité est publié sur leurs pairs.** Par conséquent, vous pouvez voir que quelqu’un de votre équipe est en ligne, puis commencer immédiatement à collaborer avec eux, à l’aide d’une invitation directe, comme indiqué ci-dessus.
Votre état peut être défini directement à partir de l’éditeur pour vous permettre de vous signaler la disponibilité à votre équipe, sans avoir à passer par le changement de contexte. Les contacts Live Share ont actuellement 4 États :

**1. disponible :** votre état par défaut est `Available` si vous avez l’extension de Live Share et que vous utilisez activement votre éditeur, alors que vous n’êtes pas dans une session.

**2. ne pas déranger :** votre état est défini sur `Do not disturb` si vous êtes actuellement dans une session Live share active et que toutes les notifications d’invitation sont supprimées.

**3. absent :** après 5 minutes d’inactivité, votre état passe automatiquement à `Away`.

**4. offline :** vous êtes hors connexion une fois que vous êtes en déplacement pendant une période prolongée, ou si vous choisissez de [refuser l’état de partage](##ManagingPresence)


## Gestion des contacts et de<a name="ManagingPresence"> </a> l’état de partage

Si vous souhaitez désactiver cette fonctionnalité, vous pouvez le faire de deux manières.
1. Vous pouvez désactiver le paramètre d’État en choisissant d’être `offline`. Une fois désactivée, vous pouvez toujours voir l’état de l’autre et l’inviter, mais votre état n’est pas publié et d’autres personnes ne peuvent pas vous inviter directement.
Vous pouvez choisir de vous connecter en mode hors connexion en cliquant sur le cercle d’État qui affiche le menu déroulant suivant :

![dropdownstatus](../media/vscode-presence-opt-out.png)
<em>indiquant la liste déroulante des États de présence</em>

2. Vous pouvez ouvrir `user settings` et accéder à *Extensions > Visual Studio Live Share > Live share : présence* et désactiver le service de présence. Une fois désactivée, vous pouvez toujours voir l’état de l’autre et l’inviter, mais votre état n’est pas publié et d’autres personnes ne peuvent pas vous inviter directement.

![presencesettings](../media/vscode-presence-setting.png)

## <a name="faqs"></a>FAQ 

###### <a name="1-will-i-be-automatically-opting-into-sharing-status-when-i-use-live-share-v10950-and-above"></a>1. dois-je automatiquement opter pour le partage de l’État lorsque j’utilise Live Share v 1.0.950 et versions ultérieures ?

La première fois que vous voyez des contacts, vous êtes averti avec un toast et une option vous permettant de refuser le partage de votre statut. Après cela, vous allez automatiquement partager votre statut avec vos contacts, sauf si vous choisissez de le désactiver comme indiqué ci-dessus.

###### <a name="2-can-i-add-my-own-contacts"></a>2. puis-je ajouter mes propres contacts ?

Actuellement, notre service de contacts détecte automatiquement les collaborateurs auxquels vous partagez fréquemment du code ou qui travaillent sur le côté, et ne vous offre pas la possibilité d’ajouter vos propres contacts. 


>Vous pensez être en mesure d’ajouter manuellement des contacts ? Aidez-nous à classer par ordre de priorité en ouvrant une demande de fonctionnalité GitHub [ici.](https://github.com/MicrosoftDocs/live-share/issues/new?template=feature_request.md)
 

 