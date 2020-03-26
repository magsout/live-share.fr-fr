---
title: Profil utilisateur-Visual Studio Live Share | Microsoft Docs
description: Vue d’ensemble de l’affichage et de la suppression de votre profil utilisateur Visual Studio Live Share.
ms.custom: ''
ms.date: 05/222/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2f9f496b47db7efe260c1f09a2906c68c07762d5
ms.sourcegitcommit: 6bf13781dc42a2bf51a19312ede37dff98ab33ea
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80295945"
---
<!--
Copyright &copy; Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Profil utilisateur

Lorsque vous vous authentifiez avec Visual Studio Live Share, il crée un profil utilisateur pour vous, qui autorise simplement les participants avec lesquels vous collaborez pour voir qui vous êtes (par exemple, votre adresse de messagerie, votre avatar). À un moment donné, vous pouvez afficher les informations de profil que Live Share a stockées en votre nom, en accédant à l’une des pages suivantes (en fonction du fournisseur d’identité que vous avez utilisé) :

- [Compte Microsoft/Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

Cette page vous demande de vous connecter (afin de vérifier votre identité) et affiche ensuite la sortie JSON brute pour votre profil utilisateur.

<img width="500px" src="media/user-profile.png" />

Si Visual Studio Live Share ne dispose pas actuellement d’un profil stocké pour l’identité avec laquelle vous vous êtes connecté, il vous en informe également.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Suppression de votre profil

Si vous souhaitez supprimer votre profil utilisateur, vous pouvez cliquer sur le bouton `Delete your account` de la [Page profil utilisateur](#user-profile). Dans le cas contraire, Visual Studio Live Share supprimera automatiquement votre profil 30 jours depuis la dernière connexion réussie. Dans ce contexte, une « connexion réussie » fait référence aux éléments suivants (selon l’outil que vous utilisez) :

| IDE/éditeur | Votre profil utilisateur sera supprimé 30 jours après la dernière fois... |
|-|-|
| Visual Studio | Lancez une nouvelle instance de l’IDE. Afin de prendre en charge l’authentification unique, Visual Studio Live Share actualise votre session d’authentification chaque fois que vous ouvrez une nouvelle instance de Visual Studio. |
| Visual Studio Code | Terminez le flux de travail d’authentification basé sur le navigateur (par exemple, en cliquant sur le bouton `Sign In` ou en exécutant la commande `Live Share: Sign in with browser`). Visual Studio Live Share mémorise votre session d’authentification sur le client, pour vous empêcher de devoir vous connecter à chaque fois que vous partagez. Toutefois, cette session expire au bout de 30 jours et n’est jamais actualisée automatiquement, jusqu’à ce que vous vous connectiez à nouveau via le navigateur. |

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](reference/security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](troubleshooting.md) ou [fournir des commentaires](support.md).
