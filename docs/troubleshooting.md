---
title: Résolution des problèmes-Visual Studio Live Share | Microsoft Docs
description: Conseils et astuces de dépannage pour Visual Studio Live Share.
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
ms.openlocfilehash: 5d18c8487bbc280c14c4d4c17e47af02dd89266e
ms.sourcegitcommit: 8579c04aa4c8ec5d32a4987cb2b95708affec318
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/07/2020
ms.locfileid: "77055527"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="troubleshooting-visual-studio-live-share"></a>Résolution des problèmes Visual Studio Live Share

Cet article traite des conseils de dépannage, des solutions de contournement et des réponses aux problèmes courants et aux questions. Vous pouvez également consulter le [Forum aux questions](faq.md). 

## <a name="installation--tool-requirements"></a>Configuration requise pour l’installation/l’outil

Vous trouverez ci-dessous des conseils de dépannage relatifs à l’installation de Visual Studio Live Share.

| Outil | Problème | Résolution/solution de contournement |
|------|---------|------------|
|VS Code <strong>(MacOS)</strong>| Un avertissement s’affiche pour vous indiquer votre <strong>macOS n’est plus pris en charge par .NET Core <strong>| Cet avertissement s’affiche en raison d’une [mise à jour récente effectuée par .net Core](https://docs.microsoft.com/en-us/dotnet/core/install/dependencies?tabs=netcore31&pivots=os-macos) qui ne prend plus en charge les versions antérieures à <strong>High Sierra (10.13 +).</strong> Pour activer l’extension de Live Share, mettez à jour le système d’exploitation.
| VS | Le programme d’installation de l’extension <strong>ne peut pas trouver une version de Visual Studio</strong> à utiliser lors de la tentative d’installation de l’extension de Visual Studio Live share. | Visual Studio Live Share nécessite **Visual Studio 2017 version 15,6** ou ultérieure pour les hôtes et les invités. Installez la dernière [mise à jour stable de Visual Studio 2017](https://visualstudio.com/vs/) , puis réessayez. |
| Visual Studio Code | Une erreur « les**dépendances n’ont pas pu être installées**» s’affiche lorsque l’extension de la **fin** de l’installation est terminée lors du premier démarrage ou lorsque vous recevez des erreurs concernant des **fichiers manquants ou déjà présents**. | Vérifiez que vous disposez d’une **bonne connexion réseau**. Si c’est le cas, vous risquez de rencontrer un problème de **proxy ou de pare-feu** . Consultez [résolution des problèmes de connectivité](#connectivity). <br /><br />|
| Visual Studio Code | L’installation de l’extension de Visual Studio Live Share à partir de la place de marché l' <strong>installe dans la version stable/Insider de vs code</strong> au lieu de la version souhaitée. | Démarrez VS Code stable ou Insider selon vos préférences, cliquez sur l’onglet « Extensions », recherchez « Visual Studio Live Share », puis installez-le à partir de là. |
| VS Code (**Linux**) | L’extension de Live Share n’est pas activée et **aucun élément de barre d’État n’apparaît** après l’installation de l’extension sur **Linux**. | Visual Studio Live Share dépend de .NET Core 2,0, qui présente un certain nombre de conditions préalables Linux qui peuvent ne pas être remplies sur certaines distributions de Linux par défaut. [Pour plus d’informations](reference/linux.md#install-linux-prerequisites) sur ce qui doit être installé, voir ici. |

## <a name="sign-in"></a>Se connecter

Vous trouverez ci-dessous des conseils de résolution des problèmes de connexion.

| Outil | Problème | Résolution/solution de contournement |
|------|---------|------------|
| VS | Vous devez vous connecter à Visual Studio Live Share avec une <strong>identité différente</strong> de celle que vous utilisez pour vous connecter à Visual Studio. | Accédez à outils > Options > Live Share compte d’utilisateur > pour sélectionner un autre compte. |
| Visual Studio Code | Quand une fenêtre de navigateur s’affiche pendant la connexion et que le processus <strong>semble être exécuté sur la page Web</strong>, la barre d’état <strong>indique toujours « se connecter »</strong> après avoir fermé le navigateur. | Après vous être connecté, cliquez sur « vous rencontrez des problèmes ». et suivez les instructions pour entrer un code utilisateur temporaire dans l’outil.<br /><br />Nous aimerions également voir ce qui se passe. Veuillez donc [consigner un bogue](https://aka.ms/vsls-problem). |
| Tous | Vous obtenez un <strong>délai d’attente ou une erreur de connexion</strong>. | Consultez [résolution des problèmes de connectivité](#connectivity). |
| Tous | Lorsque vous vous connectez à l’aide d’une **adresse de messagerie professionnelle ou scolaire** Microsoft, vous voyez un message indiquant **« nécessite une approbation de l’administrateur »** . | Votre Azure AD principe est configuré pour exiger le « consentement de l’administrateur » pour les nouvelles applications qui accèdent au contenu de l’annuaire. Pour plus d’informations, voir [ici](reference/security.md) . |
| VS Code (**MacOS**) | Lorsque vous vous connectez, vous voyez une erreur indiquant que **SecKeychainAddGenericPassword () a échoué**. | Cela est presque toujours dû à un problème courant avec macOS où les modifications de mot de passe ne sont pas reflétées dans le trousseau de connexion. Essayez d’entrer dans « Trousseau d’accès », de verrouiller le trousseau de connexion, puis de le déverrouiller. Cela peut suffire pour résoudre le problème, mais si vous ne parvenez pas à le déverrouiller avec votre mot de passe actuel, essayez le précédent. Si cela fonctionne, remplacez le mot de passe de la chaîne de connexion par votre mot de passe actuel. Cliquez [ici](https://support.apple.com/en-us/HT201609) pour obtenir des détails. |
| VS Code (**Linux**) | Lorsque vous entrez dans le code utilisateur après vous être connecté via le navigateur, vous voyez une erreur indiquant que **secret_password_store_sync () a échoué avec le code d’erreur XX**. | Cela est généralement dû à des `gnome-keyring` et/ou à des `libsecret-1-0`/ `libsecret` pas être installés. Vous pouvez valider gnome-keyring est correctement configuré en installant `seahorse`, puis en utilisant l’application « mots de passe et clés » dans votre environnement de bureau. Pour en savoir plus sur les [conditions préalables pour Linux](reference/linux.md#install-linux-prerequisites), cliquez ici. |
| VS Code (**Linux**) | Vous êtes <strong>invité à entrer un code utilisateur</strong> avec Live share v 0.3.295 ou une version antérieure, mais aucun navigateur ne s’affiche pour vous permettre d’en obtenir un. | Nous travaillons à l’élimination de l’exigence du code utilisateur sur Linux. Dans la durée moyenne, une fenêtre de navigateur doit s’afficher pour vous connecter. Si ce n’est pas le cas, la fenêtre du navigateur peut être masquée sous VS Code. Si ce n’est pas le cas, consultez le Conseil suivant.  |
| Visual Studio Code | Une fois que vous avez cliqué sur « se connecter » (ou à l’aide de la commande « Live Share : Sign in »), <strong>aucune fenêtre de navigateur ne s’affiche pour vous permettre d’entrer vos informations d’identification</strong>. | 1. [Connectez-vous ici](https://insiders.liveshare.vsengsaas.visualstudio.com/auth/login)<br />2. après vous être connecté, cliquez sur « vous rencontrez des problèmes ».<br /> 3. Suivez les instructions pour entrer un code utilisateur temporaire dans l’outil. |
| Tous | Vous souhaitez <strong>rejoindre</strong> une session de collaboration</strong> mais vous ne <strong>souhaitez pas/ne pas recevoir de mises à jour par courrier électronique</strong>. | La connexion à l’extension Live Share dans VS/VS Code ne vous permet <strong>pas</strong> de recevoir des mises à jour par courrier électronique.<br /><br />Live Share oblige les invités à se connecter en tant que mesure de sécurité afin que l’hôte ait une visibilité sur l’identité de ceux qui ont rejoint. [Votez cette fonctionnalité](https://github.com/MicrosoftDocs/live-share/issues/3) si vous souhaitez autoriser les utilisateurs anonymes à se joindre (par exemple, utilisateurs sans nom ou nom défini par l’utilisateur). |

## <a name="share-and-join"></a>Partager et joindre

Vous trouverez ci-dessous des conseils de résolution des problèmes de connexion.

| Outil | Problème | Résolution/solution de contournement |
|------|----------------|------------|
| Tous | <strong>Partage/jointure :</strong> Vous obtenez un délai d’expiration ou une erreur concernant la non-connexion. | Consultez [résolution des problèmes de connectivité](#connectivity). |
| Visual Studio Code | <strong>Joindre :</strong> Vous n’avez <strong>pas été invité à lancer vs code</strong> après avoir ouvert la page de jointure dans un navigateur. |  Conseils : <ul><li>Assurez-vous que vous avez <i>démarré la vs code au moins une fois et ATTENDU que l’installation se termine dans la barre d’État.</i></li><li>Si cela ne fonctionne pas, essayez d’exécuter la commande « Live Share : programme d’installation du lanceur ».</li><li>**Utilisateurs Linux**: Si vous êtes invité à entrer votre mot de passe d’administrateur (sudo) lors de l’exécution de la commande ci-dessus, veuillez le faire.</li><li>Enfin, consultez [jointure manuelle](reference/manual-join.md) comme solution de contournement.</li></ul> Si vous parvenez à résoudre ce problème, nous aimerions voir ce qui se passe. Veuillez donc [consigner un bogue](https://aka.ms/vsls-new-issue). |
| VS | <strong>Joindre :</strong> Vous n’étiez <strong>pas invité à lancer vs</strong> après l’ouverture de la page de jointure dans un navigateur. |  Consultez la section [Accès manuel](reference/manual-join.md).<br /><br /> Nous aimerions également voir vos journaux. Veuillez donc [consigner un bogue](https://aka.ms/vsls-problem) à l’aide de la section « signaler un problème... » de Visual Studio. fonctionnalité. |
| Tous | <strong>Joindre :</strong> Vous préférerez <strong>coller le lien de jointure directement dans Visual Studio/vs code</strong> plutôt que de cliquer sur le lien Web. | Consultez la section [Accès manuel](reference/manual-join.md). |
| Tous | <strong>Joindre :</strong> Vous voyez un message indiquant «**le propriétaire de l’espace de travail semble être hors connexion**» lors de la jointure via le navigateur. | Solutions possibles :<br /><ul><li>Essayez de [joindre manuellement](reference/manual-join.md). Nous avons rencontré des problèmes avec les jointures entre régions (par exemple, est et ouest des États-Unis) en raison de problèmes de service qui n’affectent pas les jointures manuelles.</li><li>Live Share peut ne pas être en mesure d’acheminer directement vers l’hôte lorsqu’il est exécuté en mode de connexion « automatique ». Essayez le [mode relais](reference/connectivity.md).</li></ul>Consultez la [résolution des problèmes de connectivité](#connectivity) pour plus de possibilités |
| Visual Studio Code | <strong>Joindre :</strong> Vous vous êtes connecté par le biais du navigateur <strong>avant de vous connecter</strong>, vous n’êtes pas invité à vous connecter</strong>et la jointure n’est jamais terminée. |  Il s’agit d’un [bogue connu](https://github.com/MicrosoftDocs/live-share/issues/167). Cliquez sur l’élément de la barre d’État connexion pour vous connecter, puis rejoignez. |

## <a name="connectivity"></a>Connectivité

Les informations ci-dessous peuvent vous aider à résoudre les problèmes liés à la connectivité ou aux délais d’attente lors de la connexion, du partage ou de la jonction.

Comme indiqué dans l’article [Configuration requise pour la connectivité pour Live share](reference/connectivity.md) , les différents modes de connexion ont des exigences différentes pour fonctionner, de sorte que quelques problèmes potentiels différents se posent.

| Outil | Problème | Cause probable |
|------|------|----------------|
| Tous | Vous utilisez un <strong>proxy</strong> et voyez un certain nombre de problèmes de connectivité | Les paramètres de proxy peuvent être délicats.  Essayez de définir les variables d’environnement **http_proxy** et **HTTPS_PROXY** de manière **globale** , puis redémarrez votre outil. Pour plus d’informations, consultez [paramètres de proxy](reference/connectivity.md#proxies) . Il existe probablement des configurations que nous ne prenons pas encore en charge. nous [allons donc savoir](https://github.com/MicrosoftDocs/live-share/issues/86) si cela ne fonctionne pas pour vous. |
| Visual Studio Code | Après l’installation de l’extension et le démarrage de VS Code pour la première fois, vous recevez une <strong>erreur lorsque la « finalisation de l’installation » s’affiche dans la barre d’État</strong>. |  Vous ne pouvez pas accéder à Internet ou l’accès à download.visualstudio.microsoft.com et/ou download.microsoft.com sur le port 443 est bloqué par votre pare-feu personnel ou d’entreprise. Pour [plus d’informations](https://github.com/MicrosoftDocs/live-share/issues/58) sur la raison pour laquelle Live share doit télécharger un fichier à ce stade. |
| Tous | Vous ne <strong>parvenez pas à vous connecter à Visual Studio Live share</strong> | Vous ne pouvez pas accéder à Internet ou l’accès à *. liveshare.vsengsaas.visualstudio.com sur le port 80/443 est bloqué par votre pare-feu personnel ou d’entreprise. Entrez https://insiders.liveshare.vsengsaas.visualstudio.com dans un navigateur et vérifiez que vous êtes sur la page d’hébergement Visual Studio Live Share. |
| Tous | Vous êtes en <strong>mode auto</strong> (valeur par défaut), vous pouvez vous connecter, mais vous pouvez voir un <strong>délai d’attente ou une erreur de connexion lors du</strong> partage ou de la jonction. | Les modes directe et relais ne parviennent pas à se connecter ou il existe un bogue avec le mode auto. Si vous êtes en mesure de vous connecter après avoir [basculé en mode direct ou relais](reference/connectivity.md#changing-the-connection-mode), [levez un bogue](https://aka.ms/vsls-problem). |
| Tous | Vous êtes en <strong>mode direct</strong>, êtes en mesure de vous connecter, mais vous pouvez voir un <strong>délai d’attente ou une erreur de connexion lors du</strong> partage ou de la jointure. | L’invité et l’hôte ne peuvent pas se connecter directement. Essayez le [mode automatique ou relais](reference/connectivity.md#changing-the-connection-mode) pour voir si le problème disparaît. Vous devrez peut-être [autoriser manuellement Live Share par le biais de votre pare-feu personnel](reference/connectivity.md#manually-adding-a-firewall-entry) ou simplement utiliser le mode relais. |
| Tous | Vous êtes en <strong>mode relais</strong>, vous êtes en mesure de vous connecter, mais vous êtes averti d’un <strong>délai d’attente ou</strong> d’une erreur de connexion lors du partage ou de la jointure. | L’accès à *. servicebus.windows.net sur le port 80/443 est bloqué par votre pare-feu personnel ou d’entreprise. Essayez le [mode direct](reference/connectivity.md#changing-the-connection-mode). |

Pour plus d’informations sur les conditions requises en matière de connectivité, consultez la page [Configuration requise pour Live share](reference/connectivity.md) article.

## <a name="see-also"></a>Voir aussi

Démarrages rapides

- [Partager votre premier projet](quickstart/share.md)
- [Rejoindre votre première session](quickstart/join.md)

Procédures

- [Collaborer à l’aide de Visual Studio Code](use/vscode.md)
- [Collaborer à l’aide de Visual Studio](use/vs.md)

Informations de référence

- [Tous les bogues majeurs, toutes les demandes de fonctionnalités et toutes les limitations](https://aka.ms/vsls-issues)
- [Toutes les demandes de fonctionnalités et limitations](https://aka.ms/vsls-feature-requests)
- [Exigences de connectivité pour Live Share](reference/connectivity.md)
- [Détails d’installation pour Linux](reference/linux.md)
- [Prise en charge de langues et de plateformes](reference/platform-support.md)
- [Extensions prises en charge](reference/extensions.md)

Vous rencontrez toujours des problèmes ? Vous pouvez [fournir des commentaires](support.md).
