---
title: Détails de l’installation Linux - partage en direct de Visual Studio | Microsoft Docs
description: Obtenir des informations détaillées sur l’installation de partage en direct de Visual Studio sur Linux.
ms.custom: ''
ms.date: 10/6/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 9ac16b0e598fb07446c2b682397684b7e2e4709a
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640131"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Détails de l’installation Linux

Linux est un environnement très variable et le grand nombre d’environnements de bureau et de distributions peut compliquer le travail. Si vous respectez les versions prises en charge de **bureau Ubuntu** (16.04 +), **CentOS 7**, ou **station de travail Fedora** (27 +) et utilisent uniquement **distributions officielles de VS Code**, vous devez rechercher le processus simple. Toutefois, si vous utilisez une configuration non standard ou une distribution en aval, il n’est pas exclu que vous rencontriez des difficultés. Ce document fournit des informations sur la configuration requise et des informations de dépannage qui peuvent vous aider à être opérationnel et en cours d’exécution même si vous configuration est la seule Communauté pris en charge. Notez que le partage Live prend uniquement en charge **Linux 64 bits**.

## <a name="install-linux-prerequisites"></a>Installer les composants requis pour Linux

Certaines distributions de Linux n’ont pas de bibliothèques dont Live Share a besoin pour fonctionner. Par défaut, Live Share tente de détecter et d’installer les composants requis pour Linux pour vous. Lorsque Live Share rencontre un problème pouvant être dû à des bibliothèques manquantes, vous voyez une notification toast qui vous demande l’autorisation de les installer.

![Message de montrant notification toast manquent des conditions préalables de Linux](../media/vscode-linux-prereq-missing.png)

Lorsque vous cliquez sur « Installer », une fenêtre de terminal s’affiche dans lequel votre système d’exploitation vous demandera d’entrer votre administrateur / racine (sudo) le mot de passe pour continuer. En supposant que le script se termine correctement, recharger Visual Studio Code, lorsque vous êtes invité à vous devrait être prêt ! Vous souhaitez également peut-être consulter **[Conseils par distribution](#tips-by-distribution)** pour voir d’autres conseils et des solutions de contournement s’il y en a.

Si vous voyez un message indiquant que le script ne prend pas en charge votre distribution, consultez **[Conseils pour les distributions de la communauté prises en charge](#tips-for-unsupported-distros)** pour lire les informations que la communauté a partagées avec nous.

Si vous **pour ne plus avoir de VS Code, exécutez la commande pour vous**, vous pouvez aussi pour réexécuter la toute dernière version de ce script à tout moment manuellement à l’aide de la commande suivante dans une fenêtre de Terminal :

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Conseils par distribution

Pendant l’installation de la condition préalable script ci-dessus aborde les diverses distributions, vous vous demandez peut-être ce qui manque généralement à partir d’installations vanille. La liste suivante présente les bibliothèques principales qui étaient absentes dans une nouvelle installation d’une distribution donnée. La liste fournit également quelques conseils qui peuvent vous aider à être rapidement opérationnel si vous rencontrez un problème.

| Distribution | Vanille installer les bibliothèques manquants | Étapes supplémentaires |
|--------|-------------------|----|
| Bureau Ubuntu 18.04 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Bureau Ubuntu 16.04 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16.04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18.04 (64 bits) |&lt;none&gt;  | <ul><li>Vérifiez « lancer services GNOME au démarrage » est activée dans l’onglet « Avancé » de « Démarrage et de Session ».</li><li>Si vous rencontrez des problèmes de connexion, installez `seahorse`, démarrer des « Mots de passe et clés », vérifiez que vous avez porte-clés de « Connexion » et que vous pouvez le déverrouiller.</li></ul> |
| Xubuntu 16.04 (64 bits) | &lt;none&gt; | <ul><li>Vérifiez « lancer services GNOME au démarrage » est activée dans l’onglet « Avancé » de « Démarrage et de Session ».</li><li>Si vous rencontrez des problèmes de connexion, installez `seahorse`, démarrer des « Mots de passe et clés », vérifiez que vous avez porte-clés de « Connexion » et que vous pouvez le déverrouiller.</li></ul> |
| Cannelle Mint 19 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Mint 18,3 cannelle (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| 10 Debian (Buster) test (64 bits) | Pas de version stable, par conséquent, inconnu. | <ul><li>Debian test et instable (Sid) ne sont pas pris en charge officiellement.</li><li>Il existe un [problème connu](https://github.com/dotnet/corefx/issues/33179) dans .NET Core qui affecte le partage en direct. </li><li>Consultez [ici pour une solution de contournement](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249).</li></ul> |
| Debian 9 GNOME Desktop (64 bits) | &lt;none&gt; | <ul><li>Vous devrez peut-être installer `sudo` et ajoutez votre utilisateur au groupe sudo pour utiliser le script d’installation automatisée.</li>  |
| Station de travail Fedora 29 (64 bits) | `openssl-compat10` | &lt;none&gt; |
| Station de travail Fedora 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Station de travail Fedora 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Bureau GNOME centOS 7 (64 bits) | &lt;none&gt; | &lt;none&gt; |

Consultez **[conseils pour les distributions de communauté pris en charge](#tips-for-community-supported-distros)** pour plus d’informations sur les autres Debian-non / Ubuntu ou RHL basé distributions.

Des détails supplémentaires figurent également [ci-dessous](#detailed-library-requirements) sur les bibliothèques spécifiques Partage Live a besoin.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Conseils pour les distributions de communauté pris en charge

Distributions en dehors de la Debian / Ubuntu ou RHL arborescences ne sont pas officiellement pris en charge par Visual Studio Code ou .NET Core. Par conséquent, par extension, ils ne sont pas officiellement pris en charge par le partage en direct de Visual Studio soit. Toutefois, la Communauté a contribué à des informations utiles sur la route de partage en direct et en cours d’exécution sur un nombre de distributions supplémentaires.

> **Demandes de tirage d’accueil :** Si vous êtes intéressé par la mise à jour de ces informations avec votre distribution préférée, envoyez une demande de tirage pour [ce fichier](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) dans notre référentiel GitHub de documents. Mieux encore, si vous souhaitez obtenir le programme d’installation de dépendance prenant en charge de votre distribution préférée, vous pouvez soumettre une demande de tirage [pour ce fichier](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Distribution | Utilisation ? | Vanille installer les bibliothèques manquants | Étapes supplémentaires |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Oui | Varie. Bibliothèques possibles : `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Prise en charge par le [script d’installation prérequis](#install-linux-prerequisites).</li><li>Utilisez le [visual-studio-code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) package arch pour VS Code.</li><li>`sudo` besoin d’être installé pour utiliser la condition préalable automatisée installera script.</li><li>`gnome-keyring` peut nécessiter supplémentaires [étapes d’installation](https://wiki.archlinux.org/index.php/GNOME/Keyring) dans certains environnements de postes de travail.</ul> |
| Manjaro 17.1 (64 bits) | Oui | `xorg-xprop liburcu` | <ul><li>Prise en charge par le [script d’installation prérequis](#install-linux-prerequisites).</li><li>Utilisez le [visual-studio-code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) package arch pour VS Code.</li></ul> |
| openSuSE LEAP 15 KDE (64 bits) | Oui | `libopenssl1_0_0 gnome-keyring` | <ul><li>Prise en charge par le script d’installation requis.</li></ul> |
| 3 solus (64 bits) | Oui | `xprop` | <ul><li>Prise en charge par le [script d’installation prérequis](#install-linux-prerequisites).</li><li>Les versions de la `vscode` package avant la version 57 ont été pas les valeurs de product.json requis ([voir ci-dessous](#vs-code-oss-issues)). Mettre à niveau le `vscode` package pour résoudre ce problème.</li></ul> |
| Gentoo (64 bits) | Oui | Très variable. Packages manquants possibles : `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>Le `visual-studio-code` du package dans le **jorgicio** superposition est connue pour fonctionner.</li></ul>

## <a name="install-prerequisites-manually"></a>Installer manuellement les composants requis

 Bien que nous recommandons l’utilisation du partage de Live **script d’installation de dépendance**, cette section fournit des informations complémentaires sur les exigences de la bibliothèque dans la cas où vous souhaiteriez effectuer ces étapes vous-même ou utilisez une distribution non pris en charge par le script.

Typiques bibliothèques manquants dans les installations vanille se trouve dans le [conseils par distribution](#tips-by-distribution) et [conseils pour les distributions de communauté pris en charge](#tips-for-unsupported-distros) sections.

### <a name="detailed-library-requirements"></a>Exigences détaillées de bibliothèque

Configuration requise de Visual Studio Live partage bibliothèque native proviennent de son utilisation de .NET Core 2.1, libsecret pour conserver les informations d’identification et son intégration au navigateur. Le tableau suivant récapitule ces exigences pour les distributions officiellement pris en charge par .NET Core.

| Distribution | .NET core impératifs | Demandes de stockage d’informations d’identification| Demandes d’intégration de navigateur |
|--------------|-----------|--------------------|------------|
| Ubuntu et les distributions en aval | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (pour Ubuntu 16.04, générer des 18,3) ou `libicu57` (pour Ubuntu 17.10) ou `libicu60` (pour Ubuntu 18.04, générer des 19) | `libsecret-1-0 gnome-keyring` (ou libsecret pris en charge le porte-clés - Kwallet ne prend pas en charge libsecret) | `desktop-file-utils x11-utils` |
| Distributions Debian 9 et en aval | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (ou libsecret pris en charge le porte-clés - Kwallet ne prend pas en charge libsecret) | `desktop-file-utils x11-utils` |
| RHL / CentOS/ Fedora | `openssl-libs krb5-libs zlib libicu` Fedora nécessite également `compat-openssl10`| `libsecret gnome-keyring` (ou libsecret pris en charge le porte-clés - Kwallet ne prend pas en charge libsecret) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (ou libsecret pris en charge le porte-clés - Kwallet ne prend pas en charge libsecret) | `desktop-file-utils xprop`

Tandis que les autres distributions requièrent les mêmes bibliothèques, leurs noms de package peuvent varier. Vous trouverez certaines d'entre elles dans le [conseils pour les distributions de communauté pris en charge](#tips-for-unsupported-distros) section.

### <a name="debian--ubuntu"></a>Debian / Ubuntu

Bibliothèques peuvent être installés sur les distributions Debian/Ubuntu basée en exécutant `sudo apt install <library-name>` dans un terminal.

Pour les distributions Ubuntu en y compris Mint, exécutez :

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Pour Debian 9 et les distributions en aval non Ubuntu, exécutez :

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora / CentOS / RHL

Bibliothèques peuvent être installés sur les distributions Fedora/CentOS/RHL basé en exécutant `sudo yum install <library-name>` dans un terminal. Par exemple, cela installera tous les éléments :

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problèmes de Code OSS VS

> **Arch Linux/Manjaro utilisateurs :** Utilisez le [visual-studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) package arch pour éviter ce problème.

Packages de Visual Studio Code soit vanille ou versions modifiées des systèmes d’exploitation VS Code peuvent être critiques valeur manquante dans `product.json` fichier qui empêche l’activation de partage en direct de Visual Studio.

Un moyen rapide de voir vous ait atteint ce problème consiste à accéder à l’aide > « Activer/désactiver les outils de développement » et voir si vous trouvez une trace de pile qui indique l’extension de partage en direct n’avez pas activé, car elle utilisait une « API proposée ».

Pour vérifier que c’est votre problème, vérifiez le contenu du `product.json`. L’emplacement du fichier varie-t-elle en package, mais il est généralement dans un des emplacements suivants :

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Si le `extensionAllowedProposedApi` propriété est manquante ou vous ne voyez pas « ms-vsliveshare.vsliveshare » référencé, vous utilisez une version Open source avec ce problème.

Comme un **solution de contournement**, vous pouvez ajouter le texte suivant dans le product.json :

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Consultez [ci-dessus](#tips-for-community-supported-distros) pour plus d’informations sur indique si la distribution que vous utilisez est connue pour fonctionner.

## <a name="linux-browser-integration"></a>Intégration du navigateur Linux

Généralement, Visual Studio Live Share **ne nécessite pas d’étapes d’installation supplémentaires** pour activer l’intégration d’un navigateur sur Linux.

Pour ce faire, Partage Live place automatiquement un fichier de bureau dans `~/.local/share/applications` et le Lanceur requis lui-même dans `~/.local/share/vsliveshare` lorsque l’extension initialise tout d’abord. Si cette opération réussit, aucune action n’est requise de votre part.

Dans certains cas, les distributions ne pas prendre en charge cet emplacement ou nécessitent des ajustements pour qu’il fonctionne avec leurs installations vanille. Dans ce cas, Partage Live revient à l’utilisation `/usr/local/share` à la place. Par conséquent, **vous avertit que votre mot de passe administrateur (sudo) est requise** pour terminer le processus d’installation. Une fenêtre de terminal vous indiquant où le lanceur du navigateur sera installé s’affiche. Entrez simplement votre mot de passe lorsque vous y êtes invité et appuyez sur Entrée une fois l’installation terminée pour fermer la fenêtre de terminal.

Si vous préférez exécuter la commande vous-même au lieu de cela, vous pouvez cliquer sur « À la place les copier » qui copie la commande de terminal dans le Presse-papiers à la place.

Enfin, si vous choisissez d’ignorer cette étape entièrement, vous pouvez toujours [joindre manuellement des sessions de collaboration](../use/vscode.md#join-manually), mais vous ne serez pas en mesure de joindre en ouvrant un lien d’invitation dans le navigateur. Notez que vous pouvez toujours accéder à la commande plus tard, en appuyant sur **Ctrl + Maj + P / Cmd + Maj + P** et en sélectionnant le « partage en direct : Commande du Lanceur de l’installation ».

## <a name="see-also"></a>Voir aussi

- [Guide pratique : Travailler en collaboration à l’aide de Visual Studio Code](../use/vscode.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
