AdonisJS est une collection de plusieurs paquets construits autour du [noyau du framework](https://github.com/adonisjs/core). Chaque fois que vous nous entendez mentionner la version d'AdonisJS, supposez que nous parlons de la version du noyau du framework.

Tous les autres paquets comme `@adonisjs/lucid`, ou `@adonisjs/mail` ont leurs versions indépendantes et sont libres d'avoir leur cycle de publication.

## Utilisation de semver
Nous suivons strictement le [versionnement sémantique](https://semver.org/) et faisons évoluer la version majeure après chaque modification de rupture. Cela signifie que AdonisJS 5 peut rapidement devenir AdonisJS 8 dans quelques mois.

- Nous augmenterons la version du patch lors de la publication de **corrections de bogues critiques** (ex : 5.2.0 à 5.2.1).
- La version mineure comprend **de nouvelles fonctionnalités** ou **des corrections de bogues non critiques**. De plus, nous allons déprécier des APIs pendant une version mineure. (ex : 5.2.0 à 5.3.0)
- Lorsque nous publions des modifications de rupture, nous augmentons la version majeure (ex : 5.2.0 à 6.0.0).

## Ruptures de compatibilité ascendante
Comme AdonisJS devient mature, nous prenons plus de responsabilités pour ne pas introduire des ruptures de compatibilité, et tous les changements **doivent passer par une phase de dépréciation et de RFC**.

Avant d'introduire un changement radical, nous publierons un [RFC](https://github.com/adonisjs/rfcs) expliquant les raisons de ce changement. S'il n'y a pas d'opposition significative, nous procéderons au changement.

La phase initiale du changement consistera à déprécier les API existantes lors d'une version mineure. Si vous exécutez votre application après ce changement, vous obtiendrez de nombreux avertissements, mais rien ne sera cassé et votre application continuera à fonctionner comme avant.

Après une phase d'un minimum de 4 semaines, nous supprimerons les API dépréciées lors de la prochaine version majeure. La suppression de l'ancien code est essentielle pour garantir que la base de code du framework est bien maintenue et qu'elle n'est pas encombrée de variations passées.

Les modifications suivantes ne sont pas soumises à des ruptures de compatibilité.

- **Les API non documentées et les structures de données internes** peuvent être modifiées au cours de chaque version. Par conséquent, si vous vous appuyez sur des API non documentées ou des membres de classe privés, vous serez seul lorsque nous les modifierons ou les restructurerons.
- **Les versions alpha et suivantes d'AdonisJS** peuvent recevoir des modifications de rupture sans changement de version majeur. Cela s'explique par le fait que nous voulons disposer de la liberté créative nécessaire pour itérer rapidement sur la base des enseignements tirés de la période alpha.

## Cycle de sortie
AdonisJS suit un cycle de publication de 8 semaines pour l'envoi de nouvelles fonctionnalités ou la publication de modifications de rupture. Toutefois, les corrections de bogues critiques et les correctifs de sécurité sont généralement publiés immédiatement.

Vous pouvez consulter notre [roadmap sur Trello](https://trello.com/b/3klaHbfP/adonisjs-roadmap) et notre [carte des prochaines versions](https://trello.com/c/y8PCAodY/47-september-planning-2021) pour connaître les changements à venir.
