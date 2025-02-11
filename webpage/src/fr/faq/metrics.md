# Pourquoi des statistiques d'utilisation ?

## En quoi les statistiques d'utilisation sont-elles utiles ?

QOwnNotes (l'application elle-même) est **développée par une ou parfois deux personnes sur leur temps libre**.

Les versions sont compilées pour un grand nombre de plate-formes (souvent de très vielles versions de ces dernières). Les garder à jour représente beaucoup de travail.

Les statistiques d'utilisation sont la seule véritable source d'information permettant de savoir quelles versions des plate-formes et des distributions et quelles fonctionnalités sont utilisées par les utilisateurs. Elles permettent de prendre des décisions concernant les versions à mettre à la retraite, quelles fonctionnalités nécessitent plus de travail et lesquelles sont rarement utilisées.

Les mêmes principes s'appliquent pour les langues utilisées, ce qui guide les traductions de l'application et de sa documentation.

## Où les statistiques d'utilisation sont-elles stockées ?

Les statistiques d'utilisation sont transmises et stockées sur un serveur [Matomo](https://matomo.org/) auto-hébergé. Seules les deux développeurs principaux ont accès aux données. **Aucunes données ne sont partagées avec des tierces parties.**

## Comment les statistiques d'utilisation sont-elles collectées ?

Les statistiques d'utilisation sont **anonymisées** sur le serveur Matomo après réception (l'adresse IP en est, par exemple, ôtée).

Aucune information personnelle - telle que du texte que vous avez entré ou les noms des notes - ne sont collectées ni stockées sur le serveur !

## Qu'est-ce qui est collecté ?

Sont transmises des informations basiques telles que la résolution de l'écran, le système d'exploitation et la version de QOwnNotes utilisée.

De plus des évènements sont, par exemple, envoyés au serveur quand des actions sont utilisées dans les applications.

QOwnNotes est un logiciel libre open-source. Vous pouvez contrôler les statistiques d'utilisation à n'importe quel moment en recherchant par exemple [sendVisitIfEnabled](https://github.com/pbek/QOwnNotes/search?q=sendVisitIfEnabled) et [sendEventIfEnabled](https://github.com/pbek/QOwnNotes/search?q=sendEventIfEnabled) dans le code source pour voir ce qui est envoyé.

**Aucune information personnelle - telle que du texte que vous avez entré ou les noms des notes - ne sont collectées ni stockées sur le serveur !**

## Puis-je désactiver les statistiques d'utilisation ?

Vous pouvez les désactiver au premier démarrage de l'application dans la boîte de dialogue de bienvenue, ou plus tard dans les paramètres.

## Pourquoi les statistiques d’utilisation ne sont-elles pas désactivées par défaut ?

Les réglages par défaut sont rois. Désactiver par défaut les statistiques d'utilisation voudrait pour ainsi dire aucunes statistiques utilisables.

La plupart des gens se fichent des statistiques d'utilisation. Ceux qui se préoccupent des statistiques d'utilisation et ne veulent pas voter avec les leurs concernant ce qui fera l'objet d'un travail ou pris en charge, peuvent facilement les désactiver au premier démarrage de l'application.

Vous verrez même une seconde boîte de dialogue qui vous informera sur les statistiques d’utilisation si vous avez clôt la boîte de dialogue de bienvenue trop tôt.
