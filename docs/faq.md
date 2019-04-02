---
title: FAQ - partage en direct de Visual Studio | Microsoft Docs
description: Forum aux questions sur le partage en direct de Visual Studio.
ms.custom: ''
ms.date: 05/05/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 1b68dc90f4bac5e21c04c555ab2d8fc7f59aad55
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58853597"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="frequently-asked-questions"></a>Questions fréquemment posées

## <a name="what-is-live-share"></a>Quel est le partage en direct ?
Live Share vous permet d’éditer et de déboguer en collaboration avec d’autres utilisateurs en temps réel, quels que soient les langages de programmation que vous utilisez ou les types d’applications que vous créez. Il vous permet (instantanément et en toute sécurité) qui partagent votre projet actuel et partager ensuite selon les besoins, les sessions de débogage, les instances de terminal, les applications web localhost et bien plus encore ! Les développeurs qui joignent vos sessions bénéficiez de l’ensemble de leur contexte de l’éditeur à partir de votre environnement (par exemple, services de langage, le débogage), ce qui garantit qu’ils puissent commencer productive collaborer immédiatement, sans devoir cloner les dépôts ou installer des kits de développement logiciel.

## <a name="what-are-the-tooling-requirements-for-using-live-share"></a>Quelles sont les exigences d’outils pour l’utilisation dynamique de partage ?
Le [fonctionnalités principales](#what-are-the-core-capabilities-of-live-share) de partage en direct sont entièrement pris en charge dans les outils suivants :

* [Visual Studio 2019](https://visualstudio.microsoft.com/vs/)
* [Visual Studio 2017 15.6 +)](https://visualstudio.microsoft.com/vs/older-downloads/)
* [Visual Studio Code](https://code.visualstudio.com/)

Nous itérer rapidement pour répondre aux commentaires des utilisateurs. Cela nous oblige à tirer parti des fonctionnalités dans Visual Studio et Visual Studio Code sont uniquement accessibles dans leurs versions preview/insider respectifs. Nous indiquons les fonctionnalités qui nécessitent des versions plus récentes de Visual Studio ou VS Code dans la documentation. Par exemple, prise en charge de l’annulation/de rétablissement local nécessite Visual Studio 2017 15.7 +.

## <a name="what-are-the-core-capabilities-of-live-share"></a>Quelles sont les principales fonctionnalités de partage en direct ?
Partage en direct vous permet de partager votre base de code avec les membres de votre équipe via une connexion sécurisée. Avec le partage en direct, vous êtes en mesure de plusieurs fichiers dans un espace de travail de manière collaborative et plus important encore de déboguer votre application avec vos collègues. Pendant la même modification vos modifications sont immédiatement visibles par vos collègues. Au cours du même emplacement de débogage vous partagent la même session de débogage de votre application. Cela signifie que vous et vos coéquipiers peuvent contrôler l’exécution du programme avec des points d’arrêt et des étapes, mais vous pouvez inspecter indépendamment REPLs (par exemple, la fenêtre exécution dans Visual Studio), les espions, les variables locales et les variables.

Partage en direct a un grand nombre de cas d’utilisation tels que : examen un bogue ensemble, indiquant un problème qui ne sont pas de reproduire le problème sur l’ordinateur d’une autre personne, résolution conception émet, paire de programmation et à réaliser un entretien de codage, encadrement des autres membres d’une équipe ou l’exécution révisions du code d’ad-hoc.

## <a name="by-using-live-share-is-my-code-stored-on-a-microsoft-server"></a>À l’aide de partage en direct, est mon code stocké sur un serveur de Microsoft ?
Non, le code partagé réside uniquement sur l’ordinateur du développeur qui a initié le partage. Il n’est pas stocké ou téléchargé vers le cloud en aucune façon. Au lieu de cela, Live partage simplement établit une connexion sécurisée entre vous et vos coéquipiers (qui est chiffré de bout en bout) et n’inspecter ou collecter des données sur le code qui est partagé.

## <a name="does-this-remote-based-model-work-anywhere-is-it-peer-to-peer"></a>Ce modèle basé sur à distance fonctionne en tout lieu ? Est-il peer-to-peer ?
Constitue la seule exigence du partage en direct est que la personne qui partage et son collègue ont accès à internet. Sécuriser la communication entre les membres de l’équipe pendant une session de collaboration est facilitée par un relais Azure. Votre espace de travail (autrement dit, les fichiers sources) n’est pas stockée dans le cloud. Aucune connexion de peer-to-peer spéciale est requise même si une peut être utilisée pour réduire la latence. Consultez [modifier le mode de connexion](https://aka.ms/vsls-docs/connection-mode) dans notre documentation pour plus d’informations.

## <a name="what-is-shared-during-a-live-share-session"></a>Ce qui est partagé pendant une session de partage en direct ?
Partage en direct ne transfère pas toutes les entrées clavier et souris. Il communique uniquement les données nécessaires pour chaque activité de collaboration pour les ordinateurs de vos collègues. Par exemple, lorsque vous partagez votre espace de travail, votre structure de dossier est partagé. Lorsque vous modifiez en collaboration un fichier, que le contenu du fichier est partagés. Lorsque vous effectuez un débogage en collaboration, actions de débogage (par exemple, exécution pas à pas) et l’état (par exemple, pile des appels et variables locales) sont partagées.

## <a name="when-will-live-share-be-released"></a>Quand Partage Live sera-t-il disponible ?
Partage en direct est désormais disponible ! Vous pouvez [prise en main Partage Live](https://aka.ms/vsls-start) dès aujourd'hui.

## <a name="how-much-will-it-cost"></a>Combien cela coûte-t-il ?
Nous nous engageons à un niveau gratuit au fond de Visual Studio Live Share pour les développeurs à utiliser en continu. Nous sera évalué l’introduction des niveaux payants avec des fonctionnalités avancées que nous comprenons mieux les besoins de la Communauté.

## <a name="how-is-my-code-shared-with-other-teammates"></a>Comment mon code est partagé avec d’autres collègues ?
Lorsque vous utilisez le partage en direct, que vous faites le code que vous travaillez actuellement disponibles telles que vos collègues puissent y accéder via un service cloud sécurisé qui commandes de bases de données distantes à partir de votre éditeur. Vos collègues peuvent ouvrir et modifier les fichiers sans avoir à les stocker dans le cloud ou les stocker en permanence sur l’ordinateur de votre coéquipier.

Partage en direct offre un accès immédiat à des fonctionnalités telles que l’arborescence du projet, la navigation dans le code et la recherche. Il permet également de vos collègues tirer parti des améliorations de l’éditeur telles qu’IntelliSense.

## <a name="what-happens-if-a-user-goes-offline-or-stops-sharing"></a>Que se passe-t-il si un utilisateur se déconnecte ou arrête le partage ?
Le modèle à distance requiert que le développeur de partage par le biais de partage en direct et son collègue doit être en ligne pour être connecté. Si votre collègue tente d’utiliser Partage Live lorsque vous êtes hors connexion, ils ne pourront pas rejoindre la session jusqu'à ce que vous êtes en ligne. En outre, une fois s’arrête de collaboration (par exemple, vous fermez votre éditeur, passez en mode hors connexion ou arrêtez le partage), puis les actions ou l’accès de fichier par vos collègues sont immédiatement désactivé.

## <a name="what-about-screen-sharing"></a>Qu’en est-il de partage d’écran ?
Partage en direct vous permet de partager le code de votre projet et son contexte. Cela signifie que votre collègue peut accéder à votre base de code et de travailler facilement avec vous, à l’aide de leur outil familier. Votre éditeur ou autres applications ne sont pas partagés ou visibles par votre collègue et vous n’êtes pas obligé de modifier votre méthode de travail ou utiliser une application basée sur le web.

Partage en direct ne remplace pas le partage d’écran où vous souhaiterez afficher un élément de menu ou traitent des aspects visuels de votre application ou votre éditeur. Au lieu de cela, vous avez la possibilité d’utiliser Partage Live, ainsi que la conversation instantanée, voix, vidéo et partage d’écran.

## <a name="what-about-other-collaboration-tools"></a>Qu’en est-il des autres outils de collaboration ?
Partage en direct peut être utilisé avec chat, messagerie instantanée ou les technologies de messagerie. Nous avons observé que les nombreuses interactions de collaboration entre les développeurs démarrent dans ces outils. Toutefois, lors de la discussion concerne le code, ils obtiennent souvent à un point où il est simplement trop difficile à expliquer un problème avec les fichiers texte, des extraits de code ou uniques - plus de contexte est nécessaire.

Partage en direct peut être utilisé pour de nombreux éléments, tels que : recherche d’aide sur un problème, la résolution d’un bogue, paire de programmation, effectuer un codage entretien ou l’exécution ad hoc étudier avec une validation de code ou d’une demande de tirage.

## <a name="what-about-other-web-editors"></a>Qu’en est-il des autres éditeurs web ?
Avec les éditeurs basée sur le web, les deux collègues doivent utiliser la même application web afin de tirer profit de collaboration, qui peut être pas leur éditeur principal, quotidienne. De nombreux éditeurs basée sur le web supposent que vous générez et déployez dans une Machine virtuelle souvent hébergée dans un environnement de cloud.

Si cela peut être souhaitable dans de nombreux scénarios, les développeurs souhaitent souvent de collaborer sur des applications qui ne sont pas hébergées dans une machine virtuelle ou dans le cloud.  Avec le partage en direct, vous et votre collègue peuvent utiliser les fonctionnalités de l’écosystème d’outils en plus les mêmes fonctionnalités disponibles dans les éditeurs basés sur le web.

Partage en direct va une étape plus loin et vous permet de partager une session de débogage.  Cela rend particulièrement utile dans l’inscription d’autres pour vous aider à identifier les problèmes qui ne se produisent sur votre ordinateur sans modifier leur flux de travail de développement, ni avoir à modifier la conception de l’application.

## <a name="which-languages-and-platforms-will-be-supported"></a>Les langages et les plateformes sont prises en charge ?
Notre objectif est de prendre en charge le paysage de divers langages et plateformes, afin de que nous pouvons bénéficier d’une collaboration riche, quel que soit le type d’application en cours de développement. Consultez le [langage et plateforme prise en charge](reference/platform-support.md) article pour plus d’informations sur ce qui fonctionne aujourd'hui.

## <a name="how-many-developers-can-join-a-collaboration-session"></a>Combien de développeurs permettre rejoindre une session de collaboration ?
Nous prenons en charge 30 invités simultanées, le développeur qui partage (« hébergement ») en plus de leur projet. Par défaut, nous activons invités jusqu'à 5 dans une session. 

Pour activer la limite de l’invité accrue : 
- **VS Code :** Ajoutez « liveshare.increasedGuestLimit":"true » à settings.json.
- **VISUAL STUDIO :** Définir des outils > Options > Partage Live > augmentation de la limite invité sur « True »

## <a name="what-is-the-roadmap"></a>Quelle est la feuille de route ?
Vous pouvez afficher l’ensemble des problèmes connus et éléments de la feuille de route [ici](https://aka.ms/vsls-issues). Si vous souhaitez voir les demandes de fonctionnalités uniquement, plutôt que tous les problèmes, consultez [ici](https://aka.ms/vsls-feature-requests). Nous vous encourageons à voter pour des éléments existants, demandes de nouvelles fonctionnalités de fichiers et enregistrer des rapports de bogues, afin de nous aider à la direction du produit plus tard, de forme.

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langage et plateforme](platform-support.md)
- [Exigences de connectivité pour le partage en direct](reference/connectivity.md)
- [Fonctionnalités de sécurité de partage en direct](reference/security.md)
- [Tous les bogues majeurs, demandes de fonctionnalités et limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](troubleshooting.md) ou [fournir des commentaires](support.md).
