# **LouieBot-backend**

## **What is LouieBot?**

LouieBot is an open source, simple, free and easy to use Song Request twitch bot. LouieBot Client(s) is written in TypeScript while the backend is written in Go for fast API calls.

### **Setting Up your Enviroment**

[backend](#backend) | [bot-website](https://github.com/Louuie/LouieBot) | [twitch-bot](https://github.com/Louuie/LouieBot)

---

## Backend

---

### Docker

Docker is required for this project to setup a local Postgres database. We use the database to store our song request. Please follow the following steps below to setup your local Docker container.

- First, create a docker container using the following command in the terminal.

    ``` docker
    docker run --name some-docker-name -e POSTGRES_PASSWORD=some-secret-password -d postgres
    ```

- After we have created the Docker container, start the container if you haven't already.

- Once the container has been started, we should be able to connect to it using some sort of Postgres DB tool of your choice.

### Enviroment Variables

- After successfully setting up your local docker container, the next step is to setup your enviroment variables.

- Since in Go environment variables aren't based of a file rather they are based off of the operating systems own enviroment. Meaning we must set the environment variables in either our .bashrc or .zshrc.

- The list of the required environment variables can be found below.

    |  variable | value |
    |---|---|
    |  TWITCH_CLIENT_ID | Twitch Application CLIENT_ID   |
    |  TWITCH_CLIENT_SECRET | Twitch Application CLEINT_SECRET  |  
    |  GOOGLE_API_KEY | Google Application API_KEY (most have YouTube API Enabled for the key to work) |
    | POSTGRES_CONN | postgresql://postgres-name:postgrespassword@localhost:port/table-name?sslmode=disable |
    | UNIT_TESTING_AUTH_CODE | ***(ONLY USE FOR UNIT TESTING! THIS IS NOT THE ACCESS_TOKEN, THIS IS THE CODE YOU USE TO AUTHENTICATE THE USER)*** twitch auth code  |

### Starting the Server

Once you have completed all the steps above, you can finally start the Fiber server. To do so Cd into the LouieBot-backend directory if you haven't already.

``` zsh
Cd LouieBot-backend/
```

Then you can simply start the server by running the following command into t
