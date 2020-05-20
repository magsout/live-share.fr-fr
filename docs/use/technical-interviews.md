---
title: Travailler en collaboration à l’aide de Visual Studio Code – Visual Studio Live Share | Microsoft Docs
description: Une série de guides pratiques de collaboration pour Visual Studio Code et Live Share.
ms.custom: ''
ms.date: 09/16/2019
ms.reviewer: ''
ms.suite: ''
ms.topic: conceptual
author: fubaduba
ms.author: fubaduba
manager: JonathanCarter
ms.workload:
- liveshare
ms.openlocfilehash: db2365b92f5b18198a2f976e1c6ce3d5abb755c5
ms.sourcegitcommit: d7f923c1bcd0430b48065ea2c0902b470f530987
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83569520"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="how-to-do-technical-interviews-using-live-share"></a>Comment : effectuer des entretiens techniques à l’aide de Live Share

L’utilisation de Live Share pour les entretiens permet à l’interviseur et au candidat d’avoir une session d’entretien rapide et fiable, avec un IDE ou un éditeur complet-Fidelity. 


## <a name="setup-for-interviewer"></a>Configuration de l’interviseur 
Pour interviewer un candidat avec Live Share vous devez d’abord utiliser l’un des deux clients de bureau :

Installer [Visual Studio](../use/vs.md) qui est intégré à l’extension Live share

>[!TIP] 
> Veillez à activer les Insiders pour Live Share en accédant à *outils> Options > Live Share > fonctionnalités > avancées*. Cela vous permettra d’utiliser la prise en charge de l’appel audio intégré pour les entretiens.

Ou installez [Visual Studio code](../use/vscode.md) et téléchargez le [pack d’extension Live share](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) à partir de la place de marché. Le pack d’extension vous fournira la prise en charge audio pour les entretiens. 

## <a name="scheduling-an-interview"></a>Planification d’un entretien 

**Live share dans vs code** vous permet de créer des sessions Live shares à l’avance. Vous pouvez utiliser les étapes suivantes pour créer une session à l’avance :

1. Accédez à l' `Command Palette` utilisation`Ctrl+Shift+P`
1. Tapez « SHA Live... » et cliquez sur la commande «_Live share : créer un lien de session réutilisable_».

![vscode-reusablesessioncmd](../media/vscode-cmdpalette-createreusablelink.png)

3. Cette opération crée une session réutilisable et un lien vers celle-ci est copié dans le presse-papiers. Une fenêtre contextuelle de notification s’affiche dans l’angle inférieur droit de votre éditeur.

![vscode-reusablesessionnotif](../media/vscode-notification-resuablesession.png)

4. envoyez le lien.

Une fois que vous disposez de ce lien, il vous suffit de le partager avec l’interviseur par courrier électronique ou par le biais de votre choix de mécanisme de planification. Il suffit de cliquer sur ce lien au moment de l’entretien pour qu’ils se trouvent dans une session de Live Share. 
> [!TIP] 
>Un lien de session réutilisable est persistant et dure 30 jours à partir de sa date de création ou de la date de dernière utilisation. Lors de la génération d’un lien de session réutilisable pour votre entretien, assurez-vous que l’entretien se situe dans un délai de 30 jours à compter de la date de création du lien. Si le lien expire, il vous suffit de créer une nouvelle session réutilisable. (Il existe un moyen de garantir que le lien n’expire jamais, mais cela est tout simplement plus facile pour les entretiens !)

**Remarque :** Actuellement, Live Share dans Visual Studio n’a pas la possibilité de créer des sessions à l’avance. Pour les entretiens que vous effectuez à l’aide de Live Share dans Visual Studio, vous pouvez suivre notre guide sur la façon de démarrer une session de Live Share instantanée [ici](../quickstart/share.md)



## <a name="setup-for-candidate"></a>Configuration du candidat
Bien qu’un candidat puisse toujours installer Visual Studio ou Visual Studio Code pour rejoindre l’entretien, il n’a pas besoin de le faire. **Live Share sessions d’entretien peuvent être jointes par des candidats sans aucune configuration antérieure.** Ils peuvent cliquer sur le lien de l’entretien au moment de la session et se **joindre à partir du navigateur**. Pour en savoir plus [, cliquez ici.](../quickstart/browser-join.md)



<!--
### **What to do as an Interviewer?**

As an interviewer you will act as the host of the Live Share session. If you are not familiar with Live Share, we suggest you refer to the [share a project](../use/vscode.md) section of our how-to guide
### **What to do as the Interviewee?**

If you are expecting to do a Technical Interview using Live Share, you are in luck! We want to make sure you are familiar with the basic Live Share features so you feel comfortable during your interview.

1. Before the interview, take some time and look over the [How-to guide](../use/vscode.md) so you understand how Live Share works.

1. You may want to install Visual Studio Code beforehand so that you are not waiting for the installation to complete once you start your interview

1. If you don't have the time, no worries. All you need to have a full interview is the link to a Live Share session your interviewer sends you while scheduling the interview. Just clicking on the link will automatically take you through all the steps needed.

1. At the time of the interview, just click on the link and follow the steps it takes you through. If you are early or your interviewer is late to the interview, don't worry! You will just be in the 'lobby' waiting for your interviewer to join. No other steps are required, and once your interviewer joins the session will automatically start.

>[!NOTE]
>If you find that the session has disconnected before or after the interviewer joined, don't worry. Just exit out of that session if (it isn't already closed) and re-click on the same link!

You are now all set to go with using Live Share for your interview! 
-->
