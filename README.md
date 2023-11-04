# laravel | Learning Laravel
[YT channel](https://www.youtube.com/watch?v=FQnhpuYldes&list=PLjVLYmrlmjGfh2rwJjrmKNHzGxCZwBsqj&index=4)
[Baba YT](https://www.youtube.com/watch?v=-yFJh8CavLI&list=PL0b6OzIxLPbz7JK_YYrRJ1KxlGG4diZHJ&index=4)

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
##### Basic Folders are;
- Model -> Database/ sQL queries handlling
- Controller -> Business Logics Files
- View -> HTML files
- Routing -> URL/path Defining files 
- Assets (Public Folder) -> Images, Fonts, Audio/Videos, Files, CSS/JavaScript

##### File Structue
  > app
      - Kernal.php (
      - Custom Handler
  
  >> HHTP (Important MVC
        * Controllers (Handle all Controllers here)
        * MidleWare ( provide security feature, Authentication)
        * Modules (Users information)
        * Providers (Services Providers)
  
  > Bootstrap
    * its not a CSS desineing purpose, but it is used to speedup the application. It will cache the directory path to run smoothly
  
  > config
      * configuration 
  
  > databse
    * migration (handles database management)
    * seeders ( fake data creation)
  
  > public
     * index.php is the file to strat.  here all the __CSS__ and _JS_ source files exists.
  
  > Routes
    * **web.php** will contians the path routes to the web pages to browse from > resousces directory > views> webpage.blad.php
    * **channel.php** ( this page for creating and managing broadcasting
    * **api.php** (this paage is to manage the api modules, separate from web application routes to avoid conflict with.
    * Routes plays MV role in MVC structure. we create Modle here for Views
    * ![Laravel Route](https://github.com/prolinkz/laravel/assets/45316278/be13a323-95b3-4505-af5c-b8401c8678ba)
  
  ```
  Route::get('/', function(){
    return view('welcome');
  });
  ```

  
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


```
Route::get('/', function(){
  return view('welcome');
});
```

create a new route for a new web page post.blade.php
```
Route::get('/post', function(){
  return view('post');
});
```

We can create route in sigle line to call view method instead of __get()__ method to post blade with '/post' route.
```
Route::view('post', '/post');
});
```
we can create any name for route to the view. like we create /hello route to the post page view
```
Route::get('/hello', function(){
  return view('post');
});
```
route from blade view pages
```
<a href=""> Post Page </a>
```

Route to sub-page 
```
Route::get('/post/firstpost', function(){
  return view('first-post');
});
```

Routing based testing
- Open page inspect > Network > refresh page, you will see the tabs > Headers, Network, Responce 


#### PHP Artisan Commands
- To check all the artisan command , write <code> php artisan </code>
- If we only check the specific tyype command, like Route commands, then <code> php artisan route -h </code>. This will show all the route commands
- To run the avialable command for Route list <code> php artisan route:list</code>
- The above route list will show all the system packages routes and custom routes list. To avoid the packages routes run <code> php artisan route:list --except-vendor </code> it will only show our routes
- To check particular Route, like to only show Post route we used  <code> php artisan route:list -path=post </code>


#### Route Parameters
[YT](https://www.youtube.com/watch?v=ywGqCuM-vek)  [Route Parameters](https://www.youtube.com/watch?v=ywGqCuM-vek&list=PL0b6OzIxLPbz7JK_YYrRJ1KxlGG4diZHJ&index=6) 
-
-  ![image](https://github.com/prolinkz/laravel/assets/45316278/ed87cd14-c919-416e-ae90-7419d02bb0ad)
- 

### Controllers
Controllers are 
- To create a controller . here we are creating PagesController controller to manage all pages. First create a Pages folder under View folder, open in cmd and write
```
php artisan make:controller PagesController
```

- Now browse the project directory ** > app > Http > Controllers > here the PagesController.php will added **
Open this page, and write 
```
class PagesController extends Controller
{
  public function index(){
    return view('pages.index');
  }
  public function about(){
    return view('pages.about');
  }
}
```
- Also create an index page under **Resources > Views > pages** named index.blade.php and add some html code to it.

- Now to access the pages, set the routes
  ```
  Route::get('/','PagesController@index');
   Route::get('/about','PagesController@about');
  
  ```




