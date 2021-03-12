# adonisjs-template
This is a boiler plate for building nodejs/adonisjs api

# Requirements
- `npm >= 7.6.2`
- `node >= 15.11.0`
- the version of `adonis use is 5.0.4 preview`
without the above requirement, the app may not work
# Setup
- clone
- install dependencies: `npm install`
- create `.env` and save it at the root of the project
- copy the content of `env.example` into `.env`
  - set it up according to your credential
  - the app has been configured prior for MySQL/MariaDb, to change this and get credential for other databases
  - do `node ace invoke @adonisjs/lucid`
    - select a database
    - choose where you want to see the default credentail and instruction: preferebaly I used terminal
    - follow the instruction for your chosen database credential
- generate api: `node ace generate:key` 
  - copy the generated string into your `.env` and make it equal to or assign it to the key: `APP_KEY`
- Set up your database
- start the server with: `node ace serve --watch`
  - the server will start at: `localhost:3333`


# Resource | Routes
Users
- `localhost:3333/api/v1/users`
  - `/` method: Post Create user
  - request data
    ```
    {
      "email": "email@email.com"
      "password": "secret-password"
    }
    ```

  - response
    ```
    {
      "success": true,
      "message": "some message",
      "data": {
        "user": {*},
        "token": {*}
      }
    }
    ```

  - `/login` method: Post
    ```{ "token": "some-string "}```

  - `/logout` method: Post 
    - request Header: { "Application": "Bearer some-string-token-string" }
    ```
    {
      "success": true,
      "message": "logged out"
    }
    ```
