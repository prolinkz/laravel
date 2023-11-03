# laravel | Learning Laravel
[YT channel](https://www.youtube.com/watch?v=FQnhpuYldes&list=PLjVLYmrlmjGfh2rwJjrmKNHzGxCZwBsqj&index=4)
## Start
### Requirements
- Installation of *PHP Local Server* (XAMPP, WAMP)
- Installation of **Composer** [Composer](https://getcomposer.org/ )
- Installation of Laravel fremework [laravel](https://laravel.com/docs/8.x/installation#installation-via-composer)
- Installation of *Code Editor* (VS Code, Sublime, Notepad++)

### Create Project
Once the lab is ready to start work, we first need a project name (Directory to save project files). So first we run the __Laravel__ then create a new project.
- Run Laravel Globally via command  [laravel Globally](https://laravel.com/docs/8.x/installation#the-laravel-installer)
  - we aslco run the Laravel via composer, but the Globally helps in working from any path [laravel via composer](https://laravel.com/docs/8.x/installation#installation-via-composer)
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


