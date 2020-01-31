---
title: Détails de l’installation de Linux-Visual Studio Live Share | Microsoft Docs
description: Informations détaillées sur l’installation de Visual Studio Live Share sur Linux.
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
ms.openlocfilehash: 69bc178ebb4052757f984d67482d216335f46dac
ms.sourcegitcommit: 5180aab73c086cbded6aae01aa01f71fb991dee1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2020
ms.locfileid: "76818074"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="linux-installation-details"></a>Détails de l’installation de Linux

Linux est un environnement très variable et le grand nombre d’environnements de bureau et de distributions peut compliquer le travail. Si vous utilisez des versions prises en charge d' **Ubuntu Desktop** (16.04 +), de **CentOS 7**ou de **Fedora Workstation** (27 +) et que vous utilisez uniquement **des distributions officielles de vs code**, vous devriez trouver le processus directement. Toutefois, si vous utilisez une configuration non standard ou une distribution en aval, il n’est pas exclu que vous rencontriez des difficultés. Ce document fournit des informations sur les exigences et des informations de dépannage qui peuvent vous aider à devenir opérationnel même si votre configuration est uniquement prise en charge par la communauté. Notez que Live Share prend en charge uniquement **le Linux 64 bits**.

## <a name="install-linux-prerequisites"></a>Installer les composants requis pour Linux

Certaines distributions de Linux n’ont pas de bibliothèques dont Live Share a besoin pour fonctionner. Par défaut, Live Share tente de détecter et d’installer les composants requis pour Linux pour vous. Lorsque Live Share rencontre un problème pouvant être dû à des bibliothèques manquantes, vous voyez une notification toast qui vous demande l’autorisation de les installer.

![Notification Toast indiquant que les conditions préalables de Linux sont manquantes](../media/vscode-linux-prereq-missing.png)

Lorsque vous cliquez sur « installer », une fenêtre de terminal s’affiche à l’endroit où votre système d’exploitation vous demandera d’entrer votre mot de passe d’administrateur/racine (sudo) pour continuer. En supposant que le script se termine correctement, rechargez Visual Studio Code lorsque vous y êtes invité, vous devez être ensemble. Vous souhaitez également peut-être consulter **[Conseils par distribution](#tips-by-distribution)** pour voir d’autres conseils et des solutions de contournement s’il y en a.

Si vous voyez un message indiquant que le script ne prend pas en charge votre distribution, consultez **[Conseils pour les distributions de la communauté prises en charge](#tips-for-unsupported-distros)** pour lire les informations que la communauté a partagées avec nous.

Si vous **préférez ne pas avoir vs code exécuter la commande pour vous**, vous pouvez également choisir de réexécuter la version la plus récente de ce script à tout moment manuellement en utilisant la commande suivante dans une fenêtre de terminal :

    wget -O ~/vsls-reqs https://aka.ms/vsls-linux-prereq-script && chmod +x ~/vsls-reqs && ~/vsls-reqs

## <a name="tips-by-distribution"></a>Conseils par distribution

Tandis que le script d’installation de la configuration requise ci-dessus couvre une grande variété de distributions, vous vous demandez peut-être ce qui est généralement manquant dans les installations vanille. La liste suivante répertorie les bibliothèques de clés qui manquent dans une nouvelle installation d’une distribution donnée. La liste fournit également des conseils qui peuvent vous aider à devenir opérationnel si vous avez rencontré un problème.

| Point | Installation vanille des bibliothèques manquantes | Étapes supplémentaires |
|--------|-------------------|----|
| Ubuntu Desktop 18,04 (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Ubuntu Desktop 16,04 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Kubuntu 18,04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Kubuntu 16,04 (64 bits) | `gnome-keyring desktop-file-utils` | &lt;none&gt; |
| Xubuntu 18,04 (64 bits) |&lt;none&gt;  | <ul><li>Vérifiez que l’option « lancer les services GNOME au démarrage » est cochée sous l’onglet « avancé » de « session et démarrage ».</li><li>Si vous rencontrez des problèmes de connexion, installez `seahorse`, démarrez « mots de passe et clés », vérifiez que vous disposez de l’anneau « connexion » et que vous pouvez le déverrouiller.</li></ul> |
| Xubuntu 16,04 (64 bits) | &lt;none&gt; | <ul><li>Vérifiez que l’option « lancer les services GNOME au démarrage » est cochée sous l’onglet « avancé » de « session et démarrage ».</li><li>Si vous rencontrez des problèmes de connexion, installez `seahorse`, démarrez « mots de passe et clés », vérifiez que vous disposez de l’anneau « connexion » et que vous pouvez le déverrouiller.</li></ul> |
| Menthe 19 cannelle (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Menthe 18,3 cannelle (64 bits) | &lt;none&gt;  | &lt;none&gt; |
| Test Debian 10 (Buster) (64 bits) | La version n’est pas stable, donc inconnue. | <ul><li>Les tests Debian et instables (SID) ne sont pas officiellement pris en charge.</li><li>Il existe un [problème connu](https://github.com/dotnet/corefx/issues/33179) dans .net core qui affecte Live share. </li><li>[Pour une solution de contournement](https://github.com/dotnet/corefx/issues/33179#issuecomment-435118249), voir ici.</li></ul> |
| Debian 9, bureau GNOME (64 bits) | &lt;none&gt; | <ul><li>Vous devrez peut-être installer `sudo` et ajouter votre utilisateur au groupe sudo pour utiliser le script d’installation automatisé.</li>  |
| Station de travail Fedora 29 (64 bits) | `openssl-compat10` | &lt;none&gt; |
| Station de travail Fedora 28 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| Station de travail Fedora 27 (64 bits) | &lt;none&gt; | &lt;none&gt; |
| CentOS 7 GNOME Desktop (64 bits) | &lt;none&gt; | &lt;none&gt; |

Consultez les **[conseils relatifs aux distributions prises en charge](#tips-for-community-supported-distros)** par la communauté pour plus d’informations sur d’autres distributions non-Debian/Ubuntu ou RHL.

Vous trouverez des informations supplémentaires [ci-dessous](#detailed-library-requirements) sur les bibliothèques spécifiques Live share besoins.

<a name="tips-for-unsupported-distros"></a>

## <a name="tips-for-community-supported-distros"></a>Conseils pour les distributions pris en charge par la communauté

Les distributions en dehors des arbres Debian/Ubuntu ou RHL ne sont pas officiellement prises en charge par Visual Studio Code ou .NET Core. Par conséquent, par extension, ils ne sont pas officiellement pris en charge par l’Visual Studio Live Share. Toutefois, la Communauté a participé à des informations utiles sur la mise en Live Share et l’exécution de plusieurs distributions supplémentaires.

> **Page d’accueil de PRs :** Si vous souhaitez mettre à jour ces informations avec votre distribution favorite, envoyez un PR pour [ce fichier](https://github.com/MicrosoftDocs/live-share/tree/master/docs/reference/linux.md) dans notre document GitHub référentiel. Mieux encore, si vous souhaitez que le programme d’installation de dépendances prend en charge votre distribution favorite, vous pouvez envoyer un PR [pour ce fichier](https://github.com/MicrosoftDocs/live-share/blob/master/scripts/linux-prereqs.sh).

| Point | Utilisation? | Installation vanille des bibliothèques manquantes | Étapes supplémentaires |
|--------------|----------|-------------------|------------------|
| Arch Linux (64 bits) | Oui | Diffère. Bibliothèques possibles : `gcr liburcu openssl-1.0 krb5 zlib icu gnome-keyring libsecret desktop-file-utils xorg-xprop` | <ul><li>Pris en charge par le script d’installation de la [Configuration requise](#install-linux-prerequisites).</li><li>Utilisez le package Aur [Visual Studio-code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pour vs code.</li><li>`sudo` devrez installer pour utiliser le script d’installation des composants prérequis automatisés.</li><li>`gnome-keyring` peuvent nécessiter des [étapes de configuration](https://wiki.archlinux.org/index.php/GNOME/Keyring) supplémentaires dans certains environnements de bureau.</ul> |
| Manjaro 17,1 (64 bits) | Oui | `xorg-xprop liburcu` | <ul><li>Pris en charge par le script d’installation de la [Configuration requise](#install-linux-prerequisites).</li><li>Utilisez le package Aur [Visual Studio-code-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pour vs code.</li></ul> |
| openSuSE LEAP 15 KDE (64 bits) | Oui | `libopenssl1_0_0 gnome-keyring` | <ul><li>Pris en charge par le script d’installation de la configuration requise.</li></ul> |
| Solus 3 (64 bits) | Oui | `xprop` | <ul><li>Pris en charge par le script d’installation de la [Configuration requise](#install-linux-prerequisites).</li><li>Les versions du package `vscode` antérieures à la version 57 n’étaient pas des valeurs Product. JSON requises ([voir ci-dessous](#vs-code-oss-issues)). Mettez à niveau le package `vscode` pour résoudre ce problème.</li></ul> |
| Gentoo (64 bits) | Oui | Très variable. Packages manquants possibles : `dev-libs/openssl-1.0.2 net-libs/libgsasl dev-libs/icu sys-libs/zlib sys-apps/util-linux app-crypt/libsecret gnome-base/gnome-keyring x11-apps/xprop`| <ul><li>Le package `visual-studio-code` dans la superposition **jorgicio** est connu pour fonctionner.</li></ul>

## <a name="install-prerequisites-manually"></a>Installer manuellement les composants requis

 Bien que nous vous recommandons d’utiliser le **script d’installation de dépendances**de Live Share, cette section fournit des informations supplémentaires sur les conditions requises par la bibliothèque dans l’éventualité où vous souhaiteriez effectuer ces étapes vous-même ou utiliser une distribution non prise en charge par le script.

Les bibliothèques manquantes typiques dans des installations vanille se trouvent dans les sections [conseils par distribution](#tips-by-distribution) et [conseils pour les distributions prises en charge](#tips-for-unsupported-distros) par la communauté.

### <a name="detailed-library-requirements"></a>Spécifications de bibliothèque détaillées

La configuration requise de la bibliothèque native de Visual Studio Live Share provient de son utilisation de .NET Core 2,1, libsecret pour conserver les informations d’identification et son intégration au navigateur. Le tableau suivant récapitule ces exigences pour les distributions officiellement prises en charge par .NET Core.

| Point | Demandes .NET Core | Demandes de stockage des informations d’identification| Impératifs d’intégration du navigateur |
|--------------|-----------|--------------------|------------|
| Ubuntu et distributions en aval | `libssl1.0.0 libkrb5-3 zlib1g libicu55` (pour Ubuntu 16,04, menthe 18,3) ou `libicu57` (pour Ubuntu 17,10) ou `libicu60` (pour Ubuntu 18,04, menthe 19) | `libsecret-1-0 gnome-keyring` (ou libsecret pris en charge, keyring-KWallet ne prend pas en charge libsecret) | `desktop-file-utils x11-utils` |
| Debian 9 et distributions en aval | `libssl1.0.2 libkrb5-3 zlib1g libicu57` | `libsecret-1-0 gnome-keyring` (ou libsecret pris en charge, keyring-KWallet ne prend pas en charge libsecret) | `desktop-file-utils x11-utils` |
| RHL/CentOS/Fedora | `openssl-libs krb5-libs zlib libicu` Fedora nécessite également `compat-openssl10`| `libsecret gnome-keyring` (ou libsecret pris en charge, keyring-KWallet ne prend pas en charge libsecret) | `desktop-file-utils xorg-x11-utils` |
| Alpine Linux | `openssl1.0 icu krb5 zlib` | `libsecret gnome-keyring` (ou libsecret pris en charge, keyring-KWallet ne prend pas en charge libsecret) | `desktop-file-utils xprop`

Les autres distributions requièrent les mêmes bibliothèques, mais leurs noms de packages peuvent varier. Vous trouverez des exemples dans la section [conseils pour les distributions prises en charge par la communauté](#tips-for-unsupported-distros) .

### <a name="debian--ubuntu"></a>Debian/Ubuntu

Les bibliothèques peuvent être installées sur des distributions basées sur Debian/Ubuntu en exécutant `sudo apt install <library-name>` dans un terminal.

Pour les distributions Ubuntu, y compris les menthes, exécutez :

    sudo apt install libssl1.0.0 libkrb5-3 zlib1g libicu[0-9][0-9] gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

Pour les distributions Debian 9 et non-Ubuntu en aval, exécutez :

    sudo apt install libssl1.0.2 libkrb5-3 zlib1g libicu57 gnome-keyring libsecret-1-0 desktop-file-utils x11-utils

### <a name="fedora--centos--rhl"></a>Fedora/CentOS/RHL

Les bibliothèques peuvent être installées sur des distributions basées sur Fedora/CentOS/RHL en exécutant `sudo yum install <library-name>` dans un terminal. Par exemple, ceci permet d’installer tout :

    sudo yum install openssl-libs compat-openssl10 krb5-libs zlib libicu libsecret gnome-keyring desktop-file-utils xorg-x11-utils

## <a name="vs-code-oss-issues"></a>Problèmes liés au VS Code OSS

> **Utilisateurs Arch Linux/Manjaro :** Utilisez le package Aur [Visual Studio-bin](https://aur.archlinux.org/packages/visual-studio-code-bin) pour éviter ce problème.

Les packages de Visual Studio Code qui sont des versions vanille ou modifiées des VS Code OSS peuvent manquer une valeur critique dans `product.json` fichier qui empêche les Visual Studio Live Share d’être activés.

Pour voir rapidement ce problème, vous pouvez accéder à l’aide > « Activer/désactiver Outils de développement » et voir si vous trouvez une trace de la pile indiquant que l’extension de la Live Share ne s’est pas activée, car elle utilisait une « API proposée ».

Pour vérifier qu’il s’agit bien de votre problème, vérifiez le contenu de `product.json`. L’emplacement du fichier varie selon le package, mais il se trouve généralement à l’un des emplacements suivants :

- `/usr/share/code/resources/app/product.json`
- `/usr/share/vscode/resources/app/product.json`

Si la `extensionAllowedProposedApi` propriété est manquante ou si vous ne voyez pas « MS-vsliveshare. vsliveshare » référencé, vous utilisez une version OSS avec ce problème.

Pour **contourner ce problème**, vous pouvez ajouter ce qui suit dans le produit. JSON :

        "extensionAllowedProposedApi": [
          "ms-vsliveshare.vsliveshare",
          "ms-vscode.node-debug",
          "ms-vscode.node-debug2"
     ]

Pour plus d’informations sur le fonctionnement de la distribution que vous utilisez, consultez [ci-dessus](#tips-for-community-supported-distros) .

## <a name="linux-browser-integration"></a>Intégration du navigateur Linux

Généralement, Visual Studio Live Share **ne nécessite pas d’étapes d’installation supplémentaires** pour activer l’intégration d’un navigateur sur Linux.

Pour ce faire, Live Share place automatiquement un fichier de bureau dans `~/.local/share/applications` et le lanceur requis lui-même dans `~/.local/share/vsliveshare` lors de la première initialisation de l’extension. Aucune action n’est requise de votre part si cela se déroule correctement.

Dans certains cas, les distributions ne prennent pas en charge cet emplacement ou nécessitent des ajustements pour qu’elle fonctionne avec leurs installations vanille. Dans ce cas, Live Share utilise `/usr/local/share` à la place. Par conséquent, **vous pouvez être averti que votre mot de passe d’administrateur (sudo) est requis** pour terminer le processus d’installation. Une fenêtre de terminal vous indiquant où le lanceur du navigateur sera installé s’affiche. Entrez simplement votre mot de passe lorsque vous y êtes invité et appuyez sur Entrée une fois l’installation terminée pour fermer la fenêtre de terminal.

Si vous préférez exécuter la commande vous-même, vous pouvez cliquer sur « copier à la place » pour copier la commande de terminal dans le presse-papiers à la place.

Enfin, si vous choisissez d’ignorer cette étape, vous pouvez toujours [joindre les sessions de collaboration manuellement](../use/vscode.md#join-manually), mais vous ne pourrez pas vous joindre en ouvrant un lien d’invitation dans le navigateur. Notez que vous pouvez toujours accéder à la commande ultérieurement, en appuyant sur **Ctrl + Maj + P/CMD + MAJ + P** et en sélectionnant la commande « Live share : programme d’installation du lanceur ».

## <a name="see-also"></a>Voir aussi

- [Comment : collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Exigences de connectivité pour Live Share](connectivity.md)
- [Fonctionnalités de sécurité de Live Share](security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
