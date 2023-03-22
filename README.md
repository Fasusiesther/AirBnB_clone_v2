Description of the project
The AirBnB console is a python teamwork project by ALX(Holberton School Software Engineering program). This projects sum up my experience of using C programming and implementation of python tools for my five month of studies at the ALX fullstack software engineering program.

Description of the command interpreter
The goal of the project is to deploy a replica of the Airbnb Website using my server. The final version of this project will have A command interpreter to manipulate data without a visual interface, like a shell (for development and debugging). A website (front-end) with static and dynamic functionalities A comprehensive database to manage the backend functionalities An API that provides a communication interface between the front and backend of the system.

General concepts in review for this project task
As you navigate this code base, it is great to note the following concepts, while completing this project.

How to start and use AirBnB console with examples and functions
How to create a Python package How to create a command interpreter in Python using the cmd module What is Unit testing and how to implement it in a large project How to serialize and deserialize a Class How to write and read a JSON file. How to manage date time What is an UUID What is *args and how to use it What is *kwargs and how to use it * How to handle named arguments in a function

Files and Directories
The models directory will contain all classes used for the entire project. A class, called “model” in a OOP project is the representation of an object/instance. Tests directory will contain all unit tests. console.py file is the entry point of our command interpreter. models/base_model.py file is the base class of all our models. It contains common elements: attributes: id, created_at and updated_at methods: save() and to_json() models/engine directory will contain all storage classes (using the same prototype). For the moment I will have only one: file_storage.py. The project's implementation will happen in the following stages:

Stage One
The first phase is to manipulate a powerful storage system to give an abstraction between objects and how they are stored and persisted. To achieve this, I will: put in place a parent class (called BaseModel) to take care of the initialization, serialization and deserialization of my future instances create a simple flow of serialization/deserialization: Instance <-> Dictionary <-> JSON string <-> file create all classes used for AirBnB (User, State, City, Place…) that inherit from BaseModel create the first abstracted storage engine of the project: File storage. create all unittests to validate all our classes and storage engine Create a data model Manage (create, update, destroy, etc) objects via a console/command interpreter Store and persist objects to files (JSON files).

First, you create a specific database for it (next tasks). After, you have to remember what the purpose of an unittest?

“Assert a current state (objects/data/database), do an action, and validate this action changed (or not) the state of your objects/data/database”

For example, “you want to validate that the create State name="California" command in the console will add a new record in your table states in your database”, here steps for your unittest:

get the number of current records in the table states (my using a MySQLdb for example - but not SQLAlchemy (remember, you want to test if it works, so it’s better to isolate from the system))
execute the console command
get (again) the number of current records in the table states (same method, with MySQLdb)
if the difference is +1 => test passed

Update the def do_create(self, arg): function of your command interpreter (console.py) to allow for object creation with given parameters:

Command syntax: create <Class name> <param 1> <param 2> <param 3>...
Param syntax: <key name>=<value>
Value syntax:
String: "<value>" => starts with a double quote
any double quote inside the value must be escaped with a backslash \
all underscores _ must be replace by spaces . Example: You want to set the string My little house to the attribute name, your command line must be name="My_little_house"
Float: <unit>.<decimal> => contains a dot .
Integer: <number> => default case
If any parameter doesn’t fit with these requirements or can’t be recognized correctly by your program, it must be skipped

Write a script that prepares a MySQL server for the project:

A database hbnb_dev_db
A new user hbnb_dev (in localhost)
The password of hbnb_dev should be set to hbnb_dev_pwd
hbnb_dev should have all privileges on the database hbnb_dev_db (and only this database)
hbnb_dev should have SELECT privilege on the database performance_schema (and only this database)
If the database hbnb_dev_db or the user hbnb_dev already exists, your script should not fail

Authors black_nib
1. Fasusi Esther https://github.com/Fasusiesther
2. Ogunbowale Aderemi
