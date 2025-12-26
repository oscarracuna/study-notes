
[[Wordpress]] can be installed on a Windows, Linux or Mac OS. 

Below is the directory structure of a default WP install.

```
Rhaenesis@htb[/htb]$ tree -L 1 /var/www/html
.
├── index.php
├── license.txt
├── readme.html
├── wp-activate.php
├── wp-admin
├── wp-blog-header.php
├── wp-comments-post.php
├── wp-config.php
├── wp-config-sample.php
├── wp-content
├── wp-cron.php
├── wp-includes
├── wp-links-opml.php
├── wp-load.php
├── wp-login.php
├── wp-mail.php
├── wp-settings.php
├── wp-signup.php
├── wp-trackback.php
└── xmlrpc.php
```

## Key WP Files
The root directory of WordPress contains files that are needed to configure WP to function correctly.

- index.php is the homepage.
- license.txt contains useful information such as the version WP installed.
- wp-activate.php is used for the email activation process when setting up a new WP site.
- wp-admin folder contains the login page for the administrator access and the backend dashboard. Once a user logged in, they can make changes to the site based on their assigned permissions. The login page can be located at one of the following paths:
	- /wp-admin/login.php
	- /wp-admin/wp-login.php
	- /login/php
	- wp-login.php

This file can also be renamed to make it more challenging to find the login page.

- xmlrpc.php is a file representing a feature of WP that enables data to be transmitted with HTTP acting as the transport mechanism and XML as the encoding mechanism. This type of communication has been replaced by the WP [[REST]] [[API]].

## WordPress Configuration File
- The wp-config.php file contains information required by WP to connect to the database, such as the database name, database host, username and password, authentication keys and salts, and the database table prefix. This configuration file can also be used to activate DEBUG mode, which can be useful in troubleshooting.

Example of wp-config.php

```php
<?php
/** <SNIP> */
/** The name of the database for WordPress */
define( 'DB_NAME', 'database_name_here' );

/** MySQL database username */
define( 'DB_USER', 'username_here' );

/** MySQL database password */
define( 'DB_PASSWORD', 'password_here' );

/** MySQL hostname */
define( 'DB_HOST', 'localhost' );

/** Authentication Unique Keys and Salts */
/* <SNIP> */
define( 'AUTH_KEY',         'put your unique phrase here' );
define( 'SECURE_AUTH_KEY',  'put your unique phrase here' );
define( 'LOGGED_IN_KEY',    'put your unique phrase here' );
define( 'NONCE_KEY',        'put your unique phrase here' );
define( 'AUTH_SALT',        'put your unique phrase here' );
define( 'SECURE_AUTH_SALT', 'put your unique phrase here' );
define( 'LOGGED_IN_SALT',   'put your unique phrase here' );
define( 'NONCE_SALT',       'put your unique phrase here' );

/** WordPress Database Table prefix */
$table_prefix = 'wp_';

/** For developers: WordPress debugging mode. */
/** <SNIP> */
define( 'WP_DEBUG', false );

/** Absolute path to the WordPress directory. */
if ( ! defined( 'ABSPATH' ) ) {
	define( 'ABSPATH', __DIR__ . '/' );
}

/** Sets up WordPress vars and included files. */
require_once ABSPATH . 'wp-settings.php';

```

## Key WordPress Directories

- The wp-content folder is the main directory where plugins and themes are stored. The subdirectory uploads/ is usually where any files uploaded to the platform are stored. *These directories and files should be carefully enumerated as they may lead to contain sensitive data that could lead to remote code execution or exploitation of other vulnerabilities or misconfigurations.*

- wp-includes contains everything except for the administrative components and the themes that belong to the website. This is the directory where core files are stored, such as certificates, fonts, [[JavaScript]] files, and widgets.
```
Rhaenesis@htb[/htb]$ tree -L 1 /var/www/html/wp-includes
.
├── <SNIP>
├── theme.php
├── update.php
├── user.php
├── vars.php
├── version.php
├── widgets
├── widgets.php
├── wlwmanifest.xml
├── wp-db.php
└── wp-diff.php
```


## WordPress User Roles
There are five types of users in a standard WordPress installation.

|Role|Description|
|---|---|
|Administrator|This user has access to administrative features within the website. This includes adding and deleting users and posts, as well as editing source code.|
|Editor|An editor can publish and manage posts, including the posts of other users.|
|Author|Authors can publish and manage their own posts.|
|Contributor|These users can write and manage their own posts but cannot publish them.|
|Subscriber|These are normal users who can browse posts and edit their profiles.|

Gaining access as an administrator is usually needed to obtain code execution on the server. However, editors and authors might have access to certain vulnerable plugins that normal users do not.