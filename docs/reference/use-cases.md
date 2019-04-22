---
title: Cas d’utilisation courants - partage en direct de Visual Studio | Microsoft Docs
description: Vue d’ensemble de cas d’usage qui les développeurs sont couramment tirant parti de Visual Studio Live Share pour.
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
ms.openlocfilehash: 1b6ecafc933c6521f6c21ec0dcd38c25e889a0e2
ms.sourcegitcommit: 1706889dd48377932868a03e88fbd2b4512a3729
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58853571"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="common-use-cases"></a>Cas d’usage courants

L’objectif principal de partage en direct de Visual Studio consiste à permettre aux développeurs de collaborer entre eux plus facilement, sans introduire de tout avis sur quand et comment le faire (par exemple, quel outil de communication à utiliser, la méthodologie de logiciels « droite » ou le flux de travail SCM). De cette façon, vos outils peuvent prendre en charge les interactions qui se produisent **naturellement**et en tant que **fréquemment** en fonction des besoins, mais d’une manière qui **avec les compliments** comment vous préférez déjà travailler.

Met en surbrillance ce document certaines des utilisations que partage en direct de Visual Studio est déjà utilisé pour et décrit la manière dont nous prenons en charge, ainsi que les façons nous prévoyons de les optimiser davantage (en fonction de vos commentaires !). Si vous utilisez le partage en direct pour quelque chose qui n’est pas déjà abordés ci-dessous, ou vous pensez que nous pouvons faire encore mieux pour prendre en charge d’un cas d’usage spécifique, veuillez [faites-nous savoir](https://github.com/MicrosoftDocs/live-share/issues/new).

- [Aide rapide](#quick-assistance)
    - [Heures de bureau](#office-hours)
- [Programmation par paires](#pair-programming)
    - [MOB par programmation](#mob-programming)
    - [Concours de codage / Hack-A-Thons](#coding-competitions--hack-a-thons)
    - [Projets de groupe de l’école](#school-group-projects)
    - [Développeur de diffusion en continu](#developer-streaming)
    - [Prototypage / création de projet](#prototyping--project-inception)
- [Formation interactive](#interactive-education)
    - [Parrainage / l’intégration](#peer-mentoring--onboarding)
    - [Catégories de l’équipe](#team-brown-bags)
    - [La classe conférences](#classroom-lectures)
- [Révisions de code](#code-reviews)
- [Entretiens techniques](#technical-interviews)

## <a name="quick-assistance"></a>Aide rapide

Lorsque vous rencontrez un problème (par exemple, une tentative de résoudre un bogue, la configuration de votre environnement), vous pouvez utiliser le partage en direct de Visual Studio instantanément demander une assistance à partir d’un autre pair. Dans de nombreux cas, il n’est pas immédiatement évident quel contexte devez la personne fournit de l’aide, et par conséquent, permet de partager de Live en rendant simple fournir l’accès à l’ensemble du projet et if/en tant que si nécessaire, partage progressivement plus (par exemple, un serveur local, en lecture seule Terminal Server). Il est inutile d’envoyer des extraits de code et/ou des messages d’erreur back-et-les deux sens !

En outre, étant donné que Live partager vous permet de partager votre session de débogage active, sans avoir à « invités » installer tous les kits de développement de plateformes nécessaire (par exemple, Node.js, Go, .NET Core) ou d’outils des extensions, il peut vous aider à obtenir la résolution plus rapide et empêcher « ne situations de reproduction sur mon ordinateur ». Partage en direct vous permet de partager l’état de débogage avec d’autres utilisateurs, pour n’importe quel environnement de langage ou runtime programmation (par exemple, Kubernetes, application React Native) et par conséquent, quel que soit que ce que vous avez besoin d’aide, vous pouvez le partager !

### <a name="office-hours"></a>Heures de bureau

De nombreuses entreprises et les établissements d’enseignement (par exemple, les écoles, les formations en ligne) fournissent la prise en charge pour leurs clients/employés/les étudiants prédéterminé et heures en général une périodicité (par exemple, chaque vendredi à partir de 3-5 h). De cette façon, « heures de bureau » constituent simplement un planifiée de « assistance rapide », et non entièrement ad-hoc. Partage en direct rend plus facile pour vous aider à rapidement, étant donné que l’aide de la fourniture « expert » peut immédiatement rejoindre une session de collaboration et répondre à votre question, sans avoir à configurer leur machine du tout.

## <a name="pair-programming"></a>Programmation par paires

Les plus couramment utilisés de scénarios de partage en direct de Visual Studio est « programmation par paire » : plusieurs développeurs, travaillant ensemble sur une tâche partagée, dans le but de partage des connaissances, augmentation de la cohésion de l’équipe et éventuellement, la qualité du produit. L’exacte-aspect de la programmation de la paire peut varier considérablement entre les équipes et les situations, selon ce qui suit (entre autres) :

1. L’étendue de la « tâche » en cours a collaboré sur (par exemple, un bogue, un récit utilisateur)

1. Durée prévue de la session de collaboration (par exemple, deux minutes, une heure, à plein temps, une fois par semaine, TBD)

1. Le nombre de personnes impliquées (par exemple, deux, toute l’équipe)

1. Le rôle de chaque participant (par exemple, « pilote », Observateur/réviseur, expert technique)

1. La proximité de participants (par exemple, colocalisé dans le même bâtiment, dans le monde entier)

Partage en direct a été conçu pour être indépendant de tous les problèmes mentionnés ci-dessus et au lieu de cela, il s’efforce de prendre en charge la programmation par paire qui est totalement « opportuniste » et la technologie Microsoft à votre situation. Ceci dit, contrairement aux deux développeurs partage un ensemble clavier et écran, Partage Live permet une forme de programmation par paire qui permet aux développeurs de travailler sur un objectif commun, sans supprimer leur autonomie individuel ou les préférences de l’environnement. Vous pouvez travailler indépendamment ou ensemble, ce qui permet chaque participant afficher leurs propres pensé processus pour la collaboration.

Pour décomposer ce cas d’usage encore plus loin, les éléments suivants représentent des formes de paire de programmation que nous avons observé des personnes à l’aide d’un partage de Live pour :

### <a name="mob-programming"></a>MOB par programmation

[MOB par programmation](https://en.wikipedia.org/wiki/Mob_programming) (ou swarm programmation) est essentiellement de paire de programmation, mais avec plus de deux personnes. Par conséquent, tous les avantages de partage en direct pour la programmation par paire également s’appliquer également. En outre, certaines équipes faire « l’ESSAIMAGE » sur une en fonction des besoins (par exemple, l’équipe rassembler autour d’incendie) par opposition à plein temps.

Actuellement, Partage Live prend en charge jusqu'à 30 invités au sein d’une session.
> [!TIP]
> Pour activer les 30 invités dans une session :
> - **VS Code :** ajouter « liveshare.increasedGuestLimit":"true » à settings.json
> - **VISUAL STUDIO :** Définir des outils > Options > Partage Live > augmentation de la limite invité sur « True » 

### <a name="coding-competitions--hack-a-thons"></a>Concours de codage / Hack-A-Thons

Concours de codage et de pirater un thons sont des variations efficacement à court terme, la tâche unique de la programmation de mob. Les membres de l’équipe et leur rôle actuel, sont également potentiellement dynamiques. Étant donné que ce cas d’utilisation est généralement également de temps, la capacité de collaborer en temps réel sans avoir à adopter un outil entièrement nouveau et la possibilité de travailler ensemble, sans être limités à un seul écran ou le clavier, peut accéder un moyen de journal par ordre croissant rapidité.

Dans la mesure où les participants dans cet environnement ne seront pas toujours entièrement « fiables », vous pouvez supprimer (et bloquer) un invité d’une session à tout moment. Cela fournit des « hôtes » avec contrôle total sur leur environnement.

### <a name="school-group-projects"></a>Projets de groupe de l’école

Regrouper des projets finit par beaucoup comme mob de programmation, où plusieurs étudiants travaillent ensemble et pouvez passer en toute transparence de se concentrer sur une seule tâche ou de travailler simultanément sur des tâches distinctes. Au lieu de simplement compter sur le contrôle de version pour collaborer de façon asynchrone, ils peuvent utiliser le partage en direct de collaborer en temps réel, qui peut aider aux avantages sociaux et d’enseignement de l’utilisation d’un groupe.

### <a name="developer-streaming"></a>Développeur de diffusion en continu

Développeur (via Twitch ou Mixer) de diffusion en continu est devenu un nouveau formulaire d’éducation attrayant. Tandis que Live de partage n’est pas destiné à remplacer leurs plateformes broadcasting (bien que nous avons entendu la demande !), elle offre un moyen pour l’hôte pour la paire de programme avec un ou plusieurs invités et transmettez-les cette interaction. De cette façon, visionneuses potentiellement plus en visualisant l’interaction naturelle et le processus de pensée de deux ou plusieurs développeurs, ce qui peut même être collaboration dans les systèmes d’exploitation totalement distincts et différents IDE !

### <a name="prototyping--project-inception"></a>Prototypage / création de projet

Lorsqu’une équipe démarre un nouveau projet/microservice ou prototypage/parasites une nouvelle fonctionnalité, il peut être souvent utile de collaborer afin de progresser rapidement et à Explorer de nouvelles idées. Dans la mesure où la base de code qui vient d’être formation ne peut pas être validée encore vers un référentiel partagé, Partage Live autorise tous les employés à participer au processus itératif, quel que soit si elles sont dans le même bureau ou non.

## <a name="interactive-education"></a>Formation interactive

En règle générale, Partage Live vise à aider les développeurs dans le partage des connaissances entre leur équipe. La formation est un cas d’usage fondamental pour le partage en direct, et il prend en charge cette particulièrement bien en permettant à chaque participant interagir avec la base de code en cours a collaboré sur, au lieu de simplement regarder un écran. Tout le monde apprend de différentes façons de subtilité, et par conséquent, en fournissant l’indépendance à un « student », ils sont capables de tirer parti de l’instruction en cours donnée, sans devoir sacrifier leur capacité à explorer leurs propres idées.

### <a name="peer-mentoring--onboarding"></a>Parrainage / l’intégration

Lorsque vous introduisez un développeur à une nouvelle base de code, fonctionnalité de zone, technologie, etc., vous pouvez utiliser Live de partage pour les guider tout au long du projet (à l’aide de `Follow Mode`), de sorte qu’ils peuvent suivre avec vous, mais à partir de leur propre personnel IDE. Étant donné que le partage Live permet de « invités » accéder indépendamment du projet (ouverture d’un fichier, par exemple, l’exécution d’un `Peek Definition`), ils peuvent suivre autoriser, mais également effectuer des explorations rapides en fonction des besoins (par exemple) « Hmm, ce que fait cette fonction ? »).

### <a name="team-brown-bags"></a>Catégories de l’équipe

Sacs de l’équipe marron sont effectivement comme parrainage, mais présentée à une équipe entière et éventuellement, davantage sur les méfaits connaissances généralement utile, par opposition à l’intégration prennent en charge et/ou aider avec une tâche spécifique.

### <a name="classroom-lectures"></a>La classe conférences

Lorsque les formateurs sont enseigne une leçon, ils permettent Partage Live pour partager leur projet avec les étudiants, au lieu de présenter simplement leur écran. Ainsi, la classe entière suivre l’enseignant, tout en étant en mesure d’interagir avec le projet sur leurs propres. En outre, les enseignants peuvent demandez-leur individuels pour vous aider à résoudre une partie spécifique de la leçon (par exemple) « Quelle méthode devrions nous appelons ici ? »), qui peut vous aider dans les aspects sociaux de la classe, sans nécessiter les étudiants, remonter au début de la salle, ni même être physiquement présent dans la même salle (par exemple, des cours en ligne).

Pour faciliter les paramètres de la classe, Partage Live permet le partage en mode lecture seule. Formateurs peuvent utiliser mode lecture seule pour activer leur permet de partager leurs projets avec les étudiants sans avoir à vous soucier des modifications accidentelles ou inutiles adressées.

En outre, le partage Live a prise en charge pour activer jusqu'à 30 invités rassemblant sous la forme d’une session de collaboration. De cette façon, formateurs peuvent avoir leur ensemble de la classe join dans une session et afficher le code.

Pour activer cette fonctionnalité :

- **VS Code :** Ajoutez « liveshare.increasedGuestLimit":"true » à settings.json.
- **VISUAL STUDIO :** Définir des outils > Options > Partage Live > augmentation de la limite invité sur « True »

Afin d’optimiser le partage en direct pour ce scénario, nous avons besoin pour simplifier la façon que les sessions sont lancées ([#422](https://github.com/MicrosoftDocs/live-share/issues/422)).

## <a name="code-reviews"></a>Révisions de code

Demandes de tirage sont un moyen puissant de collaborer avec d’autres personnes, mais représentent généralement l’achèvement d’une tâche (à l’exception des demandes de tirage « TEC »), et le désir de fusionnées dans. De nombreux cas, les commentaires qui sont spécifié dans une demande de tirage peuvent facilement ont reçu précédemment, et par conséquent, il se peut que valeur pour les équipes de facilement et en permanence recueillir les avis de leurs pairs, par opposition à en attente jusqu'à ce qu’ils « terminent » une tâche à demander.

Étant donné que Live partager vous permet de partager instantanément votre projet avec d’autres, il peut être utilisée pour activer « informelle » / ad-hoc révisions du code, où au lieu de la demande d’aide, vous êtes recherchiez simplement entrée pour vous assurer de votre direction et/ou l’approche s’aligne avec d’autres utilisateurs. Cela peut aider potentiellement suivantes PRs se terminer plus rapidement et sans aucun doute vous aide à établir des liens sociaux connaissances au sein de l’équipe.

En outre, étant donné que Live partager vous permet de partager un répertoire arbitraire, utilisez-le pour effectuer des révisions du code, même si vous n’utilisez pas actuellement des contrôle de version (bien que vous devez !), ou si votre équipe n’utilise pas de demandes de tirage (ex :) procéder développement trunk).

Partage en direct ne partage actuellement les différences de contrôle de code source, qui est un élément essentiel du contexte lors de l’utilisation pour les révisions de code. Il s’agit sur notre feuille de route et apprécions beaucoup vos commentaires sur la priorité ([Vote 👍 ici](https://github.com/MicrosoftDocs/live-share/issues/36)).

## <a name="technical-interviews"></a>Entretiens techniques

Lors de l’interrogation des candidats pour un poste de développeur, il peut souvent être utile d’aller au-delà des discussions sur le tableau blanc et à la place, observez les résoudre un problème de codage à partir d’un IDE réelle (en particulier si votre équipe/organisation « standard » sur un outil qui vous aimeriez voir les utiliser). Cela leur offre non seulement l’avantage de l’utilisation d’une manière qui est potentiellement plus naturel/à l’aise (la plupart des développeurs ne code sur des tableaux blancs !), mais leur donne également des commentaires/assistance immédiate lors de l’utilisation (par exemple, erreurs, intellisense de génération). De nombreux cas, il est plus important de comprendre le processus de réflexion d’un candidat, par opposition à leur capacité à mémoriser la syntaxe exacte et/ou les noms d’API. De cette façon, Partage Live fournit une expérience similaire à l’exécution d’une paire de programmation de session, mais permet le participant dans leur propre environnement (y compris les paramètres du système d’exploitation, tels que l’accessibilité), et fonctionnerait tout aussi ainsi qu’à des entretiens locales ou distants.

En outre, développement réel est plus que simplement écrire du code. Étant donné que le partage Live prend également en charge le débogage partagé, tâches et terminaux, il permet de personnes expérimentées observer les candidats en diagnostiquer un problème en lui fournissant les outils appropriés nécessaires pour résoudre le problème (par exemple, étape déboguer, exécuter des tests). Dans la mesure où tout le contexte est exécutée à distance à partir de l’ordinateur de l’hôte, les candidats peuvent accéder rapidement dans l’environnement « entretien » sans avoir à configurer leur machine (au-delà de l’installation de partage en direct). Équipes pourraient puis maintenir un référentiel de partagé à l’interrogation des applications (ou utilisez leur base de code produit réel), qui pourrait être copiés et partagés avec les candidats, en les envoyant simplement l’URL de la session avant chaque entretien.

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](platform-support.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
