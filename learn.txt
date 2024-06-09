What is inertia?
It is a glue backend with frontend

What is tinker? php artisan tinker
Commandline interface to interact with laravel
Example CL:
\App\Models\Project::count()

How to list all the routes?
php artisan route:list

=====DIRECTIVES======
@routes directive?
Responsible generate only registered route and make these route available to react component

@viteReactRefresh
Responsible for changes

@inertiaHead
Responsible to generate meta text

====DATABASE====
Steps for Database
1. php artisan make:Model name -fm (if want factory, migration)
2. Edit migration
3. Optional Factory if want to make fake data
4. DatabaseSeeder  -> if you want to factory
    For  DatabaseSeeder
      - create a factory for example
        Name::factory -> count(i)->hastask(i)create(); INSIDE function run()
5. Model time
    i. create relationship between the table

====CONTROLLER====
How to make controller?
  php artisan make:controller ProjectController --model=Project --requests --resource

  This tell that this controller is for the project model, it is a resource controler and accept request



======NOTES=======
php artisan migrate:refresh --Good for early stage bad if there teamwork and already commited and has been push

2. What ever you want to pass into the Controller (FOR INERTIA ONLY)
  - Recommended only to pass the data that you want to show only

3. Remember to create a relationship to Model
  public function AttributesName(){
    return $this->belongsTo(User::class,'name of the column')
  }

  Table A <- TableB(User)

  OR

  public function tasks(){
    return $this->hasMany(Task::class)
  }
  Table A -> Table B (Tasks)

4. Carefull on passes data to the frontend for REACT, however for Blade it automaticly dont pass data that dont use

5. Remember to add white space on className if using +
====WEB.PHP====
1.create all routes automaticly
  Route::resource('name',ControllerName::class);

  This will automaticly creates all CRUD routes


====INERTIA===
Inertia passes all the data from Props if using REACT
https://www.youtube.com/watch?v=VrQRa-afCAk&t=20027s ->1:02:27 explaination on this the (auth ) takes from the cotnroller


====RESOURCE===
How to create resource?
  php artisan make:resource NameResource

Why make resource??
  Notes#2 - it says that i need to specifically return data that you want to show only!

How to make return?
  In public function toArray
    return [
      'id'=> $this-> id
    ];

====CREATING A BADGE====
1. Refer constants.jsx
