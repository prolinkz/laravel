##

### Create Project
create project folder, enter into fordel and select the folder address bar and then write <code> cmd </code>  The command propmt will open.

Once the lab is ready to start work, we first need a project name (Directory to save project files). So first we run the Laravel then create a new project.

Run Laravel Globally via command <code> composer global require laravel/installer </code>  
composer create-project --prefer-dist laravel/laravel larainfo

Now write the artisan command to create a new project <code> laravel new project-name </code>

Enter into the project file via <code> cd project-name </code>

Run the Project via <code> php artisan serve </code> this will start the project to browse

### Step 2: Set Up Database Details in ENV
Now, you have to connect the laravel app to the database, hence open the <b> .env </b> configuration file and add the database credentials as suggested below.

.env file

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=database_name
DB_USERNAME=database_user_name
DB_PASSWORD=database_password
```

### Step 3: Install Laravel UI Package
The Bootstrap and Vue Scaffolding provided by Laravel is located in the <code> laravel/ui </code> Composer package, which may be installed using Composer; 
```
composer require laravel/ui
```
Once the <code> laravel/ui </code> package has been installed, you may installed the Scaffolding using the Artisan command;

### Step 4: Generate Basic Scaffolding...
use anyone for you requirements

```
php artisan ui bootstrap
php artisan ui vue
php artisan ui react
```


### Step 5: Step up Auth (login/registration) Scaffolding...
use anyone for you requirements

```
php artisan ui bootstrap --auth
php artisan ui vue --auth
php artisan ui react --auth
```

### Step 6: Run npm install && npm run dev command to compile fresh scaffolding
you need to install first node npm if you do not have node npm package then install first other wise Laravel mix not working .

```
npm install && npm run dev
```

### Step 7: Migrate your database
Next,run this command
```
php artisan migrate
```



#### lara

### Signin

### Register
