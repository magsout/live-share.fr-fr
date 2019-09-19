---
title: Travailler en collaboration à l’aide de Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Une série de guides pratiques de collaboration pour Visual Studio Code et Live Share.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fishah
ms.author: fishah
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: 4ed24b7c73767086e5b44909dd958c174b4f3398
ms.sourcegitcommit: ee0d569c893c2a89374026fe7df70fa3027eac1a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117906"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Procédure : Effectuer des entretiens techniques à l’aide de Live Share

Avant de commencer à utiliser Live Share pour les entretiens techniques, vous devez effectuer une étape intégrale : **Téléchargez Visual Studio et le pack d’extension Live share à partir de la place de marché** en procédant comme [suit.](../use/vscode.md#Installation)

Live Share vous offre la possibilité d’héberger des sessions réutilisables ! Cela signifie que vous pouvez planifier une session de Live Share à l’avance pour vos entretiens techniques et ne vous inquiétez pas du lien arrivant à expiration.

> [!TIP] 
>Un lien de session réutilisable est persistant et dure 30 jours à partir de sa date de création ou de la date de dernière utilisation. Lors de la génération d’un lien de session réutilisable pour votre entretien, assurez-vous que l’entretien se situe dans un délai de 30 jours à compter de la date de création du lien. Si le lien expire, il vous suffit de créer une nouvelle session réutilisable. (Il existe un moyen de garantir que le lien n’expire jamais, mais cela est tout simplement plus facile pour les entretiens !)

### <a name="what-to-do-as-an-interviewer"></a>**Que faire en tant qu’interviseur ?**

En tant qu’interviseur, vous jouerez le rôle d’hôte de la session de Live Share. Si vous n’êtes pas familiarisé avec Live Share, nous vous suggérons de consulter la section [partager un projet](../use/vscode.md) de notre guide de procédures.

Maintenant, pour créer une session Live Share pour votre entretien technique, vous allez créer une « session réutilisable » spéciale au lieu de la session de collaboration normale. Cela vous permettra d’avoir une session de Live Share qui peut être planifiée à l’avance, puis utilisée à tout moment.

Pour créer une session réutilisable, procédez comme suit :

1. Accédez à l' `Command Palette` utilisation`Ctrl+Shift+P`
1. Tapez « SHA Live... » et cliquez sur le **_Live share : Commande de création d’une_liaison**de session réutilisable».

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Cette opération crée une session réutilisable et un lien vers celle-ci est copié dans le presse-papiers. Une fenêtre contextuelle de notification s’affiche dans l’angle inférieur droit de votre éditeur.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. Votre session réutilisable a été créée. Partagez le lien avec votre session et utilisez-le chaque fois pour accéder à la session !

Une fois que vous disposez de ce lien, il vous suffit de le partager avec l’interviseur par courrier électronique ou par le biais de votre choix de mécanisme de planification. Il suffit de cliquer sur ce lien au moment de l’entretien pour qu’ils se trouvent dans une session de Live Share. 

### <a name="what-to-do-as-the-interviewee"></a>**Que faire en tant qu’interviseur ?**

Si vous prévoyez d’effectuer un entretien technique à l’aide de Live Share, vous avez la chance ! Nous voulons nous assurer que vous êtes familiarisé avec les fonctionnalités de base de Live Share, afin de vous sentir à l’aise au cours de votre entretien.

1. Avant l’entretien, prenez du temps et examinez le [Guide](../use/vscode.md) pratique pour comprendre comment Live share fonctionne.

1. Vous souhaiterez peut-être installer Visual Studio Code au préalable afin de ne pas attendre la fin de l’installation une fois que vous avez démarré votre entretien

1. Si vous n’avez pas le temps, pas de soucis. Tout ce dont vous avez besoin pour un entretien complet est le lien vers une session de Live Share que votre interviseur vous envoie lors de la planification de l’entretien. Cliquez simplement sur le lien pour accéder automatiquement à toutes les étapes nécessaires.

1. Au moment de l’entretien, cliquez simplement sur le lien et suivez les étapes qu’il vous faut. Si vous êtes tôt ou si votre interviseur est tard, ne vous inquiétez pas ! Vous ne serez qu’en attente de connexion de votre interviseur. Aucune autre étape n’est requise, et une fois que votre interviseur rejoint la session démarre automatiquement.

>[!NOTE]
>Si vous constatez que la session s’est déconnectée avant ou après la jonction de l’interviseur, ne vous inquiétez pas. Quittez cette session si (elle n’est pas déjà fermée) et recliquez sur le même lien !

Vous êtes maintenant prêt à utiliser Live Share pour votre entretien ! 
