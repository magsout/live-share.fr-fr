---
title: Sécurité-Visual Studio Live Share | Microsoft Docs
description: Informations sur les fonctionnalités de sécurité de Visual Studio Live Share.
ms.custom: ''
ms.date: 12/17/2018
ms.reviewer: ''
ms.suite: ''
ms.topic: reference
author: chuxel
ms.author: clantz
manager: AmandaSilver
ms.workload:
- liveshare
ms.openlocfilehash: 2f3a2adf0be13071f22a8ea7e33800af6f9099b5
ms.sourcegitcommit: c6ef4e5a9aec4f682718819c58efeab599e2781b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73170101"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Fonctionnalités de sécurité de Live Share

Les sessions de collaboration dans Visual Studio Live Share sont puissantes en ce qu’elles permettent à un nombre quelconque de personnes de rejoindre une session et de modifier, déboguer et bien plus encore. Toutefois, étant donné ce niveau d’accès, vous serez sans aucun doute intéressé par les fonctionnalités de sécurité que Live Share fournit. Dans cet article, nous allons fournir des recommandations et des options pour sécuriser votre environnement en fonction des besoins.

**Comme pour n’importe quel outil de collaboration, n’oubliez pas que vous ne devez partager votre code, votre contenu et vos applications qu’avec des personnes dignes de confiance.**

## <a name="connectivity"></a>Connectivité

Toutes les connexions dans Visual Studio Live Share sont chiffrées SSH ou SSL et authentifiées par rapport à un service central pour s’assurer que seuls les utilisateurs de la session de collaboration peuvent accéder à son contenu. Par défaut, Live Share tente une connexion directe et revient sur Cloud Relay si une connexion entre l’invité et l’ordinateur hôte ne peut pas être établie. Notez que le relais Cloud de Live Share ne rend pas persistant le trafic routé via ce dernier et ne « Snoope » pas le trafic de quelque manière que ce soit. Toutefois, si vous préférez ne pas utiliser le relais, vous pouvez modifier les paramètres pour toujours vous connecter directement.

Pour en savoir plus sur la modification de ces comportements et des exigences de connectivité de Live Share, consultez la page **[Configuration requise pour la connectivité pour Live share](connectivity.md)** .

## <a name="invitations-and-join-access"></a>Invitations et accès à la jointure

Chaque fois que vous démarrez une nouvelle session de collaboration, Live Share génère un **nouvel identificateur unique** qui est placé dans le lien d’invitation. Ces liens fournissent une fondation solide et sécurisée pour inviter les personnes auxquelles vous faites confiance, car l’identificateur dans le lien est « non devinable » et n’est _valide que pour la durée d’une seule session de collaboration_.

### <a name="removing-an-unexpected-guest"></a>Suppression d’un invité inattendu

En tant qu’hôte, vous êtes automatiquement averti chaque fois qu’un invité rejoint la session de collaboration.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-notification.png" width="100%" alt="Visual Studio Code join notification" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-notification.png" width="100%" alt="Visual Studio join notification"/>
    </td>
</tr>
</table>

Mieux encore, la notification vous donne la possibilité de supprimer un invité qui a rejoint si, pour une raison quelconque, vous ne le connaissez pas. (Par exemple, si vous avez accidentellement publié votre lien sur un système de conversation à l’entreprise et qu’un employé aléatoire est joint.) Cliquez simplement sur le bouton « supprimer » dans la notification qui s’affiche et qui seront éjectés de la session de collaboration.

Dans **vs code**, même si vous avez ignoré une notification de jointure, vous avez également la possibilité de supprimer un participant. En ouvrant la vue de Live Share dans l’Explorateur ou l’onglet personnalisé dans la barre d’activité VS Code, vous pouvez pointer sur le nom d’un participant ou cliquer dessus avec le bouton droit et sélectionner l’icône ou l’option « supprimer un participant ».

![Supprimer un participant dans VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Exiger l’approbation de l’invité

En règle générale, les participants qui adhèrent à une session de collaboration sont **connectés à Live share** à l’aide d’un compte Microsoft professionnel ou scolaire (AAD), d’un compte Microsoft personnel ou d’un compte github. Alors que la valeur par défaut « notification + suppression » pour les utilisateurs connectés offre une bonne combinaison de vitesse et de contrôle pour ces invités, vous souhaiterez peut-être les réduire un peu plus si vous effectuez des **opérations** sensibles.

En outre, dans certaines circonstances, forcer tous les invités à se connecter pour rejoindre une session de collaboration peut être problématique. Voici quelques exemples : demander à une personne de Live Share de participer en tant que visiteur, scénarios de classe/d’apprentissage ou de collaborer avec une personne qui ne dispose pas de l’un des types de compte pris en charge. Pour ces raisons, Live Share pouvez autoriser les utilisateurs qui **ne sont pas connectés** à joindre des sessions de collaboration en tant qu’invités **en lecture seule** . Alors que l’hôte doit **approuver** ces invités avant de pouvoir se joindre par défaut, vous souhaiterez peut-être interdire ces invités « anonymes » ou toujours les approuver à la place.

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Exiger l’approbation de l’invité pour les utilisateurs connectés

Si vous souhaitez empêcher les invités connectés de rejoindre vos sessions de collaboration jusqu’à ce que vous les ayez « approuvés », modifiez le paramètre suivant :

* Dans **vs code**, ajoutez ce qui suit à Settings. JSON (paramètres de > de fichiers > paramètres) :

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* Dans **Visual Studio**, définissez outils > Options > Live share > « exiger l’approbation de l’invité » sur true.

    ![Fenêtre paramètres Visual Studio avec le paramètre approbation d’invité mis en surbrillance](../media/vs-setting-guestapproval.png)

À partir de ce point, vous serez invité à approuver chaque invité joint.

<table style="border: none;">
<tr style="border: none;">
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vscode-join-approval.png" width="100%" alt="Visual Studio Code join approval request" />
    </td>
    <td width="50%" style="vertical-align: top; border: none;">
        <img src="../media/vs-join-approval.png" width="100%" alt="Visual Studio join approval request"/>
    </td>
</tr>
</table>

En tant qu’invité, si vous rejoignez une session où ce paramètre est activé pour l’ordinateur hôte, vous êtes averti dans la barre d’État ou la boîte de dialogue de jointure que Live Share attend que l’hôte approuve.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Rejet automatique ou acceptation d’utilisateurs qui ne sont pas connectés (anonymes)

Comme décrit ci-dessus, Live Share peut être configuré pour autoriser **les utilisateurs qui ne sont pas connectés** à rejoindre une session de collaboration en tant qu’invités **en lecture seule** .  Bien que ces **invités « anonymes » doivent entrer un nom** lors de la jointure, un simple nom ne fournit pas le même niveau de garantie qu’une connexion réelle. Par conséquent, par **défaut, l’hôte est invité à approuver** tout invité anonyme, quel que soit le paramètre « exiger l’approbation de l’invité » décrit ci-dessus.

Vous pouvez **toujours refuser** (désactiver les invités anonymes) ou **toujours accepter** les utilisateurs anonymes comme suit :

* Dans **vs code**, définissez `liveshare.anonymousGuestApproval` dans Settings. JSON (préférences de > de fichier > paramètres) sur `accept`, `reject`ou `prompt` (valeur par défaut), le cas échéant.

* Dans **Visual Studio**, définissez outils > Options > Live share > « approbation d’invité anonyme » sur accepter, rejeter ou demander (valeur par défaut), le cas échéant.

 **N’oubliez pas que vous ne devez envoyer Live Share des liens d’invitation à des personnes de confiance.**

## <a name="controlling-file-access-and-visibility"></a>Contrôle de l’accès aux fichiers et visibilité

En tant qu’invité, le modèle distant de Live Share vous donne un accès en lecture/écriture rapide aux fichiers et dossiers que l’hôte a partagés avec vous sans avoir à synchroniser l’intégralité du contenu d’un projet. Par conséquent, vous pouvez parcourir et modifier les fichiers indépendamment dans l’intégralité de l’arborescence des fichiers partagés. **Toutefois, cette liberté présente des risques pour l’hôte.** D’un point de vue conceptuel, un développeur peut choisir d’accéder au code source et de le modifier sans que vous en soyez informé ou d’afficher le code source sensible ou les secrets situés quelque part dans l’arborescence des fichiers partagés. Par conséquent, en tant qu’hôte, vous ne voudrez peut-être pas toujours que l’invité ait accès à l’intégralité d’un projet que vous partagez. Heureusement, un avantage supplémentaire de ce modèle distant est que vous pouvez choisir d’exclure des fichiers que vous ne souhaitez pas partager avec quiconque sans sacrifier les fonctionnalités. Vos invités peuvent toujours participer à des opérations telles que le débogage de sessions qui nécessiteraient normalement l’accès à ces fichiers s’ils le souhaitent.

Pour ce faire, vous pouvez ajouter un fichier **. vsls. JSON** au dossier ou au projet que vous partagez. Les paramètres que vous ajoutez à ce fichier au format JSON modifient la façon dont Live Share traite les fichiers. En plus de vous fournir un contrôle direct, ces fichiers peuvent également être validés dans le contrôle de code source afin que toute personne qui clone un projet puisse tirer parti de ces règles sans aucun effort supplémentaire de leur part.

Voici un exemple de fichier. vsls. JSON :

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"none",
    "excludeFiles":[
        "*.p12",
        "*.cer",
        "token",
        ".gitignore"
    ],
    "hideFiles": [
        "bin",
        "obj"
    ]
}
```

> [!NOTE]
> Vous pouvez également faire en sorte que tous les fichiers/dossiers que vous partagez soient **en lecture seule** lorsque vous démarrez une session de collaboration. Pour plus d’informations, voir [ci-dessous](#read-only-mode) .

Passons en revue la façon dont ces propriétés changent ce que les invités peuvent faire.

### <a name="properties"></a>Propriétés

La propriété **excludeFiles** vous permet de spécifier une liste de modèles de fichier glob (à l’instar des fichiers. gitignore trouvés) qui empêche Live share d’ouvrir certains fichiers ou dossiers pour les invités. Sachez qu’il s’agit de scénarios inclusifs, tels qu’un invité _suivant ou le passage à votre emplacement de modification, l’exécution pas à pas d’un fichier lors du débogage collaboratif, de toutes les fonctionnalités de navigation du code telles que atteindre la définition, et bien plus encore._ Elle est destinée aux fichiers que vous ne souhaitez jamais partager dans toutes les circonstances telles que celles contenant des secrets, des certificats ou des mots de passe. Par exemple, étant donné qu’ils contrôlent la sécurité, les fichiers. vsls. JSON sont toujours exclus.

La propriété **hideFiles** est similaire, mais elle n’est pas aussi stricte. Ces fichiers sont simplement masqués dans l’arborescence des fichiers. Par exemple, si vous parvenez à effectuer un pas à pas détaillé dans l’un de ces fichiers pendant le débogage, il est toujours ouvert dans l’éditeur. Cette propriété est surtout utile si vous n’avez pas de configuration de fichier. gitignore (comme c’est le cas si vous utilisez un système de contrôle de code source différent) ou si vous souhaitez simplement augmenter ce qui est déjà nécessaire pour éviter tout encombrement ou toute confusion.

Le paramètre **gitignore** établit la manière dont Live share doit traiter le contenu des fichiers. gitignore dans des dossiers partagés. Par défaut, tout modèles glob trouvé dans les fichiers. gitignore est traité comme s’il avait été spécifié dans la propriété « hideFiles ». Toutefois, vous pouvez choisir un comportement différent en utilisant l’une des valeurs suivantes :

| Option    | Résultat                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | le contenu de. gitignore est visible pour les invités dans l’arborescence de fichiers (en supposant qu’ils ne sont pas filtrés par un paramètre d’éditeur invité). |
| `hide`    | **Valeur par défaut.** Les modèles glob dans. gitignore sont traités comme s’ils étaient dans la propriété « hideFiles ».                   |
| `exclude` | Les modèles glob dans. gitignore sont traités comme s’ils étaient dans la propriété « excludeFiles ».                                 |

L’inconvénient du paramètre `exclude` est que le contenu de dossiers comme node_modules est souvent dans. gitignore, mais il peut être utile pour effectuer un pas à pas détaillé durant le débogage. Par conséquent, Live Share prend en charge la possibilité d’inverser une règle à l’aide de «  ! » dans la propriété excludeFiles. Par exemple, ce fichier. vsls. JSON exclut tous les éléments de « . gitignore » à l’exception de node_modules :

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Les règles de masquage et d’exclusion sont traitées séparément. par conséquent, si vous souhaitez toujours masquer node_modules pour réduire l’encombrement sans réellement l’exclure, vous pouvez simplement modifier le fichier comme suit :

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ],
    "hideFiles":[
        "node_modules"
    ]
}
```

### <a name="vslsjson-files-in-sub-folders"></a>fichiers. vsls. JSON dans les sous-dossiers

Enfin, tout comme. gitignore, les fichiers. vsls. JSON peuvent être placés dans des sous-dossiers. Les règles de masquage/exclusion sont déterminées en commençant par le fichier. vsls. JSON dans le dossier racine que vous avez partagé (le cas échéant), puis en parcourant à chaque sous-dossier à partir d’un fichier donné pour rechercher les fichiers. vsls. JSON à traiter. Le contenu des fichiers. vsls. JSON dans des dossiers plus éloignés de l’arborescence de fichiers, puis complète (ou remplace) les règles établies à des niveaux supérieurs.

### <a name="disabling-external-file-sharing"></a>Désactivation du partage de fichiers externe

Par défaut, Live Share partagera également tous les fichiers que l’hôte ouvre et qui sont externes au dossier/à la solution partagés. Cela facilite l’ouverture rapide d’autres fichiers associés sans devoir partager à nouveau.

Si vous préférez désactiver cette fonctionnalité :

* Dans **vs code**, ajoutez ce qui suit à Settings. JSON :

    ```json
    "liveshare.shareExternalFiles": false
    ```

* Dans **Visual Studio**, définissez outils &gt; Options &gt; Live share &gt; « partager des fichiers externes » sur false.

## <a name="read-only-mode"></a>Mode lecture seule

Parfois, lorsque vous partagez votre code en tant qu’ordinateur hôte, vous ne souhaitez pas que vos invités apportent des modifications. Vous aurez peut-être besoin de votre invité pour jeter un coup d’œil à une partie de votre code, ou vous affichez votre projet sur un grand nombre d’invités et ne souhaitez pas effectuer de modifications accidentelles ou accidentelles. Live Share offre la possibilité de partager des projets en mode lecture seule.

En tant qu’hôte, lors du partage, vous avez la possibilité d’activer le mode lecture seule pour une session de collaboration. Lorsqu’un invité se joint, il ne peut pas apporter de modifications au code, même si vous pouvez toujours voir les curseurs et les mises en surbrillance d’autres, ainsi que parcourir le projet.

Vous pouvez toujours déboguer avec des invités en mode lecture seule. Les invités n’ont pas la possibilité d’effectuer un pas à pas détaillé dans le processus de débogage, mais ils peuvent toujours ajouter ou supprimer des points d’arrêt et inspecter les variables. En outre, vous pouvez toujours partager des serveurs et des terminaux (en lecture seule) avec des invités.

Vous pouvez en savoir plus sur le démarrage d’une session de collaboration en lecture seule : [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-project) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-project)

## <a name="co-debugging"></a>Codébogage

Lorsque vous rencontrez des problèmes de codage difficile ou des bogues, il peut être très utile d’avoir une paire d’yeux pour le débogage. Visual Studio Live share active le « débogage collaboratif » ou le « débogage » en partageant la session de débogage avec tous les invités chaque fois que l’hôte démarre le débogage.

En tant qu’ordinateur hôte, vous avez un contrôle total sur le démarrage ou l’arrêt d’une session de débogage, mais le débogage pose des risques si vous partagez avec une personne à laquelle vous n’êtes pas sûr. Live Share permet aux invités que vous invitez d’exécuter des commandes de console/REPL. il y a donc **un risque qu’un acteur malveillant exécute une commande que vous ne voulez pas qu’il exécute**.

Par conséquent, vous **ne devez co-déboguer que les personnes avec lesquelles vous faites confiance.**

En savoir plus : [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#co-debugging) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Partage d’un serveur local

Lors du codébogage, il peut être très utile de pouvoir accéder aux différentes parties de l’application prise en charge par l’hôte pendant la session de débogage. Vous pouvez accéder à l’application dans un navigateur, accéder à une base de données locale ou atteindre un point de terminaison REST à partir de vos outils. Live Share vous permet de « partager un serveur » qui mappe un port local sur l’ordinateur de l’ordinateur hôte vers le même port sur l’ordinateur de l’invité. En tant qu’invité, vous pouvez interagir avec l’application exactement comme si elle était exécutée localement sur votre ordinateur (par exemple, l’hôte et l’invité peuvent tous deux accéder à une application Web s’exécutant sur http://localhost:3000).

Toutefois, en tant qu’hôte, vous devez **être très sélectif avec les ports que vous partagez avec les** invités et partager des ports d’application plutôt que des ports système. Du côté des invités, les ports partagés se comportent exactement comme si le serveur/service était en cours d’exécution sur leur propre ordinateur. Cette fonction est très utile, mais il faut éviter tout risque de partager le mauvais port. C’est la raison pour laquelle Live Share n’effectue aucune supposition quant à ce qui doit ou ne doit pas être partagé sans paramètre de configuration et l’hôte effectuant une action.

Dans Visual Studio, le **port d’application Web** spécifié dans les projets ASP.net est **automatiquement partagé pendant le débogage uniquement** pour faciliter l’accès invité à l’application Web lors de l’exécution. Toutefois, vous pouvez désactiver cette automatisation en définissant outils > Options > Live Share > « partager l’application Web lors du débogage » en « false », si vous préférez.

Dans Visual Studio Code, Live Share tente de **détecter les ports d’application appropriés** et de les partager. Toutefois, vous pouvez désactiver ce paramètre en ajoutant le code suivant à Settings. JSON :

        liveshare.autoShareServers: false

Dans les deux cas, soyez prudent lorsque vous partagez des ports supplémentaires.

Vous pouvez en savoir plus sur la configuration de la fonctionnalité ici : [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-server) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Partage d’un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Live Share vous permet de « partager un terminal » avec vos invités en tant qu’hôte. Le terminal partagé peut fonctionner en lecture seule ou en collaboration totale, auquel cas tant l’hôte que les invités ont la possibilité d’exécuter des commandes et de voir les résultats. En tant qu’hôte, vous pouvez autoriser d’autres collaborateurs à voir simplement la sortie ou à utiliser un nombre quelconque d’outils en ligne de commande pour exécuter des tests, générer ou même trier des problèmes spécifiques à l’environnement.

Seuls les hôtes peuvent démarrer des terminaux partagés pour empêcher les invités de démarrer un et d’effectuer une tâche que vous n’attendez pas ou que vous ne souhaitez pas regarder. Lorsque vous démarrez un terminal partagé en tant qu’ordinateur hôte, vous pouvez spécifier s’il doit être en lecture seule ou en lecture/écriture. Dans le deuxième cas, tout le monde, y compris l’hôte, peut taper dans le terminal, ce qui permet d’intervenir si un invité effectue une action indésirable. Dans un souci de sécurité toutefois, **ne donnez un accès en lecture/écriture qu’aux invités qui en ont réellement besoin** et tenez-vous-en aux terminaux en lecture seule si vous souhaitez simplement qu’ils voient le résultat des commandes exécutées.

Dans Visual Studio, les terminaux ne sont pas partagés par défaut. Dans VS Code, les terminaux sont automatiquement partagés par défaut en **lecture seule** . Toutefois, vous pouvez désactiver ce paramètre en ajoutant le code suivant à Settings. JSON :

```json
"liveshare.autoShareTerminals": false
```

En savoir plus : [![VS Code](../media/vscode-icon-15x15.png)](../how-to-guides/vscode.md#share-a-terminal) [![et](../media/vs-icon-15x15.png)](../how-to-guides/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Consentement de l’administrateur AAD

Lorsque vous vous connectez à l’aide d’une **adresse de messagerie professionnelle ou scolaire** Microsoft, vous pouvez voir un message indiquant **« nécessite l’approbation de l’administrateur »** lors de la connexion. Cela est dû au fait que Live Share nécessite un accès en lecture aux informations utilisateur pour ses fonctionnalités de sécurité et que votre locataire Azure AD est configuré pour exiger le « consentement de l’administrateur » pour les nouvelles applications qui accèdent au contenu de l’annuaire.

Votre administrateur AD doit résoudre ce cas pour vous en utilisant les informations suivantes :

* **Nom**de l’Application : Visual Studio Live Share (Insiders)
* **Type d’application**: application Web
* **État des applications**: production
* **Autorisations déléguées**: User. Read
* **URL**de l’Application : https://insiders.liveshare.vsengsaas.visualstudio.com/
* **URL de réponse**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Cette opération ne doit être effectuée qu’une seule fois pour toute personne utilisant Live Share. Pour plus d’informations, voir [ici](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) et [ici](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) .

## <a name="see-also"></a>Voir aussi

* [Comment : collaborer à l’aide de Visual Studio Code](../how-to-guides/vscode.md)
* [Comment : collaborer à l’aide de Visual Studio](../how-to-guides/vs.md)
* [Exigences de connectivité pour Live Share](connectivity.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
