The following is a sample ruby on rails application deployed on Heroku with a postgresql database on the backend. Steps involved in creating this application:

```
rails new rails_heroku -d postgresql -c tailwind
```

This creates a new rails application with postgresql for the backend, and tailwind CSS for the frontend UI. Enter the directory using:

```
cd rails_heroku/
```
Migrate the database using:

```
bin/rails db:migrate
```

After this, setup the database:
```
rails db:setup
```

Create a scaffold to test if the database is running on the backend:
```
rails generate scaffold User name:string email:string
```
Git add and commit the repository. Initiate heroku and then create an heroku app using:
```
heroku creare app-name
```

Add the postgresql add-on to the heroku database. Check if the postgresql add-on is working using:
```
heroku apps:info
```

After this, migrate the db to the postgresql database provided by heroku:

```
heroku run rake db:migrate -a rails-heroku
```

After all these steps, push the application to heroku:

```
git push heroku main
```




