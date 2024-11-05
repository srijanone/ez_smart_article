# srijanone/ez_ai

EzContent AI: Provides AI Features for EZContent


## Installation

### A. Create a new project using composer 

#### 1. Firstly, To create a new project and navigate to the project directory, you need to execute the following commands:
```bash
composer create-project drupal/recommended-project:^10.0 ezai
cd ezai;
```
#### 2. For Composer to understand your new Recipe install-type, you need to require the Composer Installer Extender package.
```bash
composer require oomphinc/composer-installers-extender:2.0.1
```

#### 3. Next, you need to add two entries in composer.json for an install-type and its path:
```bash
"installer-types": ["drupal-recipe"],
"installer-paths": {
 // existing entries omitted...
 "docroot/recipes/contrib/{$name}": [
   "type:drupal-recipe"
 ]
}
```

#### 4. Execute the specified commands to include these two repositories in the composer.json file
```bash
composer config repositories.drupal8 composer https://packages.drupal.org/8
composer config repositories.asset-packagist composer https://asset-packagist.org
```
#### 5. To configure the minimum stability and enable patching, execute the following commands
```bash
composer config minimum-stability dev
composer config extra.enable-patching true
```
#### 6. To enable specific composer plugins for patching and installation purposes, execute the following commands
```bash
composer config --no-plugins allow-plugins.cweagans/composer-patches true
composer config --no-plugins allow-plugins.oomphinc/composer-installers-extender true
```
#### 7. To install Composer Patches Plugin and Drush, execute the following commands
```bash
composer require cweagans/composer-patches
composer require drush/drush
```
#### 8. To merge the composer.libraries.json file into your main composer.json, install the Composer Merge Plugin. From the project directory, open a terminal and run
```bash
composer require wikimedia/composer-merge-plugin 
```

#### 9. Then Edit the composer.json file of your Drupal website, and under the "extra" section add this entry
```bash
"merge-plugin": { "include": [ "web/modules/contrib/*/composer.libraries.json" ] } 
```

#### 10. To require the dev-main branch of ez ai, execute this command
```bash
composer require srijanone/ez_ai:dev-main
```

#### 11. Now run below commands to configure your site
```bash
composer install
drush si
drush recipe recipes/contrib/ez_ai;     
```

### B. Create a new project using ddev

#### 1. Firstly, To create a new project and navigate to the project directory, you need to execute the following commands:
```bash
composer create-project drupal/recommended-project:^10.0 ezai
cd ezai;
```

#### 2. To set up config and start your ddev project, execute the following commands
```bash
ddev config --project-type=drupal9 --docroot=web --create-docroot
ddev start
```
#### 3. For Composer to understand your new Recipe install-type, you need to require the Composer Installer Extender package.
```bash
ddev composer require oomphinc/composer-installers-extender:2.0.1
```

#### 4. Next, you need to add two entries in composer.json for an install-type and its path:
```bash
"installer-types": ["drupal-recipe"],
"installer-paths": {
 // existing entries omitted...
 "docroot/recipes/contrib/{$name}": [
   "type:drupal-recipe"
 ]
}
```

#### 5. Execute the specified commands to include these two repositories in the composer.json file
```bash
ddev composer config repositories.drupal8 composer https://packages.drupal.org/8
ddev composer config repositories.asset-packagist composer https://asset-packagist.org
```
#### 6. To configure the minimum stability and enable patching, execute the following commands
```bash
ddev composer config minimum-stability dev
ddev composer config extra.enable-patching true
```
#### 7. To enable specific composer plugins for patching and installation purposes, execute the following commands
```bash
ddev composer config --no-plugins allow-plugins.cweagans/composer-patches true
ddev composer config --no-plugins allow-plugins.oomphinc/composer-installers-extender true
```
#### 8. To install Composer Patches Plugin and Drush, execute the following commands
```bash
ddev composer require cweagans/composer-patches
ddev composer require drush/drush
```
#### 9. To merge the composer.libraries.json file into your main composer.json, install the Composer Merge Plugin. From the project directory, open a terminal and run
```bash
ddev composer require wikimedia/composer-merge-plugin 
```

#### 10. Then Edit the composer.json file of your Drupal website, and under the "extra" section add this entry
```bash
"merge-plugin": { "include": [ "web/modules/contrib/*/composer.libraries.json" ] } 
```

#### 11. To require the dev-main branch of ez ai, execute this command
```bash
ddev composer require srijanone/ez_ai:dev-main
```

#### 12. Now run below commands to configure your site
```bash
ddev composer install
ddev drush si
ddev drush recipe recipes/contrib/ez_ai;     
```

### C. Install the recipe in existing project
#### 1. For Composer to understand your new Recipe install-type, you need to require the Composer Installer Extender package.
```bash
composer require oomphinc/composer-installers-extender:2.0.1
```

#### 2. Next, you need to add two entries in composer.json for an install-type and its path:
```bash
"installer-types": ["drupal-recipe"],
"installer-paths": {
 // existing entries omitted...
 "docroot/recipes/contrib/{$name}": [
   "type:drupal-recipe"
 ]
}
```

#### 3. Execute the specified commands to include these two repositories in the composer.json file
```bash
composer config repositories.drupal8 composer https://packages.drupal.org/8
composer config repositories.asset-packagist composer https://asset-packagist.org
```
#### 4. To configure the minimum stability and enable patching, execute the following commands
```bash
composer config minimum-stability dev
composer config extra.enable-patching true
```
#### 5. To enable specific composer plugins for patching and installation purposes, execute the following commands
```bash
composer config --no-plugins allow-plugins.cweagans/composer-patches true
composer config --no-plugins allow-plugins.oomphinc/composer-installers-extender true
```
#### 6. To install Composer Patches Plugin and Drush, execute the following commands
```bash
composer require cweagans/composer-patches
composer require drush/drush
```
#### 7. To merge the composer.libraries.json file into your main composer.json, install the Composer Merge Plugin. From the project directory, open a terminal and run
```bash
composer require wikimedia/composer-merge-plugin 
```

#### 8. Then Edit the composer.json file of your Drupal website, and under the "extra" section add this entry
```bash
"merge-plugin": { "include": [ "web/modules/contrib/*/composer.libraries.json" ] } 
```

#### 9. To require the dev-main branch of ez ai, execute this command
```bash
composer require srijanone/ez_ai:dev-main
```

#### 10. Now run below commands to configure your site
```bash
composer install
drush recipe recipes/contrib/ez_ai;     
```

## Tech Stack

**CMS:** Drupal

**Note:** This recipe depends on contributed libraries. Ensure you have Composer set up to manage these dependencies effectively by following the instructions in the guide.

#### Recommended Method for Installing, Updating, and Managing Contributed Module Libraries Using Composer

For detailed instructions on how to efficiently manage and install libraries for contributed Drupal modules using Composer, please refer to the official guide:

[Recommended Method for Installing, Updating, and Managing Contributed Module Libraries Using Composer](https://www.drupal.org/docs/extending-drupal/recommended-method-for-installing-updating-and-managing-contributed-module-libraries-using-composer)


This guide covers how to merge the `composer.libraries.json` with your site's `composer.json` file for seamless updates.

