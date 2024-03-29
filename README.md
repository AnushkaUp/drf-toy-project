# DRF Toy Project

The Django Rest Framework version of the Toy Project.

## Before Running the Project

### Clone the Repository

`$ git clone https://gitlab.com/mountblue/cohort-16-python/anushka_upadhyay/drf-toy-project.git`

### Create Virtual Environment and Activate it

`$ virtualenv env`

`$ source env/bin/activate`

Now, cd into the cloned repository

`$ cd drf-toy-project/`

Install the dependancies required

`$ pip3 install -r requirements.txt`

### Setting up the Database

`$ sudo -u postgres psql`

`postgres=# \i start.sql`

`postgres=# \q`

## Running the Project

Moving to the project directory

`$ cd django_rest_project`

Making the migrations

`$ python3 manage.py makemigrations`

`$ python3 manage.py migrate`

Creating the superuser

`$ python3 manage.py createsuperuser`

Now provide it with the credentials to login.

**Run the server**

`$ python3 manage.py runserver`

## Generating the token

**Step 1:** Open new tab in POSTMAN

**Step 2:** In a new tab, set the request to POST and write the url [http://localhost:8000/generate-token/](http://localhost:8000/generate-token/).

**Step 3:** Now follow the following steps:

* Click on Body.
* Click on form-data.
* First in key, write 'username', in value, write 'your username'.
* Second in key, write 'password', and in value, write 'your password'.

**Step 4.** Click Send.

Now, you will get the token in the Response section, in JSON form. You can copy the value of the token for authentication.

## Authentication

For the user authentication, we will use the token that we generated in last part.
  
**Step 1:** Open new tab in POSTMAN.

**Step 2:** Set the request to GET and write the url [http://localhost:8000/questions/](http://localhost:8000/questions/).

**Step 3:** Now follow the following steps:

* Click on Header.
* In key, write 'Authentication'.
* In value, write 'Token _copied token_'.

**Step 4:** Click Send.

This will authenticate you and give you the list of the questions(if any created).

## After running the project

**Closing the server.**

Closing the server by pressing Ctrl^C in the terminal.

**Deleting the database and the user.**

Now, opening postgres to drop the database and the user.

`$ sudo -u postgres psql`

`postgres=# \i drop.sql`

`postgres=# \q`

**Deactivating the virtual environment.**

`$ deactivate`

