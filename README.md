# QT21-Scorecard

http://www.qt21.eu/scorecard

## Installation Instructions

The installation instructions are targeted to users who know how to install a PHP application on a webserver. We assume that you have already installed

* A webserver with PHP and MySQL support (e.g. Apache Webserver)
* A MySQL server with one database
* Git

The example command line calls are written for Linux / Mac users. The process can be easily adapted to Windows systems.

### Download sourcecodes

```
git clone https://github.com/multidimensionalquality/qt21-scorecard.git
```

### Deploy Symfony 2 Application

The QT21 Scorecard was created using the Symfony Framework. To deploy it on a webserver you must follow the [official documentation of Symfony 2](http://symfony.com/doc/current/cookbook/deployment/tools.html
).

### Create database and add database settings

We assume you have already created a MySQL database. Create a new parameters file for your application:

```
cp app/config/parameters.yml.dist app/config/parameters.yml
```

And put your database settings (host, user, password, database) in `app/config/parameters.yml`.

Initialize the database with the following command:

```
php app/console doctrine:schema:update --force
```

Now you have to run the MySQL commands defined in `data/issues.sql` on your database.

### Create super user

* Register user via normal scorecard registration form. Then run the following command to promote this user to a super user:

```
php app/console scorecard:promote-superuser <<username>>
```


## License

Copyright 2015 Deutsches Forschungszentrum für Künstliche Intelligenz

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

