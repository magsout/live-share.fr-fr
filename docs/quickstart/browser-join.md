---
title: Jointure à partir du navigateur-Visual Studio Live Share | Microsoft Docs
description: Présentation de la jonction à partir du navigateur
ms.date: 03/18/2020
ms.reviewer: ''
ms.suite: ''
ms.topic: quickstart
author: fishah
ms.author: fishah
manager: joncart
ms.workload:
- liveshare
ms.openlocfilehash: 5e485397ff23be0fdab8449fad6237d829775c55
ms.sourcegitcommit: d7f923c1bcd0430b48065ea2c0902b470f530987
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83569533"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="preview-joining-a-live-share-session-from-the-browser"></a>✨ [Préversion] ✨ rejoindre une session Live Share à partir du navigateur

Toutes les sessions de collaboration Live Share ont désormais la possibilité d’être jointes à partir du navigateur. Cela signifie qu’un invité à votre session n’a plus besoin d’installer VS Code ou Visual Studio pour rejoindre votre session. Cela s’avère particulièrement utile pour toutes ces instances lorsque vous souhaitez que quelqu’un puisse rapidement accéder à votre session, ou pour les élèves qui n’ont pas les clients de bureau.


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

<!---
# Frequently asked questions 

##### 1. Is there an environment running in the background, that is hosting my session in the browser?
When you join a Live Share session from the browser, there is no new environment spun up. It is a serverless service. 
##### 2. Do I have to pay for the service of joining from the browser?
Joining from the browser is free, much like all of Live Share.

##### 3. How is this different from Visual Studio Online?
When you join from the browser, you only access the VS Code client from the browser during the session. Once the session ends, all the files and folders along with editor capabilities will close. To use an editor in the browser, backed with your own environment to edit your own files, you must use [Visual Studio Online.](aka.ms/vso)

##### 4. Does this work for all browsers?
Yes. This works on all browsers. 
##### 5. Is there a VS client that I can use in the browser?
We do not have this available yet. 

# Feedback and issues 
This is a preview feature, and we hope to get user feedback to improve the experience. Please fill out any feedback or issues you see on our GitHub repo [here.](https://github.com/MicrosoftDocs/live-share/issues/new?template=bug_report.md)

--->
