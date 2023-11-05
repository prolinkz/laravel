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

### File Structue
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


## PHP Artisan Commands
- To check all the artisan command , write <code> php artisan </code>
- If we only check the specific tyype command, like Route commands, then <code> php artisan route -h </code>. This will show all the route commands
- To run the avialable command for Route list <code> php artisan route:list</code>
- The above route list will show all the system packages routes and custom routes list. To avoid the packages routes run <code> php artisan route:list --except-vendor </code> it will only show our routes
- To check particular Route, like to only show Post route we used  <code> php artisan route:list -path=post </code>


## Route Parameters
[YT](https://www.youtube.com/watch?v=ywGqCuM-vek)  [Route Parameters](https://www.youtube.com/watch?v=ywGqCuM-vek&list=PL0b6OzIxLPbz7JK_YYrRJ1KxlGG4diZHJ&index=6) 
-
-  ![image](https://github.com/prolinkz/laravel/assets/45316278/ed87cd14-c919-416e-ae90-7419d02bb0ad)
- 

## Controllers
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

## Model - Migrate
### Work with Database (MySQL)
- In MySQL we perform functions like ;
  1. Create Database
  2. Create Tables in DB (Column name, Datatype)
  3. Insert data in tables
  4. Code with data tables

- Steps to Work with Mode
  Similarly in Laravel the Model performs some functionalities like;
  1. Create Database
  2. Create Database Migration (Create Tables in database)
  3. Seeding (Insert initial data in tables)
  ![Steps to Work with Model](https://github.com/prolinkz/laravel/assets/45316278/687b3826-0dee-4585-a4c4-aaa81a66467c)

The database configuration controll by .env file having variables of db name, server name, port, password
  ![.env file](https://github.com/prolinkz/laravel/assets/45316278/298076ef-5829-439b-a3ff-7bbd95b0f826)
  Once the variable are set, these are controlled and managed from Config>databse.php file.
  
Laravel support 4 types of database which are MySQL, SQLlite, pgsql, and SQLServer which are located at Config>databse.php
The default connection is on start of page, like here MySQL
  ![Default Databse Connection](https://github.com/prolinkz/laravel/assets/45316278/9060c14d-cc7d-49da-882f-3ac57eb4e302)


### Create Database:
We can create database from localhost/phpmyadmin o rdirect through laravel Migration command 


### Create  Table
Similarly to the dtabase, we can create table thorugh XMPP phpmyadmin or through schema command using table_name and columns with name and their datatypes
  ![Migratation - create table](https://github.com/prolinkz/laravel/assets/45316278/749a145e-1215-4209-89ba-6afc83799c8b)

```
php artisan make:migration create_students_table
```
the above command will create table 'students_table' and migration file under migration directory. 
The defalut colums would be id,, and timestamp. we can add/update, like below

```
schema::create(table_name, function(blueprint,$table))
  $table->id();
  $table->string('name',30);
  $table->string('city',20);
```
Blueprint is the classs of Migration which control all the databse funtions and data types like it convert Varchar of MySQL convert into String. Once we create table using command Run 'migrate' command to creaet table in database.
  ![image](https://github.com/prolinkz/laravel/assets/45316278/966fbf34-bf23-4075-8c63-0900f2205799)

Once we complete table , we would need to run migrate command to update entries in database
```
php artisan migrate
```

We can check all the migrated tables through
```
php artisan migrate:status
```

#### create another table 'Users'
```
php artisan make:migration create_users_table
```
add/edit columns and run migrate command to update MySQL
```
php artisan migrate
```
we can check the migration status to check tables are creted or not
```
php artisan migrate:status
```

#### How to Undo the Table migration

1. The first method for undo/delete the table is Rollback. it will delete last migrate like it will delete the Users table which is create at very last.
  ```
  php artisan migrate:rollback
  ```
  1.1 the **Rollback** commands consists two flags which are step, which means to delete last 3 scommands affects
  ```
  php artisan migrate:rollback --step=3
  ```
  1.2 the Rollback commands flag **--batch** which is used remove particular command. . like to remove only last 3rd command 
  ```
  php artisan migrate:rollback --batch=3  
  ```
  
2. The second method command is **reset** which remove all tables which are ceated using migrations
  ```
  php artisan migrate:reset
  ```

**Refresh:** The below command will refresh , it will roleback all table and create again fresh tables
  ```
  php artisan migrate:refresh
  ```

**Fresh:** It will not refresh/rollback , but remove all table and create freah tables
  ```
  php artisan migrate:fresh
  ```
  - Both Fresh and Refresh do same work.

#### How to crete Model and Migrate files at once
  ```
  php artisan make:model Task -m
  ```
it will create Model and Task task table. We can check Model in __app>Model folder__ and Migrate file in __database>Migrations file__


#### Data Types used in Laravel
##### Migration Data types
SQL data types and Laravel data types are same but only changes names for datatypes  [Data types](https://laravel.com/docs/10.x/migrations)

#### Migration Review 
![image](https://github.com/prolinkz/laravel/assets/45316278/f77efe46-1378-4dcf-bc61-d86094cf4f58)



### Migration Modifiers & Constraints
#### Modification in Migration tables 
[YT](https://www.youtube.com/watch?v=VHf5alNBLjI)
- Column Modification: add/ edit/ delete/change column order or datatypes or it size
- Table Modification  : rename table/delete table

- Add Column with Migration 
  ```
  php artisan make:migration update_students_table --table=students
  ```

![image](https://github.com/prolinkz/laravel/assets/45316278/a319ba93-deac-43f1-83af-5f49dfe7979a)

3 steps to update table
![image](https://github.com/prolinkz/laravel/assets/45316278/9dad9d4c-83a4-4d9c-8737-67e34f996f49)


#### Column Rename, delete, size update
- Rename Column: $table->renameColumn('from','to');
- Drop Column: $table->dropColumn('city');
- Drop Multiple Columns:  $table->dropColumn(['city', 'Tel', 'contact']);
- Change Data type size: $table->string('name',50)->change();
- ![image](https://github.com/prolinkz/laravel/assets/45316278/1762f985-bb17-4b56-b395-bbcfec96677a)


#### Change Column Order
Cretae 2 new columns 'address' and 'city' **after** password column, we will use **after()** function
![image](https://github.com/prolinkz/laravel/assets/45316278/cccbc02d-c7c5-4570-b9ad-bdc01bb617b3)

#### Keep Column default value
  $table->string('city',20)->default('No City')->change();
  ![image](https://github.com/prolinkz/laravel/assets/45316278/f431086e-ca59-41ce-a089-fc50c5f4c445)


#### Schema 
#### Check Schema Table or Column 'ifExist', hasTable, hasColumn
![image](https://github.com/prolinkz/laravel/assets/45316278/dc28722a-92fc-4ec5-9c05-e52b9ecb2721)

![image](https://github.com/prolinkz/laravel/assets/45316278/3b88abf6-f3b7-4619-bc66-34b80f30c385)

#### Constraints - Restrictions
![image](https://github.com/prolinkz/laravel/assets/45316278/bd48dc20-8196-42e8-9844-c388b21fe172)

![image](https://github.com/prolinkz/laravel/assets/45316278/d92a136f-b848-4e2a-b582-79eab901d721)

![image](https://github.com/prolinkz/laravel/assets/45316278/a0d74f4d-4fa1-45fc-9c37-60c1011f1b5b) 


Some of other Laravel Column Modifier 
![image](https://github.com/prolinkz/laravel/assets/45316278/afbad5a3-69c1-4f9b-a4db-217accb759de)


## Migration Primary & Foreign key

[YT](https://www.youtube.com/watch?v=FM70Ssh0bMc)

PRimary key data type should be Interger or Double, and AUTO Increment
![image](https://github.com/prolinkz/laravel/assets/45316278/48021919-c466-42b2-900b-ed00aa8e7c15)
![image](https://github.com/prolinkz/laravel/assets/45316278/7112ec8b-6286-4099-9e20-3df3035933a4)

![image](https://github.com/prolinkz/laravel/assets/45316278/0b0a813d-35d2-494e-934a-a19eadb88441)

### Foriegn Key Cascade
We we update or delete the Parent table id it will not work because it connect with some foriegn key, so the aravel contains 'Cascade' function for Update or Delete 
![image](https://github.com/prolinkz/laravel/assets/45316278/dd2623f1-c237-4002-ad71-392a2fdbd25a)
Practical entry
![image](https://github.com/prolinkz/laravel/assets/45316278/b34ece67-8132-43ab-ba59-9fd20b4508cb)


#### Restrict
Restriction is by default, means values of Foriengn key doen't change but we clso can use 'restrict' . like on update we use cascade and for deletre we use restrict.


![image](https://github.com/prolinkz/laravel/assets/45316278/b3fe30f3-b51e-44c7-aeae-1f7b24cc58a2)


![image](https://github.com/prolinkz/laravel/assets/45316278/65ec77c5-5f23-4356-bdda-589c311bc839)



