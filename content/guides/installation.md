---
summary: Créez votre première application AdonisJS
---

AdonisJS est un framework Node.js, et il nécessite donc que Node.js soit installé sur votre ordinateur. Pour être précis, nous avons besoin au moins de la dernière version de `Node.js v14`.

Vous pouvez vérifier les versions de Node.js et de npm en exécutant les commandes suivantes.

```sh
# Vérifier la version de node.js
node -v
```
Si vous n'avez pas installé Node.js, vous pouvez [télécharger le binaire](https://nodejs.org/en/download) pour votre système d'exploitation depuis le site officiel.

Si vous êtes à l'aise avec la ligne de commande, nous vous recommandons d'utiliser [Volta](https://volta.sh) ou [Node Version Manager](https://github.com/nvm-sh/nvm) pour installer et exécuter plusieurs versions de Node.js sur votre ordinateur.

## Créer un nouveau projet
Vous pouvez créer un nouveau projet en utilisant [npm init](https://docs.npmjs.com/cli/v7/commands/npm-init), [yarn create](https://classic.yarnpkg.com/en/docs/cli/create) ou [pnpm create](https://pnpm.io/tr/next/cli/create). Ces outils téléchargeront le pack de démarrage d'AdonisJS et lanceront le processus d'installation.

:::codegroup

```sh
// title: npm
npm init adonis-ts-app@latest hello-world
```

```sh
// title: yarn
yarn create adonis-ts-app hello-world
```

```sh
// title: pnpm
pnpm create adonis-ts-app hello-world
```
:::

Le processus d'installation vous invite à effectuer les sélections suivantes.

#### Structure du projet
Vous pouvez choisir l'une des structures de projet suivantes.

- La structure de projet `web` est idéale pour créer des applications classiques avec un rendu côté serveur. Nous configurons la prise en charge des sessions et installons également le moteur de template d'AdonisJS.
- La structure de projet `api` est idéale pour créer un serveur API.
- La structure de projet `slim` crée la plus petite application AdonisJS possible et n'installe aucun paquet supplémentaire, à l'exception du noyau du framework.

---

#### Nom du projet
Le nom du projet. Nous définissons cette valeur dans le fichier `package.json`.

---

#### Configurer eslint/prettier
En option, vous pouvez configurer eslint et prettier. Les deux paquets sont configurés avec les paramètres utilisés par l'équipe d'AdonisJS.

---

#### Configurer Webpack Encore
En option, vous pouvez également configurer [Webpack Encore](./http/assets-manager.md) pour regrouper et servir les dépendances frontales.

Veuillez noter qu'AdonisJS est un framework backend et ne s'occupe pas des outils de construction front. La configuration de Webpack est donc facultative.

## Démarrer le serveur de développement 
Après avoir créé l'application, vous pouvez démarrer le serveur de développement en exécutant la commande suivante.

```sh
node ace serve --watch
```

- La commande `serve` démarre le serveur HTTP et effectue une compilation en mémoire de TypeScript en JavaScript.
- Le drapeau `--watch` a pour but de surveiller les changements dans le système de fichiers et de redémarrer le serveur automatiquement.

Par défaut, le serveur démarre sur le port 3333 (défini dans le fichier .env). Vous pouvez voir la page d'accueil en visitant : http://localhost:3333.

## Compiler pour la production
Vous devez toujours déployer le JavaScript compilé sur votre serveur de production. Vous pouvez créer le build de production en exécutant la commande suivante :

```sh
node ace build --production
```

La sortie compilée est écrite dans le dossier `build`. Vous pouvez vous rendre dans ce dossier et démarrer le serveur en exécutant directement le fichier `server.js`. En savoir plus sur le [processus de construction de TypeScript](./fundamentals/typescript-build-process.md)

```sh
cd build
node server.js
```
