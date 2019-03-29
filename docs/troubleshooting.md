---
title: Résolution des problèmes - partage en direct de Visual Studio | Microsoft Docs
description: Conseils et astuces de dépannage pour le partage en direct de Visual Studio.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: troubleshooting
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 5fc611714d148a9ba1d5a6848e0399af753d1a37
ms.sourcegitcommit: 100fce9b9bbcd7e6f68d40659bd2760e9537de37
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/29/2019
ms.locfileid: "58640209"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Résolution des problèmes de partage en direct de Visual Studio

Cet article couvre la résolution des problèmes des conseils, des solutions de contournement et des réponses pour les questions et problèmes courants. Vous pouvez également jeter un coup de œil à la [FAQ](faq.md). 

## <a name="installation--tool-requirements"></a>Installation / configuration requise de l’outil

Les éléments suivants sont des conseils de dépannage liés à l’installation de partage en direct de Visual Studio.

| Tool | Problème | Résolution / solution de contournement |
|------|---------|------------|
| VS | Le programme d’installation de l’extension <strong>ne peut pas trouver une version de Visual Studio</strong> à utiliser lors de la tentative d’installer l’extension de le Partage Live Visual Studio. | Partage en direct de Visual Studio nécessite **Visual Studio 2017 version 15.6** ou une version ultérieure pour les hôtes et invités. Installer la dernière stable [mise à jour de Visual Studio 2017](https://visualstudio.com/vs/) et recommencez.|
| VS Code | Une erreur s’affiche lorsque vous tentez d’utiliser le partage en direct de Visual Studio avec Visual Studio Code sur macOS <strong>El Capitan ou ci-dessous</strong>. | Prise en charge de Visual Studio Live du partage du système d’exploitation est dépendant de .NET Core qui actuellement [prend uniquement en charge macOS Sierra et jusqu'à.]((https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md).) |
| VS Code | Un «**dépendances n’ont pas pu être installées**» erreur apparaît le pendant qu’extension est **fin de l’installation** sur le premier démarrage ou si vous obtenez des erreurs **manquant ou déjà présent fichiers**. | Vérifiez que vous êtes sur un **bonne connexion réseau**. Si vous êtes, vous pouvez exécuter dans un **proxy ou pare-feu** problème. Consultez [la résolution des problèmes de connectivité](#connectivity). <br /><br />|
| VS Code | L’installation de l’extension de le Partage Live Visual Studio à partir de la place de marché <strong>installe dans la version stable/initiés de VS Code</strong> au lieu de la version souhaitée. | Démarrer VS Code stable ou en insiders selon votre préférence, cliquez sur l’onglet « extensions », recherchez « Visual Studio Live Share » et installer à partir de là. |
| VS Code (**Linux**) | L’extension de partage en direct n’active pas et **aucun élément de barre d’état s’affichent** après l’installation de l’extension sur **Linux**. | Partage en direct de Visual Studio dépend de .NET Core 2.0 qui comporte un nombre de conditions préalables de Linux qui peuvent ne pas être satisfaites sur certaines distributions de Linux par défaut. Consultez [ici pour plus d’informations](reference/linux.md#install-linux-prerequisites) sur ce qui doit être installé. |

## <a name="sign-in"></a>Se connecter

Les éléments suivants sont des conseils de dépannage pour les problèmes de connexion.

| Tool | Problème | Résolution / solution de contournement |
|------|---------|------------|
| VS | Vous devez vous connecter à Visual Studio Live Share avec un <strong>autre identité</strong> que vous utilisez pour vous connecter à Visual Studio. | Accédez à outils > Options > Partage Live > compte d’utilisateur pour sélectionner un autre compte. |
| VS Code | Lors d’une fenêtre de navigateur affiche des pendant la connexion et le processus <strong>semblera avoir réussi sur la page web</strong>, la barre d’état <strong>indique toujours, « Connexion »</strong> après la fermeture du navigateur. | Après vous être connecté, cliquez sur « Difficultés ? » et suivez les instructions pour entrer un code utilisateur temporaire dans l’outil.<br /><br />Nous aimerions également voir ce qui peut se produire, donc Veuillez [enregistrer un bogue](https://aka.ms/vsls-problem). |
| Tous | Vous obtenez un <strong>délai d’expiration ou erreur de connexion</strong>. | Consultez [la résolution des problèmes de connectivité](#connectivity). |
| Tous | Lorsque la connexion à l’aide d’un Microsoft soutenu **Professionnel ou scolaire d’adresse de messagerie** vous voyez un message indiquant, **« Besoin d’approbation administrateur »**. | Votre principe d’Azure AD est configurée pour exiger des « consentement de l’administrateur » pour accéder au contenu du répertoire de nouvelles applications. Consultez [ici](reference/security.md) pour plus d’informations. |
| VS Code (**macOS**) | Lorsque la connexion vous voyez une erreur indiquant **SecKeychainAddGenericPassword() échoué**. | Il s’agit généralement en raison d’un problème courant avec macOS où les modifications de mot de passe ne sont pas répercutées dans le trousseau de connexion. Essayez aborder « Accès au trousseau », le trousseau de connexion de verrouillage et déverrouillage à nouveau. Cela peut être suffisant pour résoudre le problème, mais si vous ne pouvez pas déverrouiller avec votre mot de passe actuel, essayez-en votre précédente. Si cela fonctionne, modifiez le mot de passe de trousseau de connexion à votre mot de passe actuel. Consultez [ici](https://support.apple.com/en-us/HT201609) pour plus d’informations. |
| VS Code (**Linux**) | Lorsque vous entrez dans le code utilisateur après vous être connecté via le navigateur affiche une erreur indiquant **secret_password_store_sync() a échoué avec le code d’erreur XX**. | Cela est généralement dû à `gnome-keyring` et/ou `libsecret-1-0` /  `libsecret` ne pas en cours d’installation. Vous pouvez valider gnome-porte-clés est correctement configuré en installant `seahorse` , puis en utilisant l’application « Mots de passe et clés » dans votre environnement de bureau. En savoir plus sur [ici les conditions préalables Linux](reference/linux.md#install-linux-prerequisites). |
| VS Code (**Linux**) | Vous êtes <strong>vous y êtes invité à entrer un code utilisateur</strong> avec Partage Live v0.3.295 ou version antérieure, mais aucun navigateur ne semble vous permettent d’obtenir un. | Nous nous efforçons d’éliminer la nécessité de code utilisateur sur Linux. Pendant ce temps, une fenêtre de navigateur doit apparaître pour vous permet de vous connecter. Si ce n’est pas le cas, la fenêtre du navigateur peut être cachée sous VS Code. Consultez le Conseil suivant si cela n’est pas le cas.  |
| VS Code | Après avoir cliqué sur « Connexion » (ou à l’aide de la « partage en direct : Commande Sign in »), <strong>aucune fenêtre de navigateur s’affiche pour vous permettre d’entrer vos informations d’identification</strong>. | 1. [Connectez-vous ici](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. Après vous être connecté, cliquez sur « Difficultés ? »<br /> 3. Suivez les instructions pour entrer un code utilisateur temporaire dans l’outil. |
| Tous | Vous aimeriez <strong>jointure</strong> une session de collaboration</strong> mais <strong>n’ont pas / ne doivent pas recevoir de mises à jour de la messagerie</strong>. | Connexion à l’extension de partage en direct dans Visual Studio/VS Code est <strong>pas</strong> vous choisir de recevoir des mises à jour de l’e-mail.<br /><br />Partage en direct nécessite des invités pour vous connecter en tant qu’une mesure de sécurité afin de l’hôte a une visibilité à l’identité de ceux qui ont rejoint. [Voter pour cette fonctionnalité](https://github.com/MicrosoftDocs/live-share/issues/3) si vous souhaitez que l’option pour autoriser les utilisateurs anonymes à joindre (par exemple, les utilisateurs sans nom / nom défini par l’utilisateur). |

## <a name="share-and-join"></a>Partage et jointure

Les éléments suivants sont des conseils de dépannage pour les problèmes de connexion.

| Tool | Problème | Résolution / solution de contournement |
|------|----------------|------------|
| Tous | <strong>Partage/jointure :</strong> Vous obtenez un délai d’attente ou une erreur sur ne pas pouvoir se connecter. | Consultez [la résolution des problèmes de connectivité](#connectivity). |
| VS Code | <strong>Jointure :</strong> Vous étiez <strong>non demandées par invite / en mesure de lancer VS Code</strong> après l’ouverture de la page d’inscription dans un navigateur. |  Conseils : <ul><li>Vérifiez que vous avez <i>démarré le Code de Visual Studio au moins une fois et a attendu pour l’installation dans la barre d’état.</i></li><li>Si cela ne fonctionne pas, essayez d’exécuter le « partage en direct : Commande du Lanceur de l’installation ».</li><li>**Les utilisateurs Linux**: Si vous êtes invité à entrer votre mot de passe administrateur (sudo) lors de l’exécution de la commande ci-dessus, veuillez le faire.</li><li>Enfin, consultez [joindre manuellement](reference/manual-join.md) comme solution de contournement.</li></ul> Si vous rencontrez ce problème, nous aimerions voir ce qui peut se produire, donc Veuillez [enregistrer un bogue](https://aka.ms/vsls-new-issue). |
| VS | <strong>Jointure :</strong> Vous étiez <strong>non demandées par invite / en mesure de lancer Visual Studio</strong>  après l’ouverture de la page d’inscription dans un navigateur. |  Consultez la section [Accès manuel](reference/manual-join.md).<br /><br /> Nous aimerions également afficher vos journaux, donc Veuillez [enregistrer un bogue](https://aka.ms/vsls-problem) à l’aide « Rapport un problème... » de Visual Studio fonctionnalité. |
| Tous | <strong>Jointure :</strong> Vous préférez <strong>coller directement le lien de jointure dans Visual Studio / VS Code</strong> au lieu de cliquer sur le lien web. | Consultez la section [Accès manuel](reference/manual-join.md). |
| Tous | <strong>Jointure :</strong> Vous voyez un message indiquant, «**le propriétaire de l’espace de travail semble être hors connexion**, « lors de la jointure via le navigateur. | Solutions de contournement possibles :<br /><ul><li>Essayez [joindre manuellement](reference/manual-join.md). Nous avons noté des problèmes avec plusieurs régions (par exemple, est et ouest des États-Unis) jointures en raison de problèmes de service qui n’affectent pas les jointures manuelles.</li><li>Partage en direct peut être impossible d’acheminer directement à l’hôte lors de l’exécution en mode de connexion « auto ». Essayez [mode relais](reference/connectivity.md).</li></ul>Consultez [la résolution des problèmes de connectivité](#connectivity) pour plus de possibilités |
| VS Code | <strong>Jointure :</strong> Vous avez rejoint via le navigateur <strong>avant de vous connecter</strong>, n’étaient pas invité à vous connecter</strong>et la jointure s’est jamais effectuée. |  Il s’agit d’un [bogue connu](https://github.com/MicrosoftDocs/live-share/issues/167). Cliquez sur le signe dans l’élément de barre d’état pour vous connecter, puis joignez à nouveau. |

## <a name="connectivity"></a>Connectivité

Les informations ci-dessous peuvent vous aider à résoudre les problèmes si vous rencontrez des problèmes de connectivité ou des délais d’attente lors de la connexion, de partage ou de la jointure.

Comme indiqué dans le [exigences de connectivité pour le partage Live](reference/connectivity.md) article, modes de connexion différents ont des exigences différentes pour fonctionner il y a quelques problèmes potentiels différents passe.

| Tool | Problème | Cause probable |
|------|------|----------------|
| Tous | Vous utilisez un <strong>proxy</strong> et constatez un nombre de problèmes de connectivité | Paramètres de proxy peuvent être difficile.  Essayez de définir la **HTTP_PROXY** et **HTTPS_PROXY** variables d’environnement **globalement** et en redémarrant votre outil. Consultez [les paramètres de proxy](reference/connectivity.md#proxies) pour plus d’informations. Il existe probablement certaines configurations que nous ne gérons pas encore, donc [faites-nous savoir](https://github.com/MicrosoftDocs/live-share/issues/86) si cela ne fonctionne pas pour vous. |
| VS Code | Après avoir installé l’extension et de démarrage de Visual Studio Code pour la première fois que vous obtenez un <strong>une erreur lors de la « Fin de l’Installation » s’affiche dans la barre d’état</strong>. |  Vous ne peut pas accéder à internet ou l’accès à download.visualstudio.microsoft.com et/ou download.microsoft.com sur le port 443 est bloqué par votre pare-feu personnel ou d’entreprise. Consultez [ici](https://github.com/MicrosoftDocs/live-share/issues/58) pour plus d’informations sur les raisons Partage Live doit télécharger un contenu à ce stade. |
| Tous | Vous êtes <strong>Impossible de se connecter à un partage en direct de Visual Studio</strong> | Vous ne pouvez pas accéder à internet ou l’accès à *. liveshare.vsengsaas.visualstudio.com sur le port 80/443 est bloqué par votre pare-feu personnel ou d’entreprise. Entrez https://insiders.liveshare.vsengsaas.visualstudio.com dans un navigateur et vérifiez que vous accédez à la page d’accueil de le Partage Live Visual Studio. |
| Tous | Vous êtes dans <strong>mode auto</strong> (la valeur par défaut), sont en mesure de se connecter, mais consultez un <strong>délai d’expiration ou erreur de connexion</strong> lors de partage ou de jointure. | Soit les deux diriger et modes ne parviennent pas à se connecter ou il existe un bogue avec le mode auto de relais. Si vous êtes en mesure de se connecter après [basculement afin de diriger ou en mode relais](reference/connectivity.md#changing-the-connection-mode), veuillez [déclencher un bogue](https://aka.ms/vsls-problem). |
| Tous | Vous êtes dans <strong>mode direct</strong>, sont en mesure de se connecter, mais consultez un <strong>délai d’expiration ou erreur de connexion</strong> lors de partage ou de jointure. | L’invité et hôte ne peut pas se connecter directement. Essayez [mode auto ou relais](reference/connectivity.md#changing-the-connection-mode) pour voir si le problème disparaît. Vous devrez peut-être [autoriser manuellement le partage en direct via votre pare-feu personnel](reference/connectivity.md#manually-adding-a-firewall-entry) ou simplement utiliser le mode de relais. |
| Tous | Vous êtes dans <strong>mode relais</strong>, sont en mesure de se connecter, mais sont informés d’un <strong>délai d’expiration ou erreur de connexion</strong> lors de partage ou de jointure. | L’accès à *. servicebus.windows.net sur le port 80/443 est bloqué est bloqué par votre pare-feu personnel ou d’entreprise. Essayez [mode direct](reference/connectivity.md#changing-the-connection-mode). |

Consultez le [exigences de connectivité pour le partage Live](reference/connectivity.md) article, pour plus d’informations sur les exigences de connectivité.

## <a name="see-also"></a>Voir aussi

Démarrages rapides

- [Partager votre premier projet](quickstart/share.md)
- [Rejoindre votre première session](quickstart/join.md)

Articles Comment faire

- [Collaborer à l’aide de Visual Studio Code](use/vscode.md)
- [Collaborer à l’aide de Visual Studio](use/vs.md)

Référence

- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)
- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Détails d’installation pour Linux](reference/linux.md)
- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Extensions prises en charge](reference/extensions.md)

Encore des problèmes ? Vous pouvez [fournir des commentaires](support.md).
