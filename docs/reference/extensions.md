---
title: Extensions et écosystème de support - partage en direct de Visual Studio | Microsoft Docs
description: Vue d’ensemble de la prise en charge de l’extension de partage de Visual Studio Live.
ms.custom: ''
ms.date: 04/25/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: lostintangent
ms.author: joncart
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5a9787643643c22ca7302528dc794480d09df902
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255591"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="extensions-and-ecosystem-support"></a>Prise en charge de l’écosystème et des extensions

Un des principaux objectifs de partage en direct de Visual Studio est de permettre aux développeurs de collaborer avec d’autres, depuis le confort de leurs favoris, et [ **hautement personnalisée** ](https://marketplace.visualstudio.com/) outils. De cette façon, les interactions ad-hoc peuvent se produire fréquemment, tout en restant visuellement familières et ergonomique, quel que soit ce que vous vous aidez avec. Pour ce faire, il est essentiel que les participants au sein d’une session de collaboration sont en mesure de continuer à utiliser toutes les extensions qui prennent en charge leurs [préférences personnelles et des flux de travail](#user-specific-extensions) (par exemple, les thèmes de couleur/icônes, combinaisons de touches, éditeur améliorateurs de productivité).

En outre, pour rendre le fait de rejoindre une session de collaboration en tant qu’instant que possible, tout en restant hautement productifs, l’objectif de partage en direct de Visual Studio consiste à activer invités automatiquement exploiter les outils spécifiques au projet que leur hôte a partagé. De cette façon, vous pouvez simplement cliquer sur un lien, lancez l’outil de votre choix et démarrer la collaboration, sans configuration supplémentaire. Pour ce faire, il est essentiel qu’extensions, qui le cœur de l’alimentation [modifier, générer et déboguer des flux de travail](#project-specific-extensions), sont en toute transparence » exécutée à distance » de l’hôte vers l’invité, afin que les éléments tels que la saisie semi-automatique, atteindre la définition et le débogage » fonctionne tout simplement ».

Ce document couvre actuel connu d’état pour l’écosystème de grande extension, ainsi qu’un « tableau de bord » pour les objectifs mentionnés ci-dessus. Si vous rencontrez une extension qui ne répondent pas à ces critères et est essentiel de votre flux de travail personnel, veuillez vous [Donnez-nous votre avis !](https://github.com/MicrosoftDocs/live-share/issues/new)

## <a name="user-specific-extensions"></a>Extensions spécifiques à l’utilisateur

Les extensions qui prennent en charge les personnalisations spécifiques à l’utilisateur **doit** Professionnel pour l’hôte, et **doit** fonctionnent pour tous les invités. Si une extension ne fonctionne pas correctement pour l’hôte, qui serait une régression et est probablement un bogue dans le partage en direct de Visual Studio (Veuillez [signaler un problème](https://github.com/MicrosoftDocs/live-share/issues/new) si vous voyez une !). Si une extension ne se comporte pas comme prévu pour un invité, il faudra peut-être [modifications dans l’extension elle-même](#known-issues), et nous allons utiliser l’écosystème d’adresse/améliorer ces scénarios.

### <a name="visual-studio-code"></a>Visual Studio Code

| Category | Exemple (s) | Invité-pris en charge ? | Collaboration ? |
|-|-|-|-|
| Thèmes de couleurs | [Un Pro foncé](https://marketplace.visualstudio.com/items?itemName=zhuangtongfa.Material-theme), [sortie Coloriseur](https://marketplace.visualstudio.com/items?itemName=IBM.output-colorizer), [arc-en-ciel chaîne](https://marketplace.visualstudio.com/items?itemName=wk-j.vscode-rainbow-string), [coloré régions](https://github.com/jmihelcic/colored-regions), [mis en retrait de bloc de mise en surbrillance](https://marketplace.visualstudio.com/items?itemName=byi8220.indented-block-highlighting), [ Mise en surbrillance TODO](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight), [Coloriseur de paire de crochet](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer) | ✅ | *N/A* |
| Jeux d’icônes | [icônes de vscode](https://marketplace.visualstudio.com/items?itemName=robertohuertasm.vscode-icons), [icônes de classique Visual Studio](https://marketplace.visualstudio.com/items?itemName=jez9999.vsclassic-icon-theme) | ✅ | *N/A* |
| Combinaisons de touches | [VIM](https://marketplace.visualstudio.com/items?itemName=vscodevim.vim), [IntelliJ IDEA Keybindings](https://marketplace.visualstudio.com/items?itemName=k--kato.intellij-idea-keybindings), [Emacs convivial Keymap](https://marketplace.visualstudio.com/items?itemName=lfs.vscode-emacs-friendly) | ✅ | *N/A* |
| Extraits de code | [Extraits de code Angular v5](https://marketplace.visualstudio.com/items?itemName=johnpapa.Angular2), [extraits HTML](https://marketplace.visualstudio.com/items?itemName=abusaidm.html-snippets), [SVG icônes](https://marketplace.visualstudio.com/items?itemName=idleberg.svg-icons), [en-tête de fichier](https://marketplace.visualstudio.com/items?itemName=mikey.vscode-fileheader) | ✅ | *N/A* <sup>1</sup> |
| Organisation | [Synchronisation des paramètres](https://marketplace.visualstudio.com/items?itemName=Shan.code-settings-sync), [responsable de projet](https://marketplace.visualstudio.com/items?itemName=alefragnani.project-manager), [spécifiqueIl](https://marketplace.visualstudio.com/items?itemName=smulyono.timeit), [points de contrôle](https://marketplace.visualstudio.com/items?itemName=micnil.vscode-checkpoints), [TODO analyseur](https://marketplace.visualstudio.com/items?itemName=minhthai.vscode-todo-parser), [favoris ](https://marketplace.visualstudio.com/items?itemName=kdcro101.favorites) (❌), [signets](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) (❌) | ✅ <sup>2</sup> | *N/A* <sup>3</sup> |
| Productivité | [GitLens](https://marketplace.visualstudio.com/items?itemName=eamodio.gitlens), [renommer automatiquement balise](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag), [Code hiérarchique](https://github.com/patrys/vscode-code-outline), [couleur de surbrillance](https://marketplace.visualstudio.com/items?itemName=naumovs.color-highlight), [incrémenter sélection](https://marketplace.visualstudio.com/items?itemName=albymor.increment-selection), [ Bracketeer](https://marketplace.visualstudio.com/items?itemName=pustelto.bracketeer), [aperçu de l’Image](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-gutter-preview), [JSON Helper](https://marketplace.visualstudio.com/items?itemName=zhoufeng.json-helper) (pointez), [sélecteur de couleurs](https://marketplace.visualstudio.com/items?itemName=anseki.vscode-color), [copier Word dans le curseur](https://marketplace.visualstudio.com/items?itemName=alefragnani.copy-word), [CodeMetrics](https://marketplace.visualstudio.com/items?itemName=kisstkondoros.vscode-codemetrics) (CodeLens), [co-auteurs Git](https://github.com/rjimenezda/vscode-coauthor), [JavaScript Booster](https://marketplace.visualstudio.com/items?itemName=sburg.vscode-javascript-booster) (CodeActions), [journal de la Console de Turbo](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log), [ Membre suivant/précédent de GoTo](https://marketplace.visualstudio.com/items?itemName=mishkinf.goto-next-previous-member), [défilement automatique](https://github.com/PejmanNik/vscode-autoScroll?files=1), [NPM importation Version](https://marketplace.visualstudio.com/items?itemName=axetroy.vscode-npm-import-package-version) (❌), [importer coût](https://github.com/wix/import-cost) (❌) | ✅ <sup>2</sup> | ❌ <sup>3</sup> |
| REPLs | [Client REST](https://marketplace.visualstudio.com/items?itemName=humao.rest-client), [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner), [Quokka.js](https://marketplace.visualstudio.com/items?itemName=WallabyJs.quokka-vscode), [R](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) | ✅ <sup>4</sup> | ❌ <sup>3</sup>  |
| Gestionnaires de ressources | [MSSQL](https://marketplace.visualstudio.com/items?itemName=ms-mssql.mssql), [ftp simple](https://marketplace.visualstudio.com/items?itemName=humy2833.ftp-simple), [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [Docker](https://marketplace.visualstudio.com/items?itemName=PeterJausovec.vscode-docker), [Brew de Services](https://marketplace.visualstudio.com/items?itemName=beauallison.brew-services) | ✅ <sup>5</sup> | ❌ <sup>3</sup>  |

<sup>1</sup> *, sauf si un utilisateur a été déjà familiarisé avec un extrait de code, qu’elles n’attendent qu’elle soit disponible, et par conséquent, ce qui les rend partagé n’est pas forcément judicieux.*

<sup>2</sup> *ces catégories d’extension sont donc diverses, qu’il est impossible de dire elles fonctionnent toutes. Toutefois, en théorie, ils doivent, et nous allons suivre la clé de ceux qui ne.*

<sup>3</sup> *ces catégories d’extension peuvent tirer parti des expériences de collaboration, et nous avons besoin de commentaires de l’utilisateur final de savoir que !*

<sup>4</sup> *qui nécessitent l’invité pour les outils de runtime est installés (par exemple, Node.js) et fonctionne en exécutant le code localement.*

<sup>5</sup> *ces fonctionne en vous connectant à un serveur quelconque et peuvent fonctionner avec deux serveurs centralisés, les serveurs qui l’invité a partagé.*

### <a name="visual-studio"></a>Visual Studio

À venir.

## <a name="project-specific-extensions"></a>Extensions spécifiques au projet

Extensions de l’hôte installé, qui gèrent la modification, la génération et débogage d’une application de base et sont spécifiques à une langue/plateforme/library/Kit de développement logiciel, doivent être automatiquement disponibles pour les invités, sans avoir à installer quoi que ce soit. De cette façon, hôtes peuvent configurer leur environnement pour prendre en charge le développement productif d’un projet et autoriser leurs invités à instantanément les joindre, sans les composants requis supplémentaires. Étant donné que les extensions spécifiques au projet ne sont pas subjective ou personnels en aucune façon, ils peuvent être déterministe partagés à partir de l’hôte-invité, sans affecter l’environnement familier de tous les utilisateurs.

En outre, pour prendre en charge les extensions spécifiques au projet un invité ont été installés, mais l’hôte ne, qu’elles dans l’idéal, fournissent une expérience dégradée, fonctionnelle (par exemple, l’obtention d’un fichier unique intellisense, la possibilité de mettre en forme un document).

| Category | Exemple (s) | Partagé ? | Invité-pris en charge ? |
|-------|----------|--------|-----|
| Grammaires / la coloration syntaxique | [Interpréteur de commandes de poissons](https://marketplace.visualstudio.com/items?itemName=TeddyDD.fish), [Nginx](https://marketplace.visualstudio.com/items?itemName=shanoor.vscode-nginx), [Vetur](https://marketplace.visualstudio.com/items?itemName=octref.vetur), [DotEnv](https://marketplace.visualstudio.com/items?itemName=mikestead.dotenv), [ES6 chaîne HTML](https://marketplace.visualstudio.com/items?itemName=hjb2012.vscode-es6-string-html), [Todo +](https://marketplace.visualstudio.com/items?itemName=fabiospampinato.vscode-todo-plus), [Arc-en-ciel CSV](https://marketplace.visualstudio.com/items?itemName=mechatroner.rainbow-csv) | ❌ | ✅ |
| Services de langage | [YAML](https://marketplace.visualstudio.com/items?itemName=redhat.vscode-yaml), [Intellisense de chemin d’accès](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [ARM](https://marketplace.visualstudio.com/items?itemName=msazurermtools.azurerm-vscode-tools) | ✅ <sup>1</sup>| ✅ <sup>2</sup> |
| Schémas JSON | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions) | ✅ | ✅ |
| Linters | [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint), [Markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint), [Code vérificateur orthographique](https://marketplace.visualstudio.com/items?itemName=streetsidesoftware.code-spell-checker), [PHPCS](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs) | ✅ | ✅ <sup>2</sup>  |
| Formateurs | [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode), [Beautify](https://marketplace.visualstudio.com/items?itemName=HookyQR.beautify) | ✅ | ✅ <sup>2</sup> |
| Débogueurs | [Python](https://marketplace.visualstudio.com/items?itemName=ms-python.python), [débogueur pour Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome) | ✅ <sup>3</sup> | ❌ <sup>4</sup> |
| Exécuteurs de test | [Java Test Runner](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-test), [Mocha Sidebar](https://marketplace.visualstudio.com/items?itemName=maty.vscode-mocha-sidebar), [Postman Runner](https://marketplace.visualstudio.com/items?itemName=eridem.vscode-postman), [Jest Runner](https://marketplace.visualstudio.com/items?itemName=firsttris.vscode-jest-runner), [Neptune](https://marketplace.visualstudio.com/items?itemName=LambdaFactory.neptune) | ❌ <sup>5</sup> | ✅ <sup>2</sup> |
| Générateurs d’aperçu de fichier personnalisé | [Aperçu SVG](https://marketplace.visualstudio.com/items?itemName=cssho.vscode-svgviewer), [GraphViz](https://marketplace.visualstudio.com/items?itemName=joaompinto.vscode-graphviz), [Markdown taille de l’Image](https://marketplace.visualstudio.com/items?itemName=bierner.markdown-image-size) | ❌ |  ✅ |
| Générateurs de fichier/projet | [Azure Functions](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azurefunctions), [Générateur de projet C/C++](https://marketplace.visualstudio.com/items?itemName=danielpinto8zz6.c-cpp-project-generator) | ❌ | ❌<sup>6</sup> |
| Fournisseurs de contrôle de code source | [SVN](https://marketplace.visualstudio.com/items?itemName=johnstoncode.svn-scm), [Hg](https://marketplace.visualstudio.com/items?itemName=mrcrowl.hg) | ❌ | ❌ |

<sup>1</sup> *actuellement, seuls C# et JavaScript/TypeScript, avec plus de prise en charge sera bientôt disponible.*

<sup>2</sup> *uniquement en charge dans le document actif, comme invités n’ont pas accès aux fichiers locaux.*

<sup>3</sup> *l’expérience de débogage de noyau est partagé, toutefois, tous les serveurs lancées ne sont pas transférés automatiquement.*

<sup>4</sup> *invités n’ont pas une copie locale de l’application, et par conséquent, l’application en cours d’exécution et des sessions de débogage doivent démarrer sur l’ordinateur de l’hôte.*

<sup>5</sup> *la sortie d’une série de tests nécessiterait que les terminaux qui en résulte, les volets de sortie et les erreurs ont été également partagés avec les invités.*

<sup>6</sup> *presque tous ces utiliserait le Node.js `fs` module directement pour créer des fichiers qui ne fonctionnerait pas.*

### <a name="visual-studio"></a>Visual Studio

À venir.

## <a name="known-issues"></a>Problèmes connus

Problèmes connus d’extension, qui peuvent les empêcher de fonctionner pour les invités dans le contexte d’une session de collaboration (ainsi que leurs solutions de contournement) et par conséquent, peuvent avoir un impact sur leur flux de travail sont les suivantes :

### <a name="visual-studio-code"></a>Visual Studio Code

| Problème | Raison | Solution de contournement |
|-|-|-|
| L’aide de Node.js `fs` module pour détecter/lecture de fichiers (par exemple, un fichier de configuration) ou énumérer des répertoires (et vous n’êtes pas un service de langage). | Invités n’ont pas accès aux fichiers locaux. | 1. Dégradation de l’expérience utilisateur *(si possible).*<br /><br />2. Utilisez le `openTextDocument` et `findFiles` API pour lire et d’énumérer les fichiers de l’espace de travail. |
| L’aide de Node.js `fs` module pour créer ou écrire des fichiers | *Comme ci-dessus* | *N/a* vous pouvez utiliser la `openTextDocument(Uri)` API pour créer un `untitled` fichier, mais vous ne pouvez pas l’enregistrer directement sur le système de fichiers à un emplacement spécifique. |
| Selon une bibliothèque regroupés de projet ou l’outil | *Comme ci-dessus* | 1. Une version de secours de la dépendance avec l’extension du bundle<br><br> 2. Prend en charge une installation globale pour débloquer invités s’ils choisissent d’installer de manière explicite.<br><br> 3. Accédez à distance l’état/action si possible, puisque l’hôte n’auriez les dépendances de droite. |
| L’aide de Node.js `fs` module permettant de créer un répertoire | *Comme ci-dessus* | *N/A* |
| Limitant les fonctionnalités pour les documents qui utilisent le `file` schéma. | Fichiers sur l’utilisation de l’invité côté la `vsls` schéma. | Ajouter la prise en charge de `vsls` documents ([exemple](https://github.com/CoenraadS/BracketPair/pull/73)) |
| À l’aide de la `Uri.file` méthode et/ou `Uri.fsPath` / `TextDocument.fileName` membres à sérialiser/analyse des URI | *Comme ci-dessus* | Utilisez `Uri.parse` et `Url.toString()` au lieu de cela, laquelle maintenir et respectent les schémas de fichier ([exemple](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| À l’aide de la `workspace.openTextDocument` méthode avec un chemin d’accès de fichier au lieu d’un `Uri` | *Comme ci-dessus* | Fournir un `Uri` instance au lieu d’une chaîne de chemin d’accès de fichier brut ([exemple](https://github.com/micnil/vscode-checkpoints/pull/2)) |
| À l’aide de la `workspace.rootPath` propriété pour détecter la présence d’un espace de travail | Le `workspace.rootPath` les appels de propriété `Uri.fsPath` sur le premier `workspaceFolder` dans le `workspace`, qui a le même problème mentionné ci-dessus | Utilisez le `workspace.workspaceFolders` propriété pour détecter la présence d’un espace de travail à la place et si nécessaire, en revue chacune `workspaceFolder`de `Uri.scheme` pour déterminer s’il est local ou non |
| Ne pas spécifier un schéma de document lors de l’inscription des services de langage (via un `LanguageClient`, ou le `languages.register*` méthodes) | Invités recevront les résultats de service de langage à partir de leurs extensions locales et à l’hôte et par conséquent, si les deux participants ont la même extension de service de langage installée, invités ne voient pas les entrées en double pour certains éléments (par exemple, la saisie semi-automatique, code actions) | Restreindre les services de langage seulement `file` et `untitled` schémas ([exemple](https://github.com/vuejs/vetur/pull/756/files)) |
| Ne pas de vérification d’un document `Uri.scheme` avant le remplissage un `DiagnosticCollection` pour celui-ci | *Comme ci-dessus* | Générer uniquement `Diagnostics` pour `documents` dont `Uri.scheme`  ===  `file` ([exemple](https://github.com/Huachao/vscode-restclient/pull/196)) |
| Ne pas de vérification pour le schéma de l’espace de travail lors du retour `Tasks` à partir d’un personnalisé `TaskProvider`  | Invités affichent toutes les tâches à distance et locales et par conséquent, afficherait les doublons si les deux participants avaient la même extension qu’installée  | Retourner uniquement les `Tasks` pour `WorkspaceFolder`s dont `Uri.scheme`  ===  `file` ([exemple](https://github.com/Microsoft/vscode-eslint/blob/0fdb7c74b093cae9dc08355e7235582a254f24c2/client/src/tasks.ts#L42)) |

### <a name="visual-studio"></a>Visual Studio

À venir.

<!--

## Extensibility API

In addition to the core goals outlined in the beginning of this document, Live Share also wants to enable extension authors to enhance the default sharing experience in the following ways:

1. Contributing to the core collaborative feature set, based on behavior that only the extension would know about. In these scenarios, the host could have an extension installed, and potentially allow guests to benefit from it without also needing to have it installed

2. Enhancing their own experiences to be collaborative (e.g. syncing bookmarks between participants), by synchronizing any custom state and UI interactions. In these scenarios, only participants that had the custom extension installed would be able to take advantage of the added collaboratively.

This will require some form of API/SDK, which extensions can use to determine if/when the end-user is within a Live Share session, and if so, light up additional capabilities. The following represents a high-level overview of some of the extension points we've identified, and look forward to getting further feedback on:

| Shared Resource | Extensibility Point(s) |
|------------------|---------------------|
| User status | 1. Retrieving the list of participants within the current Live Share session (e.g. the [Git Co-Authors](https://marketplace.visualstudio.com/items?itemName=drrouman.git-coauthors) extension could use that to populate the host's commit message with)<br /><br /> 2. Updating a participant's location (outside of just editors), as well as allowing other participant's to jump to/pin to them as they move into custom extension UI (e.g. a participant is navigating a MongoDB database using the [Azure Cosmos DB](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-cosmosdb) extension). |
| Workspace | *N/A* - Live Share can transparently share all files, edits, cursors and highlights, without requiring an extension to do anything extra if it modified the file system and/or cursor/highlight position. |
| Language Services | *N/A* - Long-term, Live Share can transparently remote all language services (e.g. go to definition, document formatting, CodeLens) to the guest, including those that are contributed via extensions (e.g. [Path Intellisense](https://marketplace.visualstudio.com/items?itemName=christian-kohler.path-intellisense), [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)) |
| Debugging Sessions | *N/A* - Live Share can transparently remote all debugging sessions, including those that are enabled by custom extensions (e.g. [Debugger for Chrome](https://marketplace.visualstudio.com/items?itemName=msjsdiag.debugger-for-chrome)) |
| Servers | 1. Sharing a server that an extension was responsible for starting, and then optionally specifying whether a browser should be launched on the guest's machine as well (e.g. a debug adapter that launched a web server).  |
| Custom | 1. Synchronizing arbitrary state and/or user interactions (e.g. the [Bookmarks](https://marketplace.visualstudio.com/items?itemName=alefragnani.Bookmarks) extension syncing CRUD operations across participants, the [Maven for Java](https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-maven) extension exposing the project-wide view to guests) |

-->

## <a name="see-also"></a>Voir aussi

- [Prise en charge de langues et de plateformes](platform-support.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)
- [Tous les bogues majeurs, demandes de fonctionnalités et limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
