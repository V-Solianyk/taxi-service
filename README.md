<h1 style="font-size: 42px;">Taxi Service</h1>

# Summary
This project is a "Taxi service" - a web application to show simple CRUD operations, authentication, and registration using MySQL and servlets, without any frameworks.
# Description of functionality
- registration like a driver
- authentication like a driver
- create/update/remove a driver
- create/update/remove a country
- create/update/remove a manufacturer
- adding a driver to a car
- display a list of cars by a specific driver
- display a list of all drivers/countries/manufacturers
# Used technologies
Maven, Java programming language (JDK 17), JDBC, Java Servlet, JSP and HTML, Tomcat 9.0.50, MySQL 8.0.
# Project structure
This project is designed to meet the standards of multi-level architecture. Therefore, the project is divided into the following levels:
- representation: it is a package of controllers for each model separately (car, country, driver) and, accordingly, for each entity there are several controllers, each of which is responsible for one function;
- the level of work with the database (DAO layer) is a set of interfaces and their implementations for each individual entity;
- service level that describes the business logic of the web application. It consists of a set of interfaces and their implementations for each individual entity (car, country, driver), as well as the logic for authenticating a new user (driver);
- "lib" package contains the implementation of the necessary annotations (@Inject, @Service, @Dao) and the implementation of the injector;
- "util" package contains a class that is responsible for providing a connection to the MySQL database in the project. It uses JDBC (Java Database Connectivity) to create a connection to the database;
- "web.filer" package contains a class that is an authentication filter for the taxi service web application. It is used to control access to different URLs and to check user authentication;
- "resources" directory contains a file with the necessary script to initialize the database with the necessary tables and their relationships;
- "webapp" directory contains a hierarchy of packages for each model separately, where JSP pages are located for each request. This directory also contains web.xml - this file is responsible for the configuration of the web application. It defines the settings of servlets, filters, and URL mappings used in the taxi service web application;
- checkstyle.xml - is a configuration file for the checkstyle tool, which is used to check the code style. It contains settings for various checkstyle modules that perform various code checks for compliance with style standards;
- pom.xml - used to configure and create a Maven project, add the necessary dependencies.
# Instructions for launching the project
In order to launch this project, you need to take the following steps:
- clone this project to yourself locally;
- install the Tomcat servlet container version 9.0.50, DBMS MySQL version 8.0, and the IntelliJ IDEA to run the application;
- open this project through the IDE and in the resources directory there is a file with the necessary script to initialize the tables in the database, copy the content of this file;
- create a database, assign a username and password, and then paste the script to create the necessary tables;
- there is a class in the "util" package, and you need to write the configuration data from the database (URL, username, password) into it;
- next, you need to connect Tomcat to the project to do this, go to "Edit Configuration", select the Tomcat version in the "Application Server" that was installed and unzipped beforehand, also in the Tomcat server configuration you need to specify the start page that will be displayed when the application starts (select war exploded and delete all unnecessary characters before the "/" sign;
- after that, we can start the application by clicking the Run button (both in normal mode and in debug mode can be run) and if everything is done correctly, the server will start.