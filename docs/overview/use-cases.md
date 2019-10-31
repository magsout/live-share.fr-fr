---
title: Cas d’usage courants-Visual Studio Live Share | Microsoft Docs
description: Vue d’ensemble des cas d’usage que les développeurs tirent généralement parti de Visual Studio Live Share pour.
ms.custom: ''
ms.date: 05/21/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 0d328ad39b35ae1c6338825848857342765418d9
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73179875"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Cas d’usage courants

L’objectif principal de Visual Studio Live Share consiste à permettre aux développeurs de collaborer les uns avec les autres plus facilement, sans donner d’avis sur le moment et la façon de le faire (par exemple, l’outil de communication à utiliser, la méthodologie logicielle « appropriée » ou le flux de travail SCM). De cette façon, vos outils peuvent prendre en charge les interactions qui se produisent **naturellement**et aussi **souvent** que nécessaire, mais d’une **manière qui vous permet de mieux** travailler.

Ce document met en évidence certains cas d’usage pour lesquels Visual Studio Live Share est déjà utilisé, et décrit comment nous les prenons actuellement en charge, et comment nous prévoyons de les optimiser (en fonction des commentaires !). Si vous utilisez Live Share pour un objet qui n’est pas déjà abordé ci-dessous, ou si vous pensez que nous pouvons améliorer la prise en charge d’un cas d’usage spécifique, [faites-le nous savoir](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Assistance rapide](#quick-assistance)
    - [Heures Office](#office-hours)
- [Programmation de paires](#pair-programming)
    - [Programmation Mob](#mob-programming)
    - [Codage des concours/hack-A-thons](#coding-competitions--hack-a-thons)
    - [Projets School Group](#school-group-projects)
    - [Diffusion en continu pour les développeurs](#developer-streaming)
    - [Prototypage/création de projet](#prototyping--project-inception)
- [Enseignement interactif](#interactive-education)
    - [Encadrement/intégration de pairs](#peer-mentoring--onboarding)
    - [Sacs bruns de l’équipe](#team-brown-bags)
    - [Conférences en classe](#classroom-lectures)
- [Révisions du code](#code-reviews)
- [Entretiens techniques](#technical-interviews)

## <a name="quick-assistance"></a>Assistance rapide

Lorsque vous rencontrez un problème (par exemple, en essayant de résoudre un bogue, en configurant votre environnement), vous pouvez utiliser Visual Studio Live Share pour demander instantanément de l’aide d’un autre homologue. Dans de nombreux cas, il n’est pas immédiatement clair du contexte dont a besoin l’aide et, par conséquent, Live Share contribue à faciliter la fourniture d’un accès à l’ensemble de votre projet, et si/si nécessaire, partager de façon incrémentielle davantage (par exemple, un serveur local, en lecture seule Terminal). Vous n’avez pas besoin d’envoyer des extraits de code et/ou des messages d’erreur.

En outre, étant donné que Live Share vous permet de partager votre session de débogage active, sans exiger que les « invités » installent les kits de développement logiciel (SDK) de plateforme nécessaires (par exemple node. js, Go, .NET Core) ou les extensions d’outils, cela peut vous aider à obtenir une résolution plus rapide et à empêcher «ne pas reproduction sur mon ordinateur». Live Share vous permet de partager l’état de débogage avec d’autres utilisateurs, pour n’importe quel langage de programmation ou environnement d’exécution (par exemple, Kubernetes, réagi Native App) et, quelle que soit l’aide dont vous avez besoin, vous pouvez partager !

### <a name="office-hours"></a>Heures Office

De nombreuses entreprises et établissements scolaires (par exemple, des écoles, des cours de formation en ligne) fournissent un support à leurs clients/employés à des moments prédéterminés, et généralement sur une fréquence récurrente (par exemple, tous les vendredis de 3-5 PM). De cette façon, « les heures de bureau » sont simplement une forme planifiée d' « assistance rapide », par opposition à des informations entièrement ad hoc. Live Share facilite rapidement l’obtention d’aide, dans la mesure où le « spécialiste » qui fournit l’aide peut participer immédiatement à une session de collaboration et répondre à vos questions, sans avoir à configurer leur ordinateur.

## <a name="pair-programming"></a>Programmation de paires

L’un des scénarios les plus couramment utilisés pour Visual Studio Live Share est la « programmation par paire » : deux développeurs ou plus, qui travaillent ensemble sur une tâche partagée, avec l’objectif de partager les connaissances, d’augmenter la cohésion de l’équipe et, éventuellement, la qualité du produit. L’apparence exacte de la programmation de paires peut varier considérablement entre les équipes et les situations, en fonction des éléments suivants (entre autres) :

1. Portée de la « tâche » en cours de collaboration (par exemple, un bogue, un récit utilisateur)

1. Durée attendue de la session de collaboration (par exemple, deux minutes, une heure, une heure complète, une fois par semaine, TBD)

1. Le nombre de personnes impliquées (par exemple, deux, l’équipe entière)

1. Rôle de chaque participant (par exemple, « pilote », observateur/réviseur, expert en matière de domaine)

1. La proximité des participants (par exemple, colocalisés dans le même bâtiment, à travers le monde)

Live Share a été conçu pour être indépendant de tous les problèmes mentionnés ci-dessus, et à la place, s’efforce de prendre en charge la programmation de paires qui est complètement « opportuniste » et qui répond à votre situation. Cela dit, contrairement à deux développeurs partageant un seul clavier et écran, Live Share permet une forme de programmation par paire qui permet aux développeurs de travailler sur un objectif partagé, sans supprimer leurs préférences d’autonomie ou d’environnement. Vous pouvez travailler indépendamment, ou ensemble, pour permettre à chaque participant de faire de son propre processus de pensée à la collaboration.

Pour réduire encore davantage ce cas d’utilisation, les éléments suivants représentent des formes de programmation par paire que nous avons observé pour les gens qui utilisent Live Share pour :

### <a name="mob-programming"></a>Programmation Mob

La programmation [Mob](https://en.wikipedia.org/wiki/Mob_programming) (ou la programmation par essaim) est essentiellement couplée à la programmation, mais avec plus de deux personnes. Par conséquent, tous les avantages de Live Share pour la programmation par paire s’appliquent également également. En outre, certaines équipes effectuent un « essaimage » en fonction des besoins (par exemple, l’équipe rallying autour d’un exercice d’incendie) et non à plein temps.

Actuellement, Live Share prend en charge jusqu’à 30 invités au sein d’une session.
> [!TIP]
> Pour activer 30 invités dans une session :
> - **Vs code :** ajoutez « LiveShare. increasedGuestLimit » : « true » à Settings. JSON
> - **Vs :** Définir les options de > d’outils > Live Share > limite d’invités augmentée à « true » 

### <a name="coding-competitions--hack-a-thons"></a>Codage des concours/hack-A-thons

Les concours de codage et les attaques de type hack-a-thons sont des variations de la programmation Mob à bref terme et à tâche unique. Les membres de l’équipe et leur rôle actuel sont également potentiellement dynamiques. Dans la mesure où ce cas d’utilisation est généralement plus urgent, la possibilité de collaborer en temps réel sans avoir à adopter un outil entièrement nouveau, et la possibilité de travailler ensemble, sans être limité à un seul écran ou clavier, peut faire passer un journal à l’approche vélocité.

Étant donné que les participants de cet environnement peuvent ne pas toujours être entièrement « fiables », vous pouvez supprimer (et bloquer) un invité d’une session à tout moment. Cela offre aux « hôtes » un contrôle total sur leur environnement.

### <a name="school-group-projects"></a>Projets School Group

Les projets de groupe finissent par s’intéresser à une programmation Mob, où plusieurs élèves travaillent ensemble, et peuvent passer en toute transparence entre le focus sur une seule tâche ou travailler sur des tâches distinctes simultanément. Au lieu de s’appuyer simplement sur le contrôle de version pour collaborer de manière asynchrone, ils peuvent utiliser Live Share pour travailler ensemble en temps réel, ce qui peut contribuer aux avantages sociaux et de l’enseignement pour travailler dans un groupe.

### <a name="developer-streaming"></a>Diffusion en continu pour les développeurs

La diffusion en continu de développeurs (via Twitch ou mixer) est devenue une nouvelle forme d’éducation attrayante. Bien que Live Share ne soit pas destiné à remplacer leurs plateformes de diffusion (bien que nous ayons entendu parler de la demande), il permet à l’hôte de coupler le programme avec un ou plusieurs invités, puis de diffuser cette interaction. De cette façon, les visionneuses peuvent en apprendre davantage en regardant l’interaction naturelle et le processus de pensée de deux ou plusieurs développeurs, qui peuvent même travailler ensemble dans des systèmes d’exploitation et des IDE entièrement distincts.

### <a name="prototyping--project-inception"></a>Prototypage/création de projet

Lorsqu’une équipe démarre un nouveau projet/microservice ou prototypage/pics une nouvelle fonctionnalité, il peut souvent être utile de collaborer ensemble pour accélérer la progression et explorer de nouvelles idées. Étant donné que la base de code nouvellement créée peut ne pas encore être validée dans un référentiel partagé, Live Share permet à tout le monde de participer au processus itératif, qu’il soit ou non dans le même bureau.

## <a name="interactive-education"></a>Enseignement interactif

En règle générale, Live Share vise à aider les développeurs à partager des connaissances entre leur équipe. L’éducation est un cas d’utilisation fondamental pour Live Share, et elle prend en charge la plus particulièrement possible en permettant à chaque participant d’interagir avec le code base sur lequel la collaboration est effectuée, au lieu de simplement regarder un écran. Tout le monde apprend de manière subtile et, par conséquent, en fournissant une indépendance à un « étudiant », il est en mesure de tirer parti des instructions fournies, sans avoir à sacrifier leur capacité à explorer leurs propres idées en cours de route.

### <a name="peer-mentoring--onboarding"></a>Encadrement/intégration de pairs

Lors de l’introduction d’un développeur à un nouveau code base, fonctionnalité, technologie, etc., vous pouvez utiliser Live Share pour les guider dans le projet (à l’aide de `Follow Mode`), de façon à ce qu’ils puissent suivre avec vous, mais à partir de leur propre IDE personnel. Étant donné que Live Share permet aux « invités » de naviguer indépendamment dans le projet (par exemple, l’ouverture d’un fichier, l’exécution d’un `Peek Definition`), il peut suivre l’autorisation, mais également effectuer des explorations rapides si nécessaire (par exemple, « Hmm, que fait cette fonction ? »).

### <a name="team-brown-bags"></a>Sacs bruns de l’équipe

Les sacs bruns de l’équipe s’apparentent à l’encadrement des pairs, mais ils sont présentés à toute une équipe, et sont potentiellement plus concentrés sur la mise en pratique de connaissances généralement utiles, par opposition au support intégré et/ou à l’aide d’une tâche spécifique.

### <a name="classroom-lectures"></a>Conférences en classe

Quand les formateurs apprennent une leçon, ils peuvent utiliser Live Share pour partager leur projet avec les étudiants, au lieu de présenter simplement leur écran. Cela permet à la classe entière de suivre le professeur, tout en étant en mesure d’interagir avec le projet de manière autonome. En outre, l’enseignant peut demander aux étudiants individuels de vous aider à résoudre une partie spécifique de la leçon (par exemple, « quelle méthode dois-je appeler ici ? »), ce qui peut aider dans les aspects sociaux de la classe, sans qu’il soit nécessaire aux élèves d’aller au début de la salle. ou même être physiquement présent dans la même pièce (par exemple, des cours en ligne).

Pour faciliter les paramètres de la classe, Live Share permet le partage en mode lecture seule. Les formateurs peuvent utiliser le mode lecture seule pour leur permettre de partager leurs projets avec les élèves sans avoir à se soucier des modifications inutiles ou accidentelles.

En outre, Live Share prend en charge pour permettre à jusqu’à 30 invités de rejoindre une session de collaboration. De cette façon, les formateurs peuvent avoir leur jointure de classe entière dans une session et afficher le code ensemble.

Pour activer cette fonctionnalité :

- **Vs code :** Ajoutez « LiveShare. increasedGuestLimit » : « true » à Settings. JSON.
- **Vs :** Définir les options de > d’outils > Live Share > limite d’invités augmentée à « true »

Pour optimiser complètement Live Share pour ce scénario, nous devons simplifier la façon dont les sessions sont lancées ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Révisions du code

PRs est un moyen puissant de collaborer avec d’autres utilisateurs, mais représente généralement l’achèvement d’une tâche (à l’exception de « WIP » PRs) et le souhait de la fusionner dans. Bien souvent, les commentaires fournis dans une demande de tirage peuvent facilement avoir été fournis plus tôt et, par conséquent, il est possible pour les équipes de rechercher facilement et en continu des conseils de leurs pairs, par opposition à l’attente jusqu’à ce qu’ils aient « terminé » une tâche à demander.

Dans la mesure où Live Share vous permet de partager instantanément votre projet avec d’autres personnes, il peut être utilisé pour activer des révisions de code/ad-hoc « informels », où, au lieu de vous demander de l’aide, vous recherchez simplement une entrée pour vous assurer que votre direction et/ou approche sont alignées avec d’autres. Cela peut permettre d’accélérer la réalisation de la mise à niveau suivante et de simplifier la vie des connaissances de l’équipe.

En outre, étant donné que Live Share vous permet de partager un répertoire arbitraire, vous pouvez l’utiliser pour effectuer des révisions du code, même si vous n’utilisez pas actuellement le contrôle de version (bien que vous le souhaitiez !) ou si votre équipe n’utilise pas PRs (par exemple, vous effectuez le développement basé sur les Trunks.

Live Share ne partage pas actuellement les différences de contrôle de code source, ce qui est un élément essentiel du contexte lors de son utilisation pour les révisions du code. Il s’agit de notre feuille de route, et les commentaires sur la priorité sont très appréciés ([Vote 👍 ici](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entretiens techniques

Lors de l’interrogation des candidats à la position d’un développeur, il peut souvent être utile d’aller au-delà des discussions du tableau blanc, mais aussi de les observer résoudre un problème de codage à partir d’un IDE réel (surtout si votre équipe/organisation a « standardisé » sur un outil qui vous aimeriez les voir utiliser). Cela leur permet non seulement de travailler de façon plus naturelle et plus confortable (la plupart des développeurs ne codent pas sur les tableaux blancs !), mais également de leur fournir des commentaires et une assistance immédiates pendant le travail (par exemple, les erreurs de build, IntelliSense). Bien souvent, il est plus important de comprendre le processus de pensée d’un candidat, par opposition à sa capacité à mémoriser la syntaxe exacte et/ou les noms d’API. De cette façon, Live Share fournit une expérience similaire à la réalisation d’une session de programmation par paire, mais permet au participant d’être dans son propre environnement (y compris les paramètres de système d’exploitation, tels que l’accessibilité) et de fonctionner aussi bien pour les entretiens locaux que distants.

En outre, le développement réel est plus qu’une simple écriture de code. Étant donné que Live Share prend également en charge le débogage partagé, les tâches et les terminaux, il permet aux interviseurs d’observer les candidats tout en diagnostiquer un problème et de leur fournir les outils appropriés nécessaires pour le résoudre (par exemple, déboguer l’étape, exécuter les tests). Étant donné que tout le contexte est à distance à partir de l’ordinateur de l’hôte, les candidats peuvent rapidement accéder à l’environnement d’entretien sans avoir à configurer leur ordinateur (au-delà de l’installation de Live Share). Les équipes peuvent ensuite maintenir un référentiel d’applications d’interconnexion partagées (ou utiliser leur code base de produit réel), qui peuvent être clonées et partagées avec des candidats, en leur envoyant simplement l’URL de session avant chaque interview.

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](../reference/platform-support.md)
- [Exigences de connectivité pour Live Share](../reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](../reference/security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
