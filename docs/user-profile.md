---
title: Profil utilisateur - partage en direct de Visual Studio | Microsoft Docs
description: Vue d’ensemble de l’affichage et de supprimer votre profil utilisateur de le Partage Live Visual Studio.
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
ms.openlocfilehash: 1d3b4977745e33ba0ee1b599ea4257c4a49d970d
ms.sourcegitcommit: bfa1020882095fcc7d31cd71cf1f2e601e3bea06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2019
ms.locfileid: "66224700"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="user-profile"></a>Profil utilisateur

Lorsque vous authentifiez avec partage en direct de Visual Studio, il crée un profil utilisateur, ce qui permet de participants avec lequel vous collaborez à voir avec qui vous sont (par exemple, votre adresse de messagerie, l’avatar). À un moment donné, vous pouvez afficher les informations de profil qui partage Live a stocké sur votre nom, en accédant à une des pages suivantes (selon le fournisseur d’identité que vous avez utilisé) :

- [Compte Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/viewprofile)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/viewprofile)

La page vous demander de vous connecter à vérifier votre identité et puis afficher la sortie JSON brute de votre profil utilisateur.

<img width="500px" src="media/user-profile.png" />

Si un profil stocké pour l’identité que vous êtes connecté ne contient pas de partage en direct de Visual Studio, puis il vous indiquera qui également.

<img width="500px" src="media/no-profile.png" />

## <a name="removing-your-profile"></a>Suppression de votre profil

Si vous souhaitez supprimer votre profil utilisateur, vous pouvez cliquer sur le lien intitulé `Click here to get your data removed from our systems` sur le [page de profil utilisateur](#user-profile). Vous pouvez visiter un de ces pages directement (selon le fournisseur d’identité que vous avez utilisé) :

- [Compte Microsoft / Azure Active Directory](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/microsoft/deleteme)
- [GitHub](https://prod.liveshare.vsengsaas.visualstudio.com/auth/identity/github/deleteme)

Sinon, partage en direct de Visual Studio supprime automatiquement votre profil de 30 jours après votre dernière réussite de connexion à. Dans ce contexte, un réussie de « connexion » fait référence à ce qui suit (en fonction de l’outil que vous utilisez) :

| Éditeur ou IDE | Votre profil utilisateur est supprimée de 30 jours après la dernière fois que vous... |
|-|-|
| Visual Studio | Lancez une nouvelle instance de l’IDE. Pour prendre en charge l’authentification unique, le partage en direct de Visual Studio actualise votre session d’authentification chaque fois que vous ouvrez une nouvelle instance de Visual Studio. |
| Visual Studio Code | Terminer le flux de travail de l’authentification basée sur un navigateur (par exemple, en cliquant sur le `Sign In` bouton ou en cours d’exécution le `Live Share: Sign in with browser` commande). Visual Studio Live partager mémorisent votre session d’authentification sur le client, pour vous éviter d’avoir à se connecter chaque fois que vous partagez. Toutefois, cette session expire au bout de 30 jours et n’est jamais automatiquement actualisée, jusqu'à ce que vous explicite reconnecter via le navigateur. |

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Fonctionnalités de sécurité de Live Share](reference/security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](troubleshooting.md) ou [fournir des commentaires](support.md).
