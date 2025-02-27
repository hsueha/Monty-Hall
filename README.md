<p align="center"><a href="https://www.rpi.edu/" target="_blank"><img src="http://scer.rpi.edu/sites/default/files/logo-with-tag.jpg" width="400"></a></p>

# Developer Installation Guide
The website is currently being hosted on Heroku with a Laravel backend implementation and MySQL as the database. As such, backend developers will need to install PHP7, Composer, MySQL, and Git. Frontend developers will need to install PHP7, Composer, Node.js, NPM, and Git.

## Installing Git
1. For easy installation, it is recommend to install the [GitHub Desktop](https://desktop.github.com/) Client for Mac and Windows Machines
2. On Debian machines, running `sudo apt install git` should install the git CLI. As a note, you will need to authenticate your terminal by generating a token. Please refer to the [GitHub Docs](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token) for details.

## Install PHP

### Windows
1. Head to the official [PHP](https://windows.php.net/download#php-7.4) download page and download the current stable PHP7 version. It is recommend to install the `VC15 x64 Thread Safe` version.
2. Extract the folder on your desktop. Rename it to `php7`
3. Rename the file `php.ini-development` to `php.ini`
4. Open the `php.ini` file in NotePad and change `memory_limit` to `1G`
5. Remove `;` for the following lines `extension_dir = "ext"`, `extension=curl`, `extension=gd2`, `extension=mbstring`, `extension=openssl`, `extension=pdo_mysql`, `extension=sockets` and `extension=pdo_sqlite`
6. Place the `php7` folder in `C:\Program Files`
7. In the Windows Search, type in `system variables` and a Control Panel result should appear titled `Edit the system environment variables`
8. Click `Environment Variables...`
9. Under `System Variables` click on `Path` and then click `edit`.
10. Click `new` and enter in the box `C:\Program Files\php7`
11. Save your changes and exit the windows
12. Open `command prompt` and verify installation by running `php --verison`


### Mac
1. Download the [brew](https://docs.brew.sh/Installation) package manager for Mac
2. Run in Terminal `brew install php`
2. Verify installation by running `php -v`

### Debian/Ubuntu
1. Open terminal and run the following command `sudo apt install php libapache2-mod-php`
2. Verify installation by running `php -v`
3. Install php-mysql package through apt as well: `sudo apt install php-mysql`

## Install MySQL

### Windows
1. Download the mysql-installer-community (https://dev.mysql.com/downloads/installer/) (you don't need to make an account, you can just click "No thanks, just start my download")
2. Open the installer and choose Developer Default as the Setup Type (should be defaulted to that)
3. Click next and execute to install all the products
4. When it's finally done, keep clicking next, all default options should be okay
5. You may make your own Root Account Password
6. Keep clicking Next/Execute
7. Enter your password for the root account and check to make sure connection is successful, then continue through the installer until it's all finished
8. In order to use the command "php artisan migrate" on the project, we have to add a monty_hall database. Open the MySQL Command Line Client and type in your password. Use the command "CREATE DATABASE monty_hall;" in the client. You can use the "SHOW DATABASES;" command to ensure that there is a monty_hall database. Lastly, make sure to change your .env file to include your root account password under "DB_PASSWORD". The "php artisan migrate" command should now work.

### Debian/Ubuntu
1. Open the terminal and issue the following command: `sudo apt install mysql-server`
2. This will install the MySQL server package (you can use `apt info mysql-server` to see package into)
3. Verify the package is installed by running `mysql --version`

### Mac
1. Download the [brew](https://docs.brew.sh/Installation) package manager for Mac
2. Run in Terminal `brew install mysql`
2. Verify the package is installed by running `mysql --version`

## Install Composer

### Windows
1. Download and run the [composer](https://getcomposer.org/doc/00-intro.md#installation-windows) install file
2. When prompted, please check `Update this php.ini`
3. Open command prompt and test installation by running `composer`
4. Open the Monty-Hall Git Clone in command prompt (typically run `cd Documents\GitHub\Monty-Hall`) and run `composer install --ignore-platform-reqs`

### Debian / Ubuntu
1. Open the terminal and run the following: `sudo apt install composer`
2. Check to see that composer was installed successfully: `composer --version`
3. CD to the Monty-Hall directory in terminal, and run `composer install`

### Mac
TBD

## Install Node.js and NPM
Make sure that the versions are Node.js 14.X.X and NPM 6.X.X. These can be installed with installers, by compiling from source, or with package managers.

### Installer / Source
Use either an installer (Windows or Mac) or the binaries or source code (Linux) from [here](https://nodejs.org/en/download/) to set up Node.js and NPM:

### Package Manager
For instructions to download with a package manager instead, see [here](https://nodejs.org/en/download/package-manager/). Node.js and NPM should come together.

### Verification
To verify that both have installed correctly, run the following commands;

`node -v`

This should print a variation of `v14.X.X`

`npm -v`

This should print a variation of `6.X.X`

## Running a local Laravel server
Laravel comes built-in with the ability to run a local webserver using just PHP. In order to run a local version of the website and see your changes, please clone the Git repository. 

### Setting up the Laravel environment
1. Open the root file directory of the project using your terminal (`cd location\of\your\folder`)
2. Copy the file `.env.example` and rename it as `.env`, make sure this file is hidden!
3. Run `composer install` to install required packages
4. Run `php aritsan generate:key` to generate a valid `APP_KEY`
5. Run `npm install` to install NPM-related dependencies (for Laravel Mix)
6. Run `npm run dev` to compile front-end assets
7. Run `php artisan serve` to actually run the webserver. Use this command after setup.

# Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains over 1500 video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

# License

Open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
