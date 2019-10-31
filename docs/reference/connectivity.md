---
title: Connectivité-Visual Studio Live Share | Microsoft Docs
description: Informations sur la connectivité et les modes de connexion pour Visual Studio Live Share.
ms.custom: ''
ms.date: 03/22/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: c1d537ac80daddcf83d18942c8d837f3c0ce370b
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73169993"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="connectivity-requirements-for-live-share"></a>Exigences de connectivité pour Live Share

Cet article résume les conditions requises en matière de connectivité pour Visual Studio Live Share, les options de connectivité disponibles et les solutions de contournement connues, le cas échéant.

## <a name="sign-in"></a>Se connecter

Vous pouvez vous connecter à Live Share à l’aide d’un compte professionnel ou scolaire sauvegardé [Azure Active Directory](https://azure.microsoft.com/en-us/services/active-directory) , d’un [compte Microsoft](https://account.microsoft.com/account)ou d’un [Profil GitHub](https://github.com/). En général, les URL de connexion sont ouvertes dans la plupart des organisations en fonction du nombre de produits publics qui les utilisent, mais dans le cas contraire, contactez votre administrateur réseau pour qu’il ouvre `login.microsoftonline.com` et/ou `github.com` en plus des domaines [répertoriés ci-dessous](#requirements-for-connection-modes).

> [!NOTE]
> Les comptes AD local (ADFS) et les comptes local GitHub Enterprise ne sont pas pris en charge actuellement [(vote de 👍)](https://github.com/MicrosoftDocs/live-share/issues/341).

## <a name="connection-modes"></a>Modes de connexion

Pour garantir des performances optimales, par défaut Visual Studio Live Share détecte automatiquement si un ordinateur hôte de session de collaboration et un ordinateur invité peuvent communiquer directement sur un réseau et uniquement des relais via le Cloud s’il n’y a pas d’itinéraire entre eux. Ce mode mixte « auto » est flexible et permet même à certains invités de relayer le Cloud pendant que d’autres se connectent directement à la même session.

Les connexions directes sont authentifiées via un mécanisme basé sur le Cloud pour garantir la sécurité, mais nécessitent l’ouverture d’un port entre 5990 et 5999 pour permettre la connectivité. Par conséquent, lors du partage pour la première fois, votre pare-feu de bureau peut vous inviter à ouvrir un port. L’acceptation de cette option est facultative car son ignorance entraînera simplement l’utilisation du relais par Live Share quand il est en mode auto.

Toutes les connexions dans Visual Studio Live Share sont chiffrées SSH ou SSL et authentifiées par rapport à un service central pour s’assurer que seuls les utilisateurs de la session de collaboration peuvent accéder à son contenu. En outre, le relais Cloud de Live Share ne rend pas persistant le trafic acheminé via ce dernier et ne « Snoope » pas le trafic de quelque manière que ce soit.

## <a name="changing-the-connection-mode"></a>Modification du mode de connexion

Si vous préférez désactiver les connexions directes ou relayées ou simplement résoudre les problèmes de connectivité, vous pouvez forcer d’autres modes de connexion.

| Mode | Comportement de l’hôte | Comportement de l’invité |
|------|----------------|----------------------|
| Auto | La session de collaboration de l’hôte accepte des connexions directes authentifiées et sécurisées ou des connexions relayées par le Cloud. | Tente d’utiliser une connexion directe et revient au relais dans le Cloud en cas d’échec. |
| Direct | La session de collaboration de l’hôte accepte uniquement les connexions directes authentifiées et sécurisées. | Tente d’utiliser une connexion directe et s’arrête si elle ne peut pas se connecter. |
| Relay | La session de collaboration de l’hôte n’autorise pas les connexions directes. Aucun port n’est ouvert sur l’ordinateur hôte. | Se connecte toujours via le Cloud. |

Pour modifier le mode :

**COMPARATIF**

1. Accédez à outils > Options > Live Share.
2. Sélectionnez le mode dans la liste déroulante « mode de connexion ».
3. Redémarrage et

**VS Code:**

1. Modifiez Settings. JSON (fichier > Préférences > paramètres).
2. Définissez `"liveshare.connectionMode"` sur `"auto"`, `"direct"`ou `"relay"` selon vos préférences.
3. Redémarrez VS Code.

## <a name="requirements-for-connection-modes"></a>Conditions requises pour les modes de connexion

Le mode de connexion que vous utilisez permet de dicter les ports et les URL spécifiques qui doivent être disponibles pour que Live Share fonctionne.

| Mode | Spécification de l’accès client | Résolution des problèmes |
|------|--------------|-----------------|
| Any | Accès sortant à `*.liveshare.vsengsaas.visualstudio.com:443` | Vérifiez que votre pare-feu de réseau personnel ou d’entreprise vous permet de vous connecter à ce domaine. Entrez https://insiders.liveshare.vsengsaas.visualstudio.com dans un navigateur et vérifiez que vous êtes sur la page d’hébergement Visual Studio Live Share. Vous pouvez également rencontrer des [problèmes de proxy](#proxies) qui doivent être résolus.|
| Any (VS Code) | Accès sortant à `download.microsoft.com:443` | Vérifiez que votre pare-feu de réseau personnel ou d’entreprise vous permet de vous connecter à ce domaine. Vous pouvez également rencontrer des [problèmes de proxy](#proxies) qui doivent être résolus. |
| Auto | Basculements automatiques. Consultez modes directs et relais. | Basculez en mode direct ou relais pour résoudre les problèmes. |
| Direct | Hôtes : un port de la plage 5990-5999 doit être ouvert pour accepter les connexions au réseau local entrant.<br /><br />Invités : un itinéraire réseau et un accès sortant à l’hôte sur ce même port. | Vérifiez que « vsls-agent » n’est pas bloqué par votre logiciel de pare-feu de bureau pour cette plage de ports et que vous pouvez effectuer un test ping. Alors que Windows et d’autres logiciels de bureau doivent vous inviter lors du premier démarrage de l’agent, nous avons vu des instances où les stratégies de groupe empêchent ce problème et vous devrez [Ajouter l’entrée manuellement](#manually-adding-a-firewall-entry). Vous pouvez également rencontrer des [problèmes de proxy](#proxies) qui doivent être résolus. |
| Relay | Accès sortant aux `*.servicebus.windows.net:443`. | Vérifiez que votre pare-feu de réseau personnel ou d’entreprise vous permet de vous connecter à ce domaine. Vous pouvez également rencontrer des [problèmes de proxy](#proxies) qui doivent être résolus.|

## <a name="manually-adding-a-firewall-entry"></a>Ajout manuel d’une entrée de pare-feu

Comme indiqué ci-dessus, le mode direct nécessite que votre pare-feu personnel autorise **vsls-agent** à accepter des connexions dans la plage de ports 5990-5999. Si vous souhaitez utiliser le mode direct mais que votre pare-feu n’a pas d’entrée vsls-agent, vous pouvez l’ajouter manuellement. La façon dont vous procédez varie en fonction du logiciel de pare-feu, mais vous pouvez trouver des informations sur **[la configuration du pare-feu Windows ici](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-firewall/create-an-inbound-program-or-service-rule)** .

Si vous ne voyez pas d’entrée pour vsls-agent, vous pouvez trouver l’exécutable de l’agent dans l’un des emplacements suivants.

### <a name="vs-code-agent-location"></a>Emplacement de l’agent de VS Code

Remplacez la **version** du numéro de version de l’extension par l’un des chemins d’accès ci-dessous :

- **macOS, Linux**

    `$HOME/.vscode/extensions/ms-vsliveshare.vsliveshare-VERSION/dotnet_modules/vsls-agent`

- **Fenêtres**

    `%USERPROFILE%\.vscode\extensions\ms-vsliveshare.vsliveshare-VERSION\dotnet_modules\vsls-agent.exe`

### <a name="visual-studio-agent-location"></a>Emplacement de l’agent Visual Studio

L’emplacement de Visual Studio est plus dynamique, mais vous pouvez suivre ces étapes pour Rechercher l’exécutable :

1. Accédez à l’emplacement d’installation de Visual Studio. C’est généralement le cas `C:\Program Files (x86)\Microsoft Visual Studio\EDITION` où l' **édition** est Community, Enterprise, etc.

2. Exécutez une recherche pour `vsls-agent.exe` dans sous le sous-dossier **IDE\Extensions** .

Malheureusement, vous devrez peut-être effectuer cette étape **chaque fois que vous mettez à jour Visual Studio Live share.**

## <a name="proxies"></a>Serveurs proxy

Visual Studio Live Share présente actuellement des restrictions concernant l’utilisation du proxy. Alors que les paramètres de proxy automatique doivent fonctionner sous Windows, lorsque vous utilisez macOS ou Linux (et avec certaines configurations de proxy sur Windows), les variables d’environnement **http_proxy** et **HTTPS_PROXY** doivent être définies *globalement*.

Si votre proxy ne les définit pas automatiquement pour vous, vous pouvez définir manuellement les variables sous la forme suivante :

`HTTPS_PROXY=http://proxy-ip-address:proxyport`

Si vous disposez d’un proxy d’authentification, vous pouvez ajouter votre utilisateur et votre mot de passe comme suit :

`HTTPS_PROXY=http://user:password@proxy-ip-address:proxyport`

Si ces paramètres ne résolvent pas le problème pour vous, [Indiquez-nous](https://github.com/MicrosoftDocs/live-share/issues/86) les spécificités de votre configuration de proxy afin que nous puissions examiner l’amélioration du support.

## <a name="see-also"></a>Voir aussi

- [Comment : collaborer à l’aide de Visual Studio Code](../how-to-guides/vscode.md)
- [Comment : collaborer à l’aide de Visual Studio](../how-to-guides/vs.md)
- [Fonctionnalités de sécurité de Live Share](security.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
