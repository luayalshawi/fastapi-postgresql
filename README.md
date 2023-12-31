# 🚀  fastapi-postgresql 🎉

Workshop Material for KFU-CODE.
A two days training session on Sunday & Monday Nov 26-27 2023 from 3-5 pm. 

Note: Please Download & Setup all tools before the workshop.

## Setup & Run 🏃‍♂️
-   Download and install Docker with compose
https://www.docker.com/get-started/

-   VSCode 
https://code.visualstudio.com/download

-   Git & Git Bash in case on windows
https://git-scm.com/downloads

The containers are UNIX based and will load the project using host file systems.
Therore, we may need to make Git check out files with Unix-style file endings on Windows. Note this is only applicable on Windows

```
git config --global core.autocrlf false
```

- Clone the project using git
    ```
    git clone https://github.com/luayalshawi/fastapi-postgresql.git
    ```

    Navigate to the project directory
    ```
    cd fastapi-postgresql
    ```

-   Setup and Build:

    - Setup your local env file

        Either, by copying dot-env-template and renaming to .env

        or use the below command on bash terminal while in the project directory

        ```bash
        cp dot-env-template .env
        ```

    - Build and start the docker containers while in the project path:
        ```bash
        docker-compose up --build -d
        ```

    Then:
    - Visit http://localhost:4000/docs for the interactive API docs (Swagger). For initial super-username and password to first authenticate see your **.env** file.
    - Modify your code, which is linked into the *fastapi-app* container and watch uvicorn auto-restart your app when changes have been made.
    - Run pytest in your container with `docker exec fastapi-app bash ./test.sh [optional parameters]`
    - Visit http://localhost:5050/ for the PostgreSQL administrator. Upon first use you'll need to register your DB server using your **.env** file.


## Useful Commands
To get inside the container with a bash session you can start the stack with:
```
docker-compose up -d
```
and then exec inside the running container:
```
docker-compose exec fastapi-app bash
```
You should see an output like:
```
root@63a51b7acb4f:/app#
```

### Migrations
- If you created a new model in ./backend/app/app/models/, make sure to import it in ./backend/app/app/db/base.py, that Python module (base.py) that imports all the models will be used by Alembic.

- After changing a model (for example, adding a column), inside the container, create a revision, e.g.:

```
alembic revision --autogenerate -m "Add column last_name to User model"
```
- Commit to the git repository the files generated in the alembic directory.
- After creating the revision, run the migration in the database (this is what will actually change the database):
```
alembic upgrade head
```

## Features 🌈

1. **FastAPI Magic** - Because speed is not just about Fast & Furious movies!
2. **PostgreSQL Integration** - Store data like a pro. No more data loss nightmares!
3. **Docker Integration** - Set sail with a consistent environment. Because why let tech discrepancies ruin your day?

Based on 
https://github.com/bibektimilsina000/FastAPI-PgStarterKit/tree/main

And

https://github.com/tiangolo/full-stack-fastapi-postgresql
