---
title: Installation
layout:  null
tab: true
order: 1
tags: cervantes
---

# Try Cervantes

There is a live demo running on [http://demo.cervantessec.org](http://demo.cervantessec.org).

The demo server has 3 users to show the different permission levels. The credentials for these users are:

| Username              | Password      | Role          |
|-----------------------|---------------|---------------|
| admin@cervantes.local | Admin123.     | Administrator |
| su@cervantes.local    | SuperUser123. | SuperUser     |
| user@cervantes.local  | User123.      | User          |


## Runtime requirements

- Docker
- Docker compose

## How to run it locally with Docker compose

1. First you need to clone this repository

```sh
git clone https://github.com/CervantesSec/docker.git
```

2. After that you need to start your docker containers:

```sh
docker-compose -p cervantes -f docker-compose.yml up -d
```

3. After this, open your browser at http://localhost


4. Default User is:

```sh
admin@cervantes.local - Admin123.
```

## How to run it locally from source
1. Install dotnet sdk from https://dotnet.microsoft.com/en-us/download


2. Install PostgreSQL https://www.postgresql.org/download/ 


3. Clone this repository

```sh
git clone https://github.com/CervantesSec/cervantes.git
```

4. In Cervantes.Web -> appsettings.json edit the DefaultConnection with your database parameters

```sh
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=localhost;Database=cervantes;Username=postgres;Password=postgres"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Trace",
      "Microsoft": "Warning",
      "Microsoft.Hosting.Lifetime": "Information",
      "Cervantes.*": "Trace"
    }
  },
  "AllowedHosts": "*",
  "EmailConfiguration": {
    "Enabled": false,
    "Name": "Cervantes",
    "From": "cervantes@cervantes.local",
    "SmtpServer": "localhost",
    "SmtpPort": 1025,
    "SmtpUsername": "cervantes@cervantes.local",
    "SmtpPassword": "cervantes"
  },
  "JiraConfiguration": {
    "Enabled": false,
    "Auth": "Basic",
    "Url": "",
    "Project": "",
    "User": "",
    "Password": "",
    "ConsumerKey": "",
    "ConsumerSecret": "",
    "OAuthAccessToken": "",
    "OAuthTokenSecret": ""
    
  }
}
```

6. Run the project 

```sh
dotnet run --project /CERVANTES_PATH/Cervantes.Web/
```

7. After this, open your browser at http://localhost:5001


8. Default User is:

```sh
admin@cervantes.local - Admin123.
```
