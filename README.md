# laravel | Learning Laravel
[YT channel](https://www.youtube.com/watch?v=FQnhpuYldes&list=PLjVLYmrlmjGfh2rwJjrmKNHzGxCZwBsqj&index=4)
## Start
### Requirements
- Installation of *PHP Local Server* (XAMPP, WAMP)
  - To check, run command in command prompt <code> php -v </code>
- Installation of **Composer** [Composer](https://getcomposer.org/ )
   - To check, run command in command prompt <code> composer </code>
      - if the composer didn't run, check the path if it installed or not via <code> echo %PATH% </code>
     - **PATH:** C/users/jarvis/AppData (hidden folder)/roaming/composer/vendor/bin
     - ![Path Environment Variable](https://github.com/prolinkz/laravel/assets/45316278/c340f49c-c45e-46f5-9864-de7acc1b8bd9)
- Installation of Laravel fremework [laravel](https://laravel.com/docs/8.x/installation#installation-via-composer)
     - To check, run command in command prompt <code> laravel --version </code>

- Installation of *Code Editor* (VS Code, Sublime, Notepad++)

##### What is COmposer?
- A dependency manager for PHP (Payment gateway requires multi files and it install all required files first)
- Install package with simple Command ( 
- Can Update version packages, framwork etc
- Composer can used with any PHP framwork

### Create Project
Once the lab is ready to start work, we first need a project name (Directory to save project files). So first we run the __Laravel__ then create a new project.
- Run Laravel Globally via command <code> composer global require laravel/installer   [laravel Globally](https://laravel.com/docs/8.x/installation#the-laravel-installer)
  - we also run the Laravel via composer, but the Globally helps in working from any path [laravel via composer](https://laravel.com/docs/8.x/installation#installation-via-composer)
- Creating New Project
 * Navigate to the Xamp>htdocs folder, click on address bar and write <code> cmd </code> . The command propmt will open.
 * Now write the artissan command to create a new project <code> laravel new project_name </code>
 * Enter into the project file via <code> cd example-app </code>
 * Run the Project via <code> php artisan serve </code> this will start the project to browse

## Directory Structure
We know that laravel application start run via host  <code> php artisan serve </code>  command.
WE can see all the files and folders in project folder when we creae new project

> app
    - Kernal.php (
    - Custom Handler
>
    >> HHTP (Important MVC
      * Controllers (Handle all Controllers here)
      * MidleWare ( provide security feature, Authentication)
      * Modules (Users information)
      * Providers (Services Providers)
> Bootstrap
  * its not a CSS desineing purpose, but it is used to speedup the application. It will cache the directory path to run smoothly

> config
    *

> databse
  * migration (handles database management)
  * seeders ( fake data creation)

> public
   * index.php is the file to strat.  here all the __CSS__ and _JS_ source files exists.

> Routes
  * web.php (defaullt page) will contians the path routes to the page to browse from > resousces directory > views> webpage.blad.php
  * Routes plays MV role in MVC structure. we create Modle here for Views

```
Route::get('/', function(){
  return view('welcome');
});
```
  * channel.php ( this page for creating and managing broadcasting
  * api.php (this paage is to manage the api modules, separate from web application routes to avoid conflict with.

> Services
  * it handle the website services

> storage directory
  - it holds and manage the storage files directory

> tests
  - test case of an application

> vendor
  - provides package files and resources.

> .env file
  * web application environment setup file, which contains

> composer.json file
  * packages information , PHP version, LAravel version, React packages

> server.php file
  * contains


## Routing


