# 🚀  fastapi-postgresql 🎉

Workshop Meterial for KFU-CODE.
A two days training session on Sunday & Monday Nov 26-27 2023 from 3-5 pm. 

Note: Please Download & Setup before the workshop.

## Setup & Run 🏃‍♂️

- Download and install Docker with compose

-   Setup and Build:

    set up a .env file with your configuration.  For a basic version for local testing use:  
    ```bash
    cp dot-env-template .env
    ```
    Be aware that .env is *excluded from git* because it contains secrets, API keys and so on.  **Never put your .env file into git.**

    Then build and start the test/debug stack with:
    ```bash
    docker-compose up --build
    ```

    Then:
    - Visit http://localhost:4000/docs for the interactive API docs (Swagger). For initial super-username and password to first authenticate see your **.env** file.
    - Modify your code, which is linked into the *fastapi-app* container and watch uvicorn auto-restart your app when changes have been made.
    - Run pytest in your container with `docker exec fastapi-app bash ./test.sh [optional parameters]`
    - Visit http://localhost:5050/ for the PostgreSQL administrator. Upon first use you'll need to register your DB server using your **.env** file.

## Features 🌈

1. **FastAPI Magic** - Because speed is not just about Fast & Furious movies!
2. **PostgreSQL Integration** - Store data like a pro. No more data loss nightmares!
3. **Docker Integration** - Set sail with a consistent environment. Because why let tech discrepancies ruin your day?

Base strucutre is taken from https://github.com/bibektimilsina000/FastAPI-PgStarterKit/tree/main

