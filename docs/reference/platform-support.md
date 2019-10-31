---
title: Prise en charge des plateformes et des langues-Visual Studio Live Share | Microsoft Docs
description: Vue d’ensemble de la prise en charge des plateformes et des langages pour Visual Studio Live share.
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
ms.openlocfilehash: 386a8204787ed378413e1b35b7c2a80e0de678ce
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170089"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="language-and-platform-support"></a>Prise en charge de langues et de plateformes

Les fonctionnalités de Visual Studio Live Share sont destinées à fonctionner dans un paysage diversifié de langues et de plateformes d’application. Toutefois, étant donné le nombre important de variations, certaines plateformes et certains langages sont plus complets que d’autres. Ce document décrit l’état actuel connu d’un certain nombre de langages et plateformes populaires pour les fonctionnalités actuellement prises en charge.

Vous voyez un langage ou une plateforme dont vous avez besoin ? Vous souhaitez en ajouter une qui ne s’affiche pas ? [Votez ici.](https://github.com/MicrosoftDocs/live-share/issues/12)

## <a name="visual-studio-code"></a>Visual Studio Code

Tous les langages/plateformes ont le même fichier IntelliSense (lorsque l’extension respective est installée), ainsi que la prise en charge de la colorisation et de la co-édition. Les listes ci-dessous traitent actuellement des fonctionnalités avancées sans prise en charge complète et universelle :

### <a name="languages"></a>Langages

| Langue | Services de langage partagé | Débogage partagé |
|----------|--------------------------------|--------------|
| Ansible | ✅ | *NON APPLICABLE* |
| Ballerina | ✅ | ✅ |
| Bash | ✅ | ✅ |
| C++ | ✅ | ✅ |
| C# | ✅ | ✅ |
| Clojure | ✅ | *N/A* <sup>4</sup> |
| [ColdFusion (CFML)](https://marketplace.visualstudio.com/items?itemName=KamasamaK.vscode-cfml) | ✅ | *N/A* <sup>4</sup> |
| [Crystal Reports](https://marketplace.visualstudio.com/items?itemName=faustinoaq.crystal-lang) | ✅ | *N/A* <sup>4</sup> |
| CSHTML | *N/A* <sup>1</sup> | ✅ |
| CSS | *NON APPLICABLE* | *NON APPLICABLE* |
| Fléchette | ✅ | ✅ |
| Docker | ✅ | *NON APPLICABLE* |
| Elixir | ✅ | ✅ |
| Elm | ✅ |  *N/A* <sup>4</sup> |
| Erlang | ✅ | ✅ |
| F# | ✅ |  *N/A* <sup>4</sup> |
| Flux | ✅ |  *N/A* <sup>4</sup> |
| Fortran | ✅ | *NON APPLICABLE* |
| Go | ✅ | ✅ |
| Gradle | ✅ | *N/A* <sup>4</sup> |
| GraphQL | ✅ | *N/A* <sup>4</sup> |
| Haskell | ✅ | ✅ |
| HTML | *NON APPLICABLE* | <sup>2</sup> |
| Java | ✅ | ✅ |
| JavaScript/machine à écrire | ✅ | ✅ <sup>3</sup> |
| Julia | ✅ | *N/A* <sup>4</sup> |
| [Kotlin](https://marketplace.visualstudio.com/items?itemName=mathiasfrohlich.Kotlin) | *NON APPLICABLE* | *N/A* <sup>4</sup> |
| Privilège | ✅ | ✅ |
| Markdown | ✅ | *NON APPLICABLE* |
| MATLAB |  ✅ | *N/A* <sup>4</sup> |
| Objective-C | ✅ | *N/A* <sup>4</sup> |
| Casse | ✅ | *N/A* <sup>4</sup> |
| Perl | ✅ | ✅ |
| PHP | ✅ | ✅ |
| PowerShell | *NON APPLICABLE* | ✅ |
| Python |  ✅ | ✅ |
| PureScript | ✅ | *N/A* <sup>4</sup> |
| R |  ✅ | *N/A* <sup>4</sup> |
| [Raison/OCaml](https://marketplace.visualstudio.com/items?itemName=freebroccolo.reasonml) | ✅ | *N/A* <sup>4</sup> |
| reStructuredText | ✅ | *NON APPLICABLE* |
| Ruby | ✅ | ✅ |
| Rust | ✅ | *N/A* <sup>4</sup> |
| [Sass](https://marketplace.visualstudio.com/items?itemName=robinbentley.sass-indented) | ✅ | *NON APPLICABLE* |
| Scala | ✅ | *N/A* <sup>4</sup> |
| Solidité | ✅ | *N/A* <sup>4</sup> |
| SQL/T-SQL | *NON APPLICABLE* | *N/A* <sup>4</sup> |
| [Stylet](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus) | ✅ | *NON APPLICABLE* |
| [Svelte](https://marketplace.visualstudio.com/items?itemName=JamesBirtles.svelte-vscode) | ✅ | *N/A* <sup>4</sup> |
| Swift | ✅ | *N/A* <sup>4</sup> |
| Terraform | ✅ | *N/A* <sup>4</sup> |
| XML | ✅ | *N/A* <sup>4</sup> |
| YAML | ✅ | *N/A* <sup>4</sup> |

<sup>1</sup> aucune prise en charge C# de cshtml dans l’extension.<br />
<sup>2</sup> le JavaScript incorporé en HTML est pris en charge lors du débogage du client.<br />
<sup>3</sup> débogage de code JavaScript/de la machine à écrire pour le nœud ou le navigateur.<br />
<sup>4</sup> l’extension respective de vs code ne prend pas en charge le débogage pour le moment. Dès que c’est le cas, nous examinerons l’ajout de la prise en charge du débogage. <br />

### <a name="platforms"></a>Plateformes

| Type d’application/plateforme | Débogage partagé | Partage d’applications |
|-------------------|--------------|-------------|
| Arduino | ✅ | *NON APPLICABLE* |
| Azure App Service | ✅ | *NON APPLICABLE* |
| Azure Dev Spaces | ✅ | ✅ <sup>1</sup> |
| Azure Functions (local et distant) | ✅ | ✅ <sup>1</sup> |
| Blockchain (Ethereum) | ✅ | ✅ <sup>1</sup> |
| Console/interface de commande | ✅ | ✅ <sup>4</sup> |
| Bases de données | <sup>5</sup> | ✅ <sup>1</sup> |
| Bureau (électron/native) | ✅ | <sup>9</sup> |
| Dynamics NAV 2018 | ✅ | ✅ <sup>1</sup> |
| Jeux (Unity) | ✅ | <sup>9</sup> |
| Jeux (non réels) | ✅ | <sup>9</sup> |
| Kubernetes (YAML, Helm) | ✅ |  ✅ <sup>1</sup> |
| Markdown | *NON APPLICABLE* | ✅ <sup>6</sup> |
| Mobile (Cordova) | ✅ | ✅ <sup>1, 7</sup> |
| Mobile (natif) | ✅ | <sup>9</sup> |
| Mobile (REACT native) | ✅ | ✅ <sup>1, 8</sup> |
| Application Web/API (serveur principal) | ✅ | ✅ <sup>1</sup> |
| Application Web (frontale) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Extensions de VS Code | | <sup>9</sup> |

<sup>1</sup> via [partager un serveur local](../how-to-guides/vscode.md#share-a-server).<br />
<sup>2</sup> le débogage se produit sur le navigateur de l’hôte au lieu de l’invité.<br />
<sup>3</sup> en partageant le serveur principal.<br />
<sup>4</sup> pris en charge via des terminaux partagés.<br />
<sup>5</sup> les procédures stockées de base de données de débogage ne sont pas prises en charge actuellement <br />
<sup>6</sup> via « preview ». Toutefois, les images ne s’affichent pas en raison d’un problème connu. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/61)<br />
<sup>7</sup> les applications Cordova peuvent être partagées via la plateforme « Browser »<br />
<sup>8</sup> les applications natives REACT peuvent être partagées via les serveurs d’exposition et [partagés](../how-to-guides/vscode.md#share-a-server).<br />
<sup>9</sup> Live share ne prend pas actuellement en charge le partage des fenêtres/écrans. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/236)

## <a name="visual-studio"></a>Visual Studio

Bien que la plupart des langages aient une prise en charge IntelliSense à fichier unique, certains avertissements sont décrits ci-dessous. Toutes les langues/plateformes prennent en charge la co-édition. Le reste de la liste couvre actuellement des fonctionnalités avancées sans prise en charge complète et universelle :

### <a name="languages"></a>Langages

| Langue | Services de langage à fichier unique | Services de langage à l’ensemble du projet | Co-débogage |
|----------|-------------------------------|--------------------------------|--------------|
| C# | ✅ | ✅ | ✅ |
| CSHTML | ✅<sup>1</sup> | | ✅ |
| ASPX | ✅ <sup>1</sup> |  | ✅ |
| HTML | ✅ | *NON APPLICABLE* | <sup>2</sup> |
| CSS | ✅ | *NON APPLICABLE* | *NON APPLICABLE* |
| JavaScript/machine à écrire | ✅ | ✅ | ✅ <sup>3</sup> |
| C++ | ✅ | ✅ | ✅ |
| Python | ✅ | | ✅ |
| Markdown | ✅ | *NON APPLICABLE* | *NON APPLICABLE* |
| PowerShell | ✅ | *NON APPLICABLE* | ✅ |
| VB.NET | ✅ | | ✅ |
| VBHTML | ✅ <sup>1</sup> | | ✅ |
| XAML | ✅ | *NON APPLICABLE* | <sup>4</sup> |
| SQL/T-SQL | ✅ | *NON APPLICABLE* | |
| F# | ✅ | | ✅ |
| R | ❌ <sup>5</sup> | *NON APPLICABLE* | ✅ |

<sup>1</sup> écart : cshtml, VBHTML et aspx présentent des problèmes connus concernant la prise C#en charge des/VB incorporées C#. les fichiers/VB code-behind ne sont pas résolus en raison de la non-implémentation d’IntelliSense complète. [Vote (👍) ici sur CSHTML/VBHTML.](https://github.com/MicrosoftDocs/live-share/issues/59) [Vote (👍) ici sur ASPX.](https://github.com/MicrosoftDocs/live-share/issues/70)<br />
<sup>2</sup> le JavaScript incorporé en HTML est pris en charge lors du débogage du client.<br />
<sup>3</sup> débogage de code JavaScript/de la machine à écrire pour le nœud ou le navigateur.<br />
<sup>4</sup> bien que le débogage du XAML lui-même soit techniquement N/a, le débogage du code-behind est pris en charge.<br />
<sup>5</sup> écart : Erreurs du service de langage R côté invité lors de la jointure et après chaque saut de ligne. Non prise en charge. [Vote (👍) ici.](https://github.com/MicrosoftDocs/live-share/issues/72)<br />

### <a name="platforms"></a>Plateformes

| Type d’application/plateforme | Codébogage | Partage d’applications |
|-------------------|--------------|-------------|
| Application Web/API (serveur principal) | ✅ | ✅ <sup>1</sup> |
| Application Web (frontale) | ✅ <sup>2</sup> | ✅ <sup>3</sup> |
| Azure Functions | ✅  | ✅ <sup>5</sup> |
| Azure Service Fabric | ✅ | ✅ <sup>5</sup> |
| [Azure Dev Spaces](https://aka.ms/devspaces) | ✅ | ✅ <sup>1</sup> |
| Bases de données | <sup>4</sup> | ✅ <sup>5</sup> |
| Console/interface de commande | ✅ | ✅ <sup>6</sup> |
| Bureau (WinForms) | ✅ | |
| Bureau (WPF) | ✅ | |
| Plateforme Windows universelle | ✅ |  |
| Extensions VS | ✅ |  |

<sup>1</sup> via [partager un serveur local](../how-to-guides/vs.md#share-a-server). ASP.NET Web Apps peut également utiliser le [partage d’applications Web automatique](../how-to-guides/vs.md#automatic-web-app-sharing).<br />
<sup>2</sup> le débogage se produit sur le navigateur de l’hôte au lieu de l’invité.<br />
<sup>3</sup> en partageant le serveur principal.<br />
<sup>4</sup> les procédures stockées de base de données de débogage ne sont pas prises en charge actuellement <br />
<sup>5</sup> via [partager un serveur local](../how-to-guides/vs.md#share-a-server). <br />
<sup>6</sup> partiellement pris en charge via des terminaux partagés.<br />
<sup>?</sup> Pas encore validé.

## <a name="see-also"></a>Voir aussi

- [Extensions prises en charge](extensions.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
