# mysql-php-apache-notes
Notes about installation of MySQL database PHP connection<br>
**Warning: mysqli::__construct(): (HY000/1044): Access denied for user**<br>
_FIX_ : tick _Check all_ of **Global Privileges**<br>

**Unpack the latest version of Moodle into the c:\xampp\htdocs folder.**

**Fix php_intl.dll extension in php.ini :**<br>
Add:<br> 
**extension= php_intl.dll**<br>
**intl.default_locale = en_utf8**<br>
**intl.error_level = E_WARNING**<br>

to **c:\xampp\php\php.ini**<br>
**restart XAMPP to update changes**<br>
~~extension= php_sodium.dll~~ not working ❌<br> 
~~extension= sodium~~ not working ❌<br>

**follow guidance from this link to make sodium works: ✅**<br> 
**https://py-ipv8.readthedocs.io/en/latest/preliminaries/install_libsodium/** <br>
add **extension= php_sodium.dll ✅** <br>
add **extension= sodium.dll ✅** <br>
**hosting with ngrok:** <br>
change **wwwroot** to **ngrok address** <br>
**localhost/moodle** to **http://(ngrok address)/moodle** <br>

**Installation notes** <br>
Create user passwoword and optional database in phpmyadmin first <br>
Use MySQL PID 3306  as Database Port <br>
Have your database connected in php application <br>

**moodle login refused to connect** <br>
Change to **Listen 8083** and **ServerName localhost:8083** <br>
Change to **Listen 444** and **ServerName localhost** <br>
Access https://docs.moodle.org/310/en/Errors_FAQ#Are_you_using_XAMPP.3F to see XAMPP solution <br>
open **config.php** and change to **$CFG->wwwroot   = 'http://localhost:8083/moodle';** <br>
access moodle through **localhost:8083/moodle** <br><br>

**Connect moodle app to moodle desktop** <br>
Dashboard/ <br>
Site administration/ <br>
Plugins/ <br>
Web services/ <br>
External services/ <br>
Settings/<br>
External service/<br>
**Click the tick to enable External Web Services** <br><br>

**Access Mobile settings in Site administration and enable web services for mobile devices** <br>
**Moodle Desktop account is the same to Moodle app account** <br><br>

**Forgot moodle password ?** <br>
Access **moodle/admin/cli/reset_password.php**, run the command and execute the given requests shown in the console <br>

