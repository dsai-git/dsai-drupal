# Docksal powered Drupal 8 Installation for DSAi

This is a DSAi Drupal 8 installation pre-configured for use with Docksal.  

## Setup instructions

### Step #1: Docksal environment setup

**This is a one time setup - skip this if you already have a working Docksal environment.**  

Follow [Docksal environment setup instructions](https://docs.docksal.io/getting-started/setup/)

### Step #2: Project setup

1. Clone this repo into your Projects directory

    ```
    git clone https://github.com/dsai-git/dsai-drupal
    cd dsai-drupal
    ```

2. Initialize the site

    This will initialize local settings and setup the site via drush

    ```
    fin start
    ```

3. Request latest database snapshot from a team member

4. Import database to your local setup

    ```
    fin db import dev_backup_db.sql
    ```

5. Install necessary php components
    ```
    cd docroot
    fin composer install
    ```

6. Install and build UI components necessary for DSAi theme to work
    ```
    cd docroot/themes/custom/dsai
    fin exec npm install
    fin exec npm run watch
    ```

7. Point your browser to

    ```
    http://dsai-drupal.docksal
    ```

    macOS and Linux users can use http://dsai-drupal.docksal:3000 for browser auto refresh to work
    Windows user will have to refresh browser manually

8. Request admin login and password from a team member to gain acces to the admin panel

9. Go to http://dsai-drupal.docksal/admin/config/development/configuration and "import all" if there are items on the list there

10. Clear cache just in case

    ```
    fin drush cr --root=docroot
    ```