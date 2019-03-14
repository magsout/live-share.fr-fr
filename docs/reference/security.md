---
title: Sécurité - partage en direct de Visual Studio | Microsoft Docs
description: Informations sur les fonctionnalités de sécurité de partage en direct de Visual Studio.
ms.custom: ''
ms.date: 12/17/2018
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
ms.openlocfilehash: 0bc97691ca7733f694190e86140b930e68657ade
ms.sourcegitcommit: 4f733c9053848f26da03d47050bcb734f6c98b31
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/02/2019
ms.locfileid: "57255551"
---
<!--
Copyright © Microsoft Corporation
All rights reserved.
Creative Commons Attribution 4.0 License (International): https://creativecommons.org/licenses/by/4.0/legalcode
-->

# <a name="security-features-of-live-share"></a>Fonctionnalités de sécurité de partage en direct

Sessions de collaboration dans le partage en direct de Visual Studio sont puissants car ils permettent à n’importe quel nombre de personnes pour participer à une session et en collaboration modifier, déboguer et bien plus encore. Toutefois, étant donné ce niveau d’accès, sans aucun doute on intéressé par les fonctionnalités de sécurité que propose de partage en direct. Dans cet article, nous allons fournir des recommandations et des options permettant de sécuriser votre environnement en fonction des besoins.

**Comme avec n’importe quel outil de collaboration, n’oubliez pas que vous devez uniquement partager votre code, de contenu et les applications avec les personnes que dignes de confiance.**

## <a name="connectivity"></a>Connectivité

Toutes les connexions dans le partage en direct de Visual Studio sont SSH ou SSL chiffrés et authentifiés par rapport à un service central pour vous assurer que seules dans la session de collaboration peuvent-ils accéder à son contenu. Par défaut, le partage Live tente une connexion directe et revient sur un relais cloud si une connexion entre l’invité et l’hôte ne peut pas être établie. Notez que les relais de cloud du partage en direct ne conserve pas tout le trafic acheminé vers lui et ne pas « surveillance » le trafic en aucune façon. Toutefois, si vous préférez ne doit ne pas utiliser le relais vous pouvez modifier les paramètres pour toujours vous connecter directement.

Pour en savoir plus sur la modification de ces comportements et les exigences de connectivité du partage en direct, consultez  **[exigences de connectivité pour le partage de Live](connectivity.md)**.

## <a name="invitations-and-join-access"></a>Invitations et accès de jointure

Chaque fois que vous démarrez une nouvelle session de collaboration, Partage Live génère un **nouvel identificateur unique** qui est placé dans le lien d’invitation. Ces liens fournissent une base solide et sécurisée pour inviter des personnes de confiance dans la mesure où l’identificateur dans le lien est « non-à deviner » et est _valide uniquement pour la durée d’une session de collaboration unique_.

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

Mieux encore, la notification vous donne la possibilité de supprimer un invité qui a joint si pour une raison quelconque vous ne connaissez pas les. (Par exemple, si votre lien est accidentellement validé sur un système de conversation de l’entreprise et joint un employé aléatoire.) Cliquez simplement sur le bouton « Supprimer » dans la notification qui s’affiche, et ils seront être supprimés du cache de la session de collaboration.

Dans **VS Code**, même si vous quittez une notification de jointure, vous avez également la possibilité de supprimer un participant après cela. En ouvrant la vue de partage en direct dans l’Explorateur ou de l’onglet personnalisé dans la barre d’activités de VS Code, vous pouvez survoler ou cliquez sur le nom d’un participant et sélectionnez l’icône de « Remove participant » ou l’option.

![Supprimer le participant dans VS Code](../media/vscode-remove-participant.png)

### <a name="requiring-guest-approval"></a>Demander une approbation de l’invité

En règle générale, les participants qui rejoindre une session de collaboration seront **connecté à un partage Live** à l’aide d’un Microsoft compte professionnel ou scolaire (AAD), compte Microsoft personnel ou compte GitHub. Alors que « notification + remove » par défaut pour les utilisateurs connecté fournit une bonne combinaison de vitesse et de contrôle pour ces invités, vous pouvez souhaiter **verrouiller les choses** un peu plus si vous effectuez une opération sensibles.

En outre, dans certaines circonstances de forcer tous les invités à se connecter à une collaboration session peut être problématique. Exemples incluent une personne de nouveau au partage de Live pour joindre en tant qu’invité, apprentissage/scénarios, ou lorsqu’ils collaborent avec une personne qui n’a pas un des types de compte pris en charge. Pour ces raisons, Partage Live peut autoriser les utilisateurs qui sont **ne pas connecté** joindre aux sessions de collaboration en tant que **en lecture seule** invités. Alors que l’hôte doit **approuver** ces invités avant de pouvoir participer par défaut, vous souhaiterez toujours à la place les approuver ou interdire ces invités « anonymes ».

#### <a name="requiring-guest-approval-for-signed-in-users"></a>Nécessitant une approbation invité pour connecter les utilisateurs

Si vous souhaitez empêcher connecté invités de rejoindre votre collaboration sessions jusqu'à ce que vous avez « approved » les, modifiez le paramètre suivant :

* Dans **VS Code**, ajoutez le code suivant settings.json (fichier > Préférences > Paramètres) :

    ```json
    "liveshare.guestApprovalRequired": true
    ```

* Dans **Visual Studio**, définir des outils > Options > Partage Live > « Exiger l’approbation invité » sur True.

    ![Fenêtre Paramètres de Visual Studio avec les invités d’approbation de paramètre en surbrillance](../media/vs-setting-guestapproval.png)

À ce stade, vous devrez approuver chaque invité qui joint.

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

En tant qu’invité, si vous joignez une session où l’hôte a ce paramètre est activé, vous serez averti dans la barre d’état ou de joindre la boîte de dialogue Partage Live est en attente sur l’ordinateur hôte à approuver.

#### <a name="auto-rejecting-or-accepting-users-that-are-not-signed-in-anonymous"></a>Acceptation ou rejet d’automatique des utilisateurs qui ne sont pas signés dans (anonyme)

Comme décrit ci-dessus, le partage Live peut être configuré pour autoriser **les utilisateurs qui ne sont pas signés dans** rejoindre une session de collaboration en tant que **en lecture seule** invités.  Bien que ces **invités « anonymes » doivent entrer un nom** lors de la jointure, un nom simple ne fournit pas le même niveau d’assurance comme une connexion réelle. Par conséquent, **par défaut, l’hôte est invité à approuver** n’importe quel invité anonyme, quel que soit le « approbation invité » définition décrit ci-dessus.

Vous pouvez **toujours rejeter** (désactiver les invités anonymes) ou **toujours accepter** les utilisateurs anonymes à la place comme suit :

* Dans **VS Code**, affectez la valeur `liveshare.anonymousGuestApproval` dans settings.json (fichier > Préférences > Paramètres) à `accept`, `reject`, ou `prompt` (la valeur par défaut) selon les besoins.

* Dans **Visual Studio**, définir des outils > Options > Partage Live > « approval invité anonyme » pour accepter, rejeter ou une invite (la valeur par défaut) en tant qu’appropriées.

 **Malgré tout, n’oubliez pas que vous devez uniquement envoyer Partage Live invitation des liens vers des personnes que vous faites confiance.**

## <a name="controlling-file-access-and-visibility"></a>Contrôle de l’accès aux fichiers et visibilité

En tant qu’invité, modèle distant du partage Live vous donne accès en lecture/écriture rapide aux fichiers et dossiers de que l’ordinateur hôte a partagé avec vous sans avoir à synchroniser tout le contenu d’un projet. Vous pouvez par conséquent indépendamment Parcourir et modifier des fichiers dans l’arborescence de la totalité du fichier partagé. **Toutefois, cette liberté pose certains risques à l’hôte.** Dans son concept, un développeur peut choisir d’aller dans et modifier du code source sans votre connaissance ou consultez le code source sensibles ou « secrets » situés quelque part dans l’arborescence des fichiers partagés. Par conséquent, en tant qu’hôte, vous souhaiterez peut-être pas toujours l’invité d’accéder à l’intégralité d’un projet que vous partagez. Heureusement, un autre avantage de ce modèle à distance est que vous pouvez choisir de « exclure les fichiers que vous ne souhaitez pas partager avec d’autres personnes sans sacrifier les fonctionnalités ». Vos invités peuvent toujours participer des éléments tels que les sessions qui exigeraient normalement accéder à ces fichiers lorsqu’ils souhaitaient faire dans leur propre de débogage.

Vous pouvez accomplir cela en ajoutant un **. vsls.json** fichier au dossier ou au projet que vous partagez. Les paramètres que vous ajoutez à ce fichier au format json modifie comment Partage Live traite les fichiers. En plus de vous fournir un contrôle direct, ces fichiers peuvent également être validées dans le contrôle de code source par conséquent, toute personne le clonage d’un projet pourront tirer parti de ces règles sans aucun effort supplémentaire de leur part.

Voici un exemple. vsls.json fichier :

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
> Vous pouvez également rendre les tous les fichiers/dossiers vous partagez **en lecture seule** lorsque vous démarrez une session de collaboration. Consultez [ci-dessous](#read-only-mode) pour plus d’informations.

Nous allons étudier comment ces propriétés changent invités réalisables.

### <a name="properties"></a>Properties

Le **excludeFiles** propriété vous permet de spécifier une liste de modèles de fichier glob (comme ceux trouvé les fichiers .gitignore très) Partage Live qui empêche l’ouverture de certains fichiers ou dossiers pour les visiteurs. N’oubliez pas qu’il s’agit qui inclut des scénarios tels que d’un invité _suivant ou le passage à votre emplacement d’édition, pas à pas détaillé dans un fichier pendant le débogage collaboratifs, les fonctionnalités de navigation du code comme atteindre la définition et bien plus encore._ Il concerne les fichiers que vous souhaitez jamais partager les circonstances telles que celles contenant des secrets, des certificats ou des mots de passe. Par exemple, car ils contrôlent la sécurité,. vsls.json les fichiers sont toujours exclus.

Le **hideFiles** propriété est similaire, mais pas aussi stricte. Ces fichiers sont simplement masquées dans l’arborescence des fichiers. Par exemple, si vous avez à parcourir un de ces fichiers pendant le débogage, il est toujours ouvert dans l’éditeur. Cette propriété est particulièrement utile si vous n’avez pas d’un programme d’installation du fichier .gitignore (comme c’est le cas si vous utilisez un système de contrôle source différente) ou si vous souhaitez simplement augmenter ce qui existe déjà pour éviter l’encombrement ou toute confusion.

Le **gitignore** paramètre détermine comment Partage Live doit traiter le contenu des fichiers .gitignore dans des dossiers partagés. Par défaut, les modèles glob dans les fichiers .gitignore est traités comme s’ils ont été spécifiés dans la propriété « hideFiles ». Toutefois, vous pouvez choisir un comportement différent en utilisant l’une des valeurs suivantes :

| Option    | Résultat                                                                                                                 |
| --------- | ---------------------------------------------------------------------------------------------------------------------- |
| `none`    | contenu du fichier .gitignore est visibles pour les invités dans l’arborescence des fichiers (en supposant qu’ils ne sont pas filtrés en définissant un rédacteur en chef invité). |
| `hide`    | **La valeur par défaut.** Modèles glob dans .gitignore est traitées comme si elles se trouvaient dans la propriété « hideFiles ».                   |
| `exclude` | Modèles glob dans .gitignore est traitées comme si elles se trouvaient dans la propriété « excludeFiles ».                                 |

Un inconvénient de la `exclude` paramètre est que le contenu des dossiers comme node_modules est fréquemment dans .gitignore mais peut être utile de pas à pas détaillé lors du débogage. Par conséquent, Partage Live prend en charge la possibilité pour inverser une à l’aide de la règle « ! » dans la propriété excludeFiles. Par exemple, cela. vsls.json fichier exclure tous les éléments de « .gitignore » à l’exception de node_modules :

```json
{
    "$schema": "http://json.schemastore.org/vsls",
    "gitignore":"exclude",
    "excludeFiles":[
        "!node_modules"
    ]
}
```

Les règles de masquer et d’exclusion sont traitées séparément, donc si vous souhaitez toujours masquer node_modules pour réduire l’encombrement sans réellement à l’exclusion, vous pouvez simplement modifier le fichier comme suit :

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

### <a name="vslsjson-files-in-sub-folders"></a>. vsls.json des fichiers dans les sous-dossiers

Enfin, tout comme .gitignore,. vsls.json fichiers peuvent être placés dans les sous-dossiers. Masquer/exclure des règles sont déterminées en commençant par le. fichier vsls.json dans le dossier racine que vous avez partagé (le cas échéant) et puis parcourant à chaque sous-dossier à partir de là pointe vers un fichier donné à rechercher. vsls.json fichiers traiter. Le contenu de. vsls.json fichiers des dossiers plus loin dans l’arborescence des fichiers puis compléter (ou le remplacement) règles établies à des niveaux supérieurs.

### <a name="disabling-external-file-sharing"></a>Désactivation du partage de fichier externe

Par défaut, Partage Live partagent également tous les fichiers s’ouvre l’hôte qui sont externes au dossier partagé / solution. Cela facilite l’ouvrir rapidement les autres fichiers connexes sans avoir à partager de nouveau.

Si vous préférez désactiver cette fonctionnalité :

* Dans **VS Code**, ajoutez le code suivant à settings.json :

    ```json
    "liveshare.shareExternalFiles": false
    ```

* Dans **Visual Studio**, définir des outils &gt; Options &gt; Partage Live &gt; « Partage des fichiers externes » sur False

## <a name="read-only-mode"></a>Mode lecture seule

Parfois, lorsque vous partagez votre code en tant qu’hôte, vous ne voulez vos invités pour apporter des modifications. Vous devrez peut-être votre invité à examiner une partie de votre code, ou vous affichent votre projet à un grand nombre d’invités et que vous ne souhaitez pas les modifications accidentelles ou inutiles qu’il veut. Partage en direct offre la possibilité de partager des projets en mode lecture seule.

En tant qu’hôte, lors du partage, vous avez la possibilité d’activer le mode lecture seule pour une session de collaboration. Lorsqu’un invité rejoint, ils ne seront pas en mesure d’apporter des modifications au code, bien que vous pouvez toujours voir les curseurs entre eux et met en évidence ainsi naviguez dans le projet.

Vous pouvez toujours même déboguer avec invités en mode en lecture seule. Invités n’aura pas la possibilité de parcourir le processus de débogage, mais peuvent toujours ajouter ou supprimer des points d’arrêt et inspecter les variables. En outre, vous pouvez toujours partager des serveurs et terminaux (en lecture seule) avec les invités.

Pour plus d’informations sur le démarrage d’une session de collaboration en lecture seule : [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-project) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-project)

## <a name="co-debugging"></a>Codébogage

Lorsque vous êtes confronté difficiles problèmes de codage ou des bogues, avoir une paire supplémentaire d’yeux lors du débogage peut être très utile. Partage en direct de Visual Studio permet à « débogage collaboratifs » ou « colocalisés débogage » en partageant la session de débogage avec tous les invités chaque fois que l’hôte démarre le débogage.

En tant qu’hôte, vous êtes dans un contrôle complet sur lors du démarrage d’une session de débogage ou s’arrête, mais que le même emplacement de débogage pose certains risques si vous partagez avec une personne n’est pas fiable. Partage en direct permet aux invités vous inviter à exécuter des commandes de console/REPL et il est donc **un risque d’un acteur malveillant exécutant une commande que vous souhaiteriez pas qu’exécuter**.

Par conséquent, vous devez **déboguer uniquement conjointement avec des personnes de confiance.**

Pour en savoir plus : [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#co-debugging) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#co-debugging)

## <a name="sharing-a-local-server"></a>Partage d’un serveur local

Lors du codébogage, il peut être très utile de pouvoir accéder aux différentes parties de l’application prise en charge par l’hôte pendant la session de débogage. Voulez-vous accéder à l’application dans un navigateur, accéder à une base de données locale ou appuyez sur un point de terminaison REST à partir de vos outils. Partage en direct vous permet de « partage un serveur » qui mappe un port local sur l’ordinateur de l’hôte sur le même port exact sur l’ordinateur de l’invité. En tant qu’invité, vous pouvez alors interagir avec l’application comme s’il s’exécutait localement sur votre ordinateur (par exemple, l’hôte et l’invité peuvent à la fois accéder à une application web s’exécutant sur http://localhost:3000).

Toutefois, en tant qu’hôte, vous devez **être très sélective avec les ports que vous partagez** avec les invités et de partage uniquement application ports plutôt des ports système. Pour les invités, des ports partagés seront comportent exactement comme il le ferait si le service/serveur était en cours d’exécution sur leur propre ordinateur. Cela est très utile, mais si le port incorrect est partagé permettre également être à risque. Pour cette raison, le partage en direct ne fait pas d’hypothèses concernant ce qui doit ou ne doit pas être partagé sans un paramètre de configuration et de l’hôte qui effectue une action.

Dans Visual Studio, le **port de l’application web** spécifié dans les projets ASP.NET est **automatiquement partagés pendant le débogage uniquement** pour faciliter l’accès invité à l’application web lors de l’exécution. Toutefois, vous pouvez désactiver cette automatisation en définissant des outils > Options > Partage Live > « Partage web app sur debug » sur « False » si vous préférez.

Dans Visual Studio Code, Live partager tente de **détecter les ports d’application appropriée** et de les partager. Toutefois, vous pouvez le désactiver en ajoutant le code suivant à settings.json :

        liveshare.autoShareServers: false

Dans les deux cas, soyez vigilant lorsque vous partagez des ports supplémentaires.

Pour plus d’informations sur la configuration de la fonctionnalité ici : [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-server) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-server)

## <a name="sharing-a-terminal"></a>Partage d’un terminal

Aujourd’hui, le développement utilise couramment un large éventail d’outils en ligne de commande. Heureusement, Live Share vous permet de « partager un terminal » avec vos invités en tant qu’hôte. Le terminal partagé peut être en lecture seule ou entièrement collaborative afin de vous et les invités peuvent exécuter des commandes et voir les résultats. En tant que l’ordinateur hôte, vous êtes en mesure d’autoriser les autres collaborateurs soit voir simplement la sortie ou pour utiliser n’importe quel numéro de ligne de commande Outils pour exécuter des tests, builds, ou même de triage des problèmes spécifiques à l’environnement.

Seuls les ordinateurs hôtes peuvent démarrer des terminaux partagées pour empêcher les invités à partir d’un démarrage et de faire quelque chose vous ne sont pas attendu ou l’observation des. Lorsque vous démarrez un terminal partagé en tant qu’hôte, vous pouvez spécifier si elle doit être en lecture seule ou lecture/écriture. Lorsque le terminal est en lecture/écriture, tout le monde peut taper dans le terminal, y compris l’hôte, ce qui facilite l’intervenir si un invité fait quelque chose que vous n’aimez pas. Toutefois, pour plus de sécurité, vous devez **donner uniquement un accès en lecture/écriture aux invités lorsque vous savez ils en ont réellement besoin** cap et gardez-le terminaux en lecture seule pour les scénarios où vous voulez juste l’invité pour voir le résultat de toutes les commandes que vous exécutez.

Dans Visual Studio, les terminaux ne sont pas partagées par défaut. Dans VS Code, terminaux sont automatiquement partagées **en lecture seule** par défaut. Toutefois, vous pouvez le désactiver en ajoutant le code suivant à settings.json :

```json
"liveshare.autoShareTerminals": false
```

Pour en savoir plus : [![VS Code](../media/vscode-icon-15x15.png)](../use/vscode.md#share-a-terminal) [![VS](../media/vs-icon-15x15.png)](../use/vs.md#share-a-terminal)

## <a name="aad-admin-consent"></a>Consentement de l’administrateur AAD

Lorsque la connexion à l’aide d’un Microsoft soutenu **Professionnel ou scolaire d’adresse de messagerie** peut s’afficher un message indiquant **« Besoin d’approbation administrateur »** lors de la connexion. Il s’agit, car le partage Live nécessite un accès en lecture aux informations de l’utilisateur pour ses fonctionnalités de sécurité et de votre client Azure AD est configuré pour exiger des « consentement de l’administrateur » pour accéder au contenu du répertoire de nouvelles applications.

Votre administrateur AD devra résoudre ce problème à l’aide des informations suivantes :

* **Nom de l’application**: Partage en direct de Visual Studio (Insiders)
* **Type d’application**: Application web
* **État de l’application**: Production
* **Autorisations déléguées**: User.Read
* **URL de l’application**: https://insiders.liveshare.vsengsaas.visualstudio.com/
* **L’URL de réponse**: https://insiders.liveshare.vsengsaas.visualstudio.com/auth/redirect/windowslive/

Cela aurait uniquement besoin d’être effectuée qu’une fois pour toute personne utilisant le partage en direct. Consultez [ici](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-v2-scopes#admin-restricted-scopes) et [ici](https://stackoverflow.com/questions/39861830/azure-ad-admin-consent-from-the-azure-portal) pour plus d’informations.

## <a name="see-also"></a>Voir aussi

* [Comment : Collaborer à l’aide de Visual Studio Code](../use/vscode.md)
* [Comment : Collaborer à l’aide de Visual Studio](../use/vs.md)
* [Exigences de connectivité pour Live Share](connectivity.md)

Vous rencontrez des problèmes ? Voir la section [dépannage](../troubleshooting.md) ou [fournir des commentaires](../support.md).
