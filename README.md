# Using PostgreSQL on Linux (Ubuntu)

A guide for installing, setting up, and using PostgreSQL on Linux (Ubuntu).

# What is PostgreSQL

[PostgreSQL](https://www.postgresql.org/) is a Relational Database Management System **(RDBMS)** that enables you to organize, store, and manage data in structured objects with tables and allows relationships between these tables. 

## What You Should Know About PostgreSQL on Ubuntu

According to the official [PostgreSQL documentation](https://www.postgresql.org/download/linux/ubuntu/), PostgreSQL is by default available and supported by all Ubuntu versions. It is one of the reasons why I recommend using this RDBMS over any other open source (RDBMS) options on Ubuntu. Nonetheless, you may have your personal preference/favorite for different reasons.

## Installing PostgreSQL on Linux (Ubuntu)

Let's get to it, shall we? 

1. Open your terminal 

2. According to the official [PostgreSQL documentation](https://www.postgresql.org/download/linux/ubuntu/), you should run the following command:

    ```
    apt install postgresql
    ```

    - But you may run into a **Permission denied** error: 
    
        ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/644d8d1f-e5a7-4da2-9246-65cf05c9b8c0)

    - In that case, run the command as a superuser with `sudo`:
        ```
        sudo apt install postgresql
        ```

        ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/0a2ff42b-09d6-4161-b04c-1efcdc98d784)

3. Explore more ways to install postgreSQL on Ubuntu for automatic updates throughout the support lifetime of PostgreSQL in the official [PostgeSQL documentation](https://www.postgresql.org/download/linux/ubuntu/)

## Setting Up PostgreSQL

- To use PostgreSQL seamlessly, we will need to create a user.

### Creating a User on PostgreSQL

1. Switch to the **PostgreSQL Server** by running the following command on your terminal:

    ```
    sudo -i -u postgres
    ```
    ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/e2569a8a-9ac9-43b4-9423-165d68548c33)

2. To create a user with a password, run the following command **(also see option 3 below)**:

    ```
    createuser NameOfUserHere -P
    ```

    - Replace **NameOfUserHere** with your preferred name for the new user.
    - You will be prompted to enter a **password** for the new user and confirm it.
    - When you're done creating the new user, type `exit` and press `ENTER` to exit the **postgres** server.

        ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/e5faf676-23ea-434d-b6fe-70276235d6e3)

3. An alternative **(recommended)** approach is to use the --interactive flag.
    - Run the following command:

        ```
        createuser -P --interactive
        ```

    - This will prompt you to enter the following:
        - Name of the role/user you want to create
        - The password and password confirmation for this new user
        - Whether to assign a **superuser** role to this new user (recommended if you haven't created any other user)

    - When you're done creating the new user, type `exit` and press `ENTER` to exit the **postgres** server.

        ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/9856a932-59f0-441c-9f47-b828c03f6bf1)

### Creating a Database with PostgreSQL

After creating a user, you may proceed to create a database.

1. Run the following command to open a postgres shell:

    ```
    psql
    ```

    ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/484120cd-6590-466e-8cda-7580465b6bce)

2. Run the following command to create a new database

    ```
    CREATE DATABASE nameOfYourNewDb;
    ```

    - Replace **nameOfYourDb** with your preferred name for your database.
    - Please remember to add a semicolon `;` after each line.
    - When you've created your new database, type `\q` and press `ENTER` to exit the postgres shell.

        ![image](https://github.com/benie254/postgresql-on-linux/assets/99865051/aa6b2e15-b124-45f8-b916-bbcabf0e0103)

That's it! You've created your first database which you can use locally to store data.

## PostgreSQL Official Documentation

Check out the official [PostgreSQL documentation](https://www.postgresql.org/docs/) for more ways that you can use and interact with PostgreSQL.

## Using Your New PostgreSQL Database

Check out the following [guide]() to learn how to use your new database in a [Python- Django](https://www.djangoproject.com/) application.
