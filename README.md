# Cours de CMS (wordpress)

## Les métiers du web

- le développeur créé des applications
- l'administrateur système s'occupe des plateformes sur lesquelles tournent les applications
- l'administrateur réseau s'occupe de l'organisations de tous les réseaux d'une structure
- l'administrateur de base de données

## Les thèmes

- [Thèmes WordPress gratuits](https://fr.wordpress.org/themes/)

Quelques mots clés à explorer :
- one page
- portfolio
- shop / commerce
- responsive
- corporate
- community / social
- magazine
- fashion
- blog
- light / white
- dark / black
- design / creative
- rough

## Le child theme

[Child Themes « WordPress Codex](https://codex.wordpress.org/Child_Themes)

Exemple avec twentyseventeen

	twentyseventeen-child/
		functions.php
		screenshot.png (optionnel)
		style.css

## Les plugins

### D'autres plugins

[25 Most Useful WordPress Widgets for Your Site](http://www.wpbeginner.com/showcase/25-most-useful-wordpress-widgets-for-your-site/)

#### Comment désactiver un plugin ?

Pour désactiver un plugin sans passer par le backoffice, vous pouvez rajouter un symbole underscore `_` au début du nom de son dossier (`wp-content/plugins/_monplugin` par exemple).

### Des plugins de mise en page recommandés

#### Page Builder

sur le site de wordpress : [Page Builder by SiteOrigin — WordPress Plugins](https://wordpress.org/plugins/siteorigin-panels/)

le site web officiel : [Page Builder Plugin - SiteOrigin](https://siteorigin.com/page-builder/)

Les widgets en plus : https://wordpress.org/plugins/so-widgets-bundle/

#### Live Composer

sur le site de wordpress : [Page Builder: Live Composer - drag and drop website builder (visual front end site editor) — WordPress Plugins](https://fr.wordpress.org/plugins/live-composer-page-builder/)

le site web officiel : [Page Builder for WordPress: 100% Free Plugin – LiveComposer](https://livecomposerplugin.com/)

#### Elementor

sur le site de wordpress : [Elementor Page Builder — WordPress Plugins](https://wordpress.org/plugins/elementor/)

le site web officiel : [Elementor - Drag & Drop Page Builder for WordPress](https://elementor.com/)

#### D'autres plugins de mise en page :
- [Page Builder by MotoPress — WordPress Plugins](https://wordpress.org/plugins/motopress-content-editor-lite/)
- [Forge - Front-End Page Builder — WordPress Plugins](https://wordpress.org/plugins/forge/)

## Reset du password admin

Par requête sql :

	UPDATE wp_users SET user_pass=MD5("123") WHERE ID = 1

## Lorem ipsum

[Lorem Ipsum - All the facts - Lipsum generator](http://lipsum.com/)

## Resources iconographiques libres de droit

[Unsplash | Free High-Resolution Photos](https://unsplash.com/)
[Trouvez l’inspiration. | Flickr](https://www.flickr.com/)

## La copie de sauvegarde (backup)

### Avec le plugin backwpup

L'idéal : cron (sur le serveur de backup) + wp-cron (sur le serveur web)

Sinon utiliser le plannificateur de tâches (windows) avec la commande : `start http://localhost/mywordpress/wp-cron.php?_nonce=8087d3fe&backwpup_run=runext&jobid=1`

Pensez à augmenter la durée du timeout de votre navigateur. Voici comment procéder avec Firefox : https://superuser.com/questions/303217/how-can-i-change-the-connection-timeout-setting-in-firefox

## La mise en production (MEP) ou la migration

La migration se fait en 2 étapes :
- le transfert des fichiers
- le transfert de la base de données

Mais avant de pouvoir transférer la base de données, il faut remplacer :
- l'ancien nom de domaine par le nouveau
- l'ancien chemin du dossier par le nouveau

Exemples de remplacement du nom de domaine :
- `localhost/mywordpress` => `mywordpress.com`
- `localhost` => `mywordpress.com`
- `localhost:8000/mywordpress` => `mywordpress.com`
- `localhost:8000` => `mywordpress.com`

Exemples de remplacement du chemin du dossier :
- `C:\UwAmp\www\mywordpress` => `/home/bar/www`
- `C:\Utilisateurs\Foo\Bureau\uwamp\www\mywordpress` => `/home/bar/www`
- `/home/foo/public_html/mywordpress` => `/home/bar/www`
- `/var/www` => `/home/bar/www`
- `/var/www/mywordpress` => `/home/bar/www`

### Les plugins de migration

- [Moving WordPress « WordPress Codex](https://codex.wordpress.org/Moving_WordPress)
- [Better Search Replace — WordPress Plugins](https://wordpress.org/plugins/better-search-replace/)
- [Duplicator — WordPress Plugins](https://wordpress.org/plugins/duplicator/)
- [All-in-One WP Migration — WordPress Plugins](https://wordpress.org/plugins/all-in-one-wp-migration/)

### Les plugins de remplacement de texte dans la base de données

- [Command line interface for WordPress | WP-CLI](http://wp-cli.org/)
  [wp search-replace | WP-CLI](http://wp-cli.org/commands/search-replace/)

### Comment trouver le chemin du dossier actuel ?

Vous pouvez utiliser le script `info.php`

    <?php

    echo "domaine: " . $_SERVER["SERVER_NAME"] . "<br />\n";
    echo "dossier: " . $_SERVER["DOCUMENT_ROOT"] . "<br />\n";

