---
title: Connectivité - partage en direct de Visual Studio | Microsoft Docs
description: Informations sur les modes de connectivité et de connexion pour le partage en direct de Visual Studio.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- liveshare
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 6edc5bcf18dde6f84a4972a1efd755592cbef18c
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57256124"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Exigences de connectivité pour le partage en direct

Cet article résume les exigences de connectivité pour le partage en direct de Visual Studio, options de connectivité disponibles et les solutions de contournement connues le cas échéant.

## <a name="sign-in"></a>Se connecter

Vous pouvez vous connecter dans le partage en direct en utilisant l’une [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) sauvegardée compte professionnel ou scolaire, une [compte Microsoft](https://account.microsoft.com/account), ou un [profil GitHub](https://github.com/). En général, connectez-vous URL pour ceux-ci sont ouverts dans la plupart des organisations, étant donné le nombre de produits accessible sur public qui les utilisent, mais si pas, contactez votre administrateur de réseau sur l’ouverture `login.microsoftonline.com` et/ou `github.com` outre les domaines [ci-dessous](#requirements-for-connection-modes).

> [!NOTE]
> En local les comptes Active Directory (ADFS) et les comptes d’entreprise de GitHub en local ne sont pas actuellement pris en charge [(voter 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modes de connexion

Pour vous assurer optimal des performances, par défaut de partage en direct de Visual Studio détecte automatiquement si un ordinateur hôte de session collaboration et l’ordinateur invité peuvent communiquer directement sur un réseau et relaie uniquement via le cloud s’il en existe aucun itinéraire entre eux. Ce mode mixte « auto » est flexible et permet même de quelques invités à prendre le relais via le cloud tandis que d’autres se connectent directement pour la même session.

Les connexions directes sont authentifiées via un mécanisme basé sur le cloud pour garantir la sécurité, mais nécessite l’ouverture d’un port entre 5990 et 5999 pour activer la connectivité. Par conséquent, lorsque le partage pour la première fois votre pare-feu de bureau peut inviter vous ouvrir un port. Acceptation de que cette étape est facultative, comme elle est ignorée entraîne simplement Partage Live à toujours utiliser le relais en mode auto.

Toutes les connexions dans le partage en direct de Visual Studio sont SSH ou SSL chiffrés et authentifiés par rapport à un service central pour vous assurer que seules dans la session de collaboration peuvent-ils accéder à son contenu. En outre, les relais de cloud du partage de Live ne conserve pas tout le trafic acheminé par son intermédiaire et ne pas « surveillance » le trafic en aucune façon.

## <a name="changing-the-connection-mode"></a>Modification du mode de connexion

Si vous préférez désactiver les connexions directes ou relayées et simplement la résolution des problèmes de connectivité, vous pouvez forcer les autres modes de connexion.

| Mode | Comportement d’hôte | Comportement de l’invité |
|------|----------------|----------------------|
| Auto | Session de collaboration de l’hôte accepte des connexions directes sécurisées et authentifiées ou connexions de cloud relayé. | Tente d’utiliser une connexion directe et revient à relayer des messages via le cloud en cas d’échec. |
| Direct | Session de collaboration de l’hôte accepte uniquement les connexions directes authentifiées et sécurisées. | Tente d’utiliser une connexion directe et s’arrête s’il ne peut pas se connecter. |
| Relay | Session de collaboration de l’hôte n’autorise pas les connexions directes. Aucun port n’est ouvert sur l’ordinateur de l’hôte. | Se connecte toujours via le cloud. |

Pour modifier le mode :

**VISUAL STUDIO :**

1. Accédez à outils > Options > Live partage.
2. Sélectionnez le mode dans la liste déroulante « Mode connexion ».
3. Redémarrez Visual Studio.

**VS Code :**

1. Modifier settings.json (fichier > Préférences > Paramètres).
2. Définissez `"liveshare.connectionMode"` à `"auto"`, `"direct"`, ou `"relay"` selon votre préférence.
3. Redémarrez VS Code.

## <a name="requirements-for-connection-modes"></a>Configuration requise pour les modes de connexion

Vous êtes dans le mode de connexion déterminent les ports spécifiques et les URL qui doivent être disponibles pour le partage en direct de la fonction.

| Mode | Exigence d’accès client | Résolution des problèmes |
|------|--------------|-----------------|
| Any | Accès sortant à `*.liveshare.vsengsaas.visualstudio.com:443` | Assurez-vous que votre entreprise ou pare-feu personnel réseau vous permet de se connecter à ce domaine. Entrez https://insiders.liveshare.vsengsaas.visualstudio.com dans un navigateur et vérifiez que vous accédez à la page d’accueil de le Partage Live Visual Studio. Vous pouvez également être en cours d’exécution dans [problèmes de proxy](#proxies) qui doivent être résolus.|
| N’importe quel (VS Code) | Accès sortant à `download.microsoft.com:443` | Assurez-vous que votre entreprise ou pare-feu personnel réseau vous permet de se connecter à ce domaine. Vous pouvez également être en cours d’exécution dans [problèmes de proxy](#proxies) qui doivent être résolus. |
| Auto | Automatique-commutateurs. Consultez direct et modes de relais. | Commutateur de diriger ou de mode pour résoudre les problèmes de relais. |
| Direct | Hôtes : Un port dans la plage 5990-5999 doit être ouvert pour accepter les connexions de réseau local entrant.<br /><br />Invités : Un itinéraire réseau et un accès sortant à l’hôte sur ce même port. | Vérifiez que « VSL-agent » n’est pas bloqué par votre logiciel de pare-feu de bureau pour cette plage de ports que vous pouvez un test ping sur l’autre. Tandis que Windows et autres logiciels de bureau vous invite lors du premier démarrage de l’agent, nous avons vu des instances où les stratégies de groupe éviter ce problème et vous devrez [ajouter manuellement une entrée](#manually-adding-a-firewall-entry). Vous pouvez également être en cours d’exécution dans [problèmes de proxy](#proxies) qui doivent être résolus. |
| Relay | Accès sortant à `*.servicebus.windows.net:443`. | Assurez-vous que votre entreprise ou pare-feu personnel réseau vous permet de se connecter à ce domaine. Vous pouvez également être en cours d’exécution dans [problèmes de proxy](#proxies) qui doivent être résolus.|

## <a name="manually-adding-a-firewall-entry"></a>Ajout manuel d’une entrée de pare-feu

Comme indiqué ci-dessus, le mode direct requiert que votre pare-feu personnel autorisent **agent VSL** pour accepter les connexions dans le port de plage 5990-5999. Si vous souhaitez utiliser le mode direct, mais a trouvé que votre pare-feu n’a pas d’entrée de l’agent de VSL, vous pouvez l’ajouter manuellement. Procédure à suivre peuvent varier selon le logiciel de pare-feu, mais vous trouverez des informations sur  **[configuration du pare-feu Windows ici](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)**.

Si vous ne voyez pas une entrée pour l’agent VSL, vous trouverez l’agent exécutable dans un des emplacements suivants.

### <a name="vs-code-agent-location"></a>Emplacement de l’agent VS Code

Substitute **VERSION** pour le numéro de version d’extension dans un des chemins d’accès ci-dessous :

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Windows**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Emplacement de l’agent Visual Studio

L’emplacement de Visual Studio est plus dynamique, mais vous pouvez suivre ces étapes pour rechercher le fichier exécutable :

1. Accédez à votre emplacement d’installation de Visual Studio. Il s’agit généralement `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` où **édition** est Community, Enterprise, etc.

2. Exécuter une recherche de `vsls-agent.exe` dans sous la **IDE\Extensions** sous-dossier.

Malheureusement, vous devrez peut-être effectuer cette étape **chaque fois que vous mettez à jour les partage en direct de Visual Studio.**

## <a name="proxies"></a>Serveurs proxy

Partage en direct de Visual Studio a actuellement quelques limitations concernant l’utilisation du proxy. Bien que les paramètres de proxy automatique doivent fonctionner sur Windows, lorsque vous utilisez Mac OS ou Linux (et avec certaines configurations de proxy sur Windows) les **HTTP_PROXY** et **HTTPS_PROXY** doivent des variables d’environnement être définie *globalement*.

Si votre proxy ne définit pas automatiquement ces valeurs pour vous, vous pouvez définir manuellement les variables sous la forme suivante :

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Si vous avez un proxy d’authentification, vous pouvez ajouter votre utilisateur et le mot de passe comme suit :

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Si ces paramètres ne résolvent pas le problème pour vous, [faites-le nous savoir](https://github.com/MicrosoftDocs/live-share/issues/86) les spécificités de votre proxy configurer pour que nous pouvons jeter un coup de œil à améliorer la prise en charge.

## <a name="see-also"></a>Voir aussi

- [Comment : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
- [Comment : Collaborer à l’aide de Visual Studio](../use/vs.md)
- [Fonctionnalités de sécurité de Live Share](security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
