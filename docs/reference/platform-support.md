---
title: Support de plate-forme et langage - partage en direct de Visual Studio | Microsoft Docs
description: Vue d’ensemble de la prise en charge de plateforme et le langage de Visual Studio Live de partage.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 91e80df324a0b2f49fdf37a5270cf7b86fca5c7c
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640222"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Prise en charge de langage et plateforme

Fonctionnalités de Visual Studio Live du partage sont destinées à fonctionner sur un paysage de divers langages et plateformes d’application. Toutefois, étant donné le nombre élevé de variantes, certains langages et plateformes sont plus complètes que d’autres. Ce document décrit l’état d’un nombre de langages populaires plateformes et pour les fonctionnalités actuellement prises en charge connu actuel.

Consultez une langue ou la plateforme que vous avez besoin ? Vous souhaitez ajouter un que vous ne voyez pas ? [Voter ici.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Tous les langages / plateformes ont le même intellisense avec un fichier (lorsque l’extension respectif est installée), ainsi que la coloration et même édition prise en charge. Les listes ci-dessous couvre avancés des fonctionnalités actuellement sans prise en charge complète et universelle :

### <a name="languages"></a>Langages

| Langue | Services de langage partagé | Partagé de débogage |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *N/A* |
| Ballerine | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Crystal](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *N/A* <sup>1</sup> | ✅ |
| CSS | *N/A* | *N/A* |
| DART | ✅ | ✅ |
| Docker | ✅ | *N/A* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| Flux | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *N/A* |
| Go | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *N/A* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript / TypeScript | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *N/A* | *N/A* <sup>4</sup> |
| Lua | ✅ | ✅ |
| Markdown | ✅ | *N/A* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Pascal | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *N/A* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Reason/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *N/A* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *N/A* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Uniformité | ✅ | *N/A* <sup>4</sup> |
| SQL / T-SQL | *N/A* | *N/A* <sup>4</sup> |
| [Stylus](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *N/A* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> prise en charge non CSHTML dans C# extension.<br />
<sup>2</sup> JavaScript incorporé au format HTML est pris en charge lors de débogage du client.<br />
<sup>3</sup> JavaScript / TypeScript de débogage pour le nœud ou le navigateur.<br />
<sup>4</sup> l’extension respectif pour VS Code ne prend actuellement en charge le débogage. Dès qu’il est le cas, nous allons étudier lui ajoutant une prise en charge même emplacement de débogage. <br />

### <a name="platforms"></a>Plateformes

| Type de plateforme d’application | Partagé de débogage | Partage d’application |
|-------------------|--------------|-------------|
| Arduino | ✅ | *N/A* |
| Azure App Service | ✅ | *N/A* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (local et distant) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Console / CLI | ✅ | ✅ <sup>4</sup> |
| Bases de données | <sup>5</sup> | ✅ <sup>1</sup> |
| Bureau (électrons/natif) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Jeux (Unity) | ✅ | <sup>9</sup> |
| Jeux (Unreal) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *N/A* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1,7</sup> |
| Mobile (natif) | ✅ | <sup>9</sup> |
| Mobile (React Native) | ✅ | ✅ <sup>1,8</sup> |
| Application Web / API (Back-end) | ✅ | ✅ <sup>1</sup> |
| Application Web (frontal) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensions de VS Code | | <sup>9</sup> |

<sup>1</sup> via [serveur local partage](../use/vscode.md#share-a-server).<br />
<sup>2</sup> débogage portant sur l’ordinateur hôte navigateur plutôt qu’invité.<br />
<sup>3</sup> par partage de serveur principal.<br />
<sup>4</sup> pris en charge par le biais de terminaux partagés.<br />
<sup>5</sup> déboguer les procédures stockée de base de données est actuellement pas en charge <br />
<sup>6</sup> via « preview ». Toutefois, les images n’apparaissent pas en raison du problème connu. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> Cordova apps peuvent être partagées par le biais de la plateforme « navigateur »<br />
<sup>8</sup> applications react Native peuvent être partagées via Expo et [serveurs partagés](../use/vscode.md#share-a-server).<br />
<sup>9</sup> partage live ne prend actuellement en charge partage windows/écrans. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Alors que la plupart des langages ont un seul fichier prise en charge Intellisense, il existe certaines restrictions décrites ci-dessous. Tous les langages/plateformes prennent en charge la même modification. Le reste de la liste couvre les fonctionnalités avancées actuellement sans prise en charge complète et universelle :

### <a name="languages"></a>Langages

| Langue | Services de langage de fichier unique | Services de langage de l’échelle du projet | Même emplacement de débogage |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅  <sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *N/A* | <sup>2</sup> |
| CSS | ✅ | *N/A* | *N/A* |
| JavaScript / TypeScript | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *N/A* | *N/A* |
| PowerShell | ✅ | *N/A* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *N/A* | <sup>4</sup> |
| SQL / T-SQL | ✅ | *N/A* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *N/A* | ✅ |

<sup>1</sup> gap : ASPX, CSHTML et VBHTML ont connu problèmes incorporé environ C#étant donné le code-behind de la prise en charge /VB C#/VB fichiers ne sont pas résolues en raison des fonctionnalités intellisense complètes non implémentée. [Vote (👍) ici sur CSHTML/VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Vote (👍) ici sur ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> JavaScript incorporé au format HTML est pris en charge lors de débogage du client.<br />
<sup>3</sup> JavaScript / TypeScript de débogage pour le nœud ou le navigateur.<br />
<sup>4</sup> bien que le débogage de XAML lui-même est techniquement n/a, le débogage de code-behind est pris en charge.<br />
<sup>5</sup> gap : Erreurs service de langage de R sur le côté de l’invité sur la jonction et après chaque saut de ligne. Non pris en charge. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plateformes

| Type de plateforme d’application | Codébogage | Partage d’application |
|-------------------|--------------|-------------|
| Application Web / API (Back-End) | ✅ | ✅ <sup>1</sup> |
| Application Web (frontal) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Espaces de développement Azure](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bases de données | <sup>4</sup> | ✅ <sup>5</sup> |
| Console / CLI | ✅ | ✅ <sup>6</sup> |
| Bureau (WinForms) | ✅ | |
| Desktop (WPF) | ✅ | |
| Plateforme Windows universelle | ✅ |  |
| Extensions VS | ✅ |  |

<sup>1</sup> via [serveur local partage](../use/vs.md#share-a-server). Les applications Web ASP.NET peuvent également utiliser [partage d’application web automatique](../use/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> débogage portant sur l’ordinateur hôte navigateur plutôt qu’invité.<br />
<sup>3</sup> par partage de serveur principal.<br />
<sup>4</sup> déboguer les procédures stockée de base de données est actuellement pas en charge <br />
<sup>5</sup> via [serveur local partage](../use/vs.md#share-a-server). <br />
<sup>6</sup> partiellement prises en charge par le biais de terminaux partagés.<br />
<sup>?</sup> Pas encore validées.

## <a name="see-also"></a>Voir aussi

- [Extensions prises en charge](extensions.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
