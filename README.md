# README
Docker template that runs on M1 Mac and Intel Mac.

Version
```
Ruby 3.0.2
Rails 6.1.4
MySQL 5.7
```

## Usage

### 1. Get template

```bash
$ mkdir YOUR_REPOSITORY_NAME
$ cd YOUR_REPOSITORY_NAME
$  .
```

### 2. Rails new

```bash
$ docker-compose run app rails new . --force --database=mysql
```

### 3. Edit database.yml

Edit username and password you set in docker-compose.yml

```bash
default: &default
  adapter: mysql2
  encoding: utf8mb4
  pool: <%= ENV.fetch("RAILS_MAX_THREADS") { 5 } %>
  username: root
  password: password
  host: db
```

### 4. Build docker-image
```
$ docker-compose build
```

### 5. Create database

```bash
$ docker-compose run app rails db:create
```

### 4. Start the Docker container
```
$ docker-compose up
```


## Commands

### docker-compose run --rm app bash

```
$ app-container
```

## REFERENCE
https://norix.tokyo/environment/443/