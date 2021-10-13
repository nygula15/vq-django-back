# VQ Backend

VQ Backend Project


- python 3.9, pip, virtualenv

## 1. Instructions for use and launch app.

1. Configure virtual environment settings

    1.1 Create virtual environment and activate it

    ```bash
    python venv -m venv
    source venv/bin/activate
    ```
    1.2 Install required libraries

    ```bash
    pip install requirements.txt
    ```
2. Install [mysql](https://www.digitalocean.com/community/tutorials/mysql-ubuntu-18-04-ru) and create database

    Connect to the mysql server

    ```bash
    sudo mysql
    ```
    Create database with user in the shell

    ```bash
    CREATE DATABASE vq_dev;
    CREATE USER 'vq_admin'@'localhost' IDENTIFIED BY 'vq_admin';
    GRANT ALL PRIVILEGES ON vq_admin.* TO 'vq_admin'@'localhost';
    FLUSH PRIVILEGES;
    quit
    ```

3. Migrate with database
    ```bash
    ./manage.py migrate
    ```

4. Create super user to view all data from admin panel

    ```bash
    ./manage.py createsuperuser
    ```

5. Run the server

    ```bash
    ./manage.py runserver
    ```
