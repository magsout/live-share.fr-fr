---
title: Jointure à partir du navigateur-Visual Studio Live Share | Microsoft Docs
description: Présentation de la jointure à partir du navigateur transmet
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 741292a3df8b86a8f7a9484875b352ebe6e8ec10
ms.sourcegitcommit: 382f069abbd81ed258d497a974b30379be36b4f0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "79510624"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Préversion] ✨ rejoindre une session Live Share à partir du navigateur

Toutes les sessions de collaboration Live Share ont désormais la possibilité d’être jointes au navigateur. Cela signifie qu’un invité à votre session n’a plus besoin d’installer VS Code ou Visual Studio pour rejoindre votre session. Cela s’avère particulièrement utile pour toutes ces instances lorsque vous souhaitez que quelqu’un puisse rapidement accéder à votre session, ou pour les élèves qui n’ont pas les clients de bureau.

> [!TIP]
> Consultez notre section FAQ ci-dessous pour connaître les questions les plus courantes sur la jointure à partir du navigateur.

# <a name="how-to-join-a-live-share-session-from-the-browser"></a>Comment joindre une session de Live Share à partir du navigateur 

### <a name="1-host-starts-session"></a>1. hôte : démarre la session 
Pour commencer, l’hôte doit accéder à Visual Studio ou VS Code pour démarrer une session de collaboration. Lorsque l’hôte partage un dossier ou un projet.

![Animation de démarrage de la session](https://user-images.githubusercontent.com/51928518/76938928-b814e300-68b4-11ea-923e-cefabd4688c6.gif)

### <a name="2-guest-uses-shared-link-to-join-from-browser"></a>2. invité : utilise un lien partagé pour rejoindre le navigateur 
Live Share générera un lien de jointure qui peut être partagé avec l’invité. L’invité peut maintenant utiliser ce lien pour accéder à une page Web, qui lui donne maintenant la possibilité de continuer le navigateur.

![Animation de jointure d’une session](https://user-images.githubusercontent.com/51928518/76941137-b8af7880-68b8-11ea-8228-41fdf4afd3ef.gif)

### <a name="3-guest-enjoys-full-fidelity-collaboration-experience-from-browser"></a>3. invité : bénéficie d’une expérience de collaboration fidèle à partir du navigateur 
Une fois que l’invité a rejoint la session, il peut se comporter comme s’il travaillait sur les clients de bureau.

![Animation de fidélité complète](https://user-images.githubusercontent.com/51928518/76942009-40e24d80-68ba-11ea-885c-6eb1069ed550.gif)
# <a name="frequently-asked-questions"></a>Forum aux questions 

##### <a name="1-is-there-an-environment-running-in-the-background-that-is-hosting-my-session-in-the-browser"></a>1. existe-t-il un environnement en cours d’exécution en arrière-plan, qui héberge ma session dans le navigateur ?
Quand vous joignez une session Live Share à partir du navigateur, aucun nouvel environnement n’est lancé. Il s’agit d’un service sans serveur. 
##### <a name="2-do-i-have-to-pay-for-the-service-of-joining-from-the-browser"></a>2. dois-je payer pour le service de jointure à partir du navigateur ?
La jointure à partir du navigateur est gratuite, à l’instar de toutes les Live Share.

##### <a name="3-how-is-this-different-from-visual-studio-online"></a>3. en quoi cela diffère-t-il de Visual Studio Online ?
Lorsque vous vous joignez à partir du navigateur, vous accédez uniquement au client VS Code à partir du navigateur pendant la session. Une fois la session terminée, tous les fichiers et dossiers ainsi que les fonctionnalités de l’éditeur se ferment. Pour utiliser un éditeur dans le navigateur, avec votre propre environnement pour modifier vos propres fichiers, vous devez utiliser [Visual Studio online.](aka.ms/vso)

##### <a name="4-does-this-work-for-all-browsers"></a>4. cela fonctionne-t-il pour tous les navigateurs ?
Oui. Cela fonctionne sur tous les navigateurs. 
##### <a name="5-is-there-a-vs-client-that-i-can-use-in-the-browser"></a>5. existe-t-il un client VS que je peux utiliser dans le navigateur ?
Cette opération n’est pas encore disponible. 

# <a name="feedback-and-issues"></a>Commentaires et problèmes 
Il s’agit d’une fonctionnalité en version préliminaire qui nous permet d’obtenir des commentaires de l’utilisateur pour améliorer l’expérience. Veuillez remplir les commentaires ou les problèmes que vous voyez sur notre référentiel GitHub [ici.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)