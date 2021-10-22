# setup-node-express-database for FAC server-side projects

# Setup

## Download a package and dependencies

```
npm install -D
```

## ESlint
```
npm install eslint --save-dev
```
```
npm init -y
```
```
npx eslint --init
```

ESlint Airbnb
```
npm info "eslint-config-airbnb-base@latest" peerDependencies
```

## Express

```
npm install express
```

## Cypress
```
npm install -D cypress
```

package.json
```
 "scripts": {
    "test": "cypress open"
  },
```

npm run test => cypress folder will be created.
  
## Nodemon
(for auto-restarting the server)

```
npm install -D nodemon 
```

package.json
```
    "dev": "nodemon -r -L dotenv/config server.js"
```

## Database

Enter the Postgres command-line interface
```
psql
```

Exit
```
ctrl+ d
```

Create a database
```
CREATE DATABASE database_name
```

List all the databases
```
\list
```
Connect the new database
```
\connect database_name
```
Run SQL directly from a file
```
\include init.sql
```

See all the database tables
```
\dt
```


### Database setup
Creating a local database
```
./scripts/create_db

```
Populating the database 
```
./scripts/populate_db

```

***A way for Node server toconnect to the database***
- Use pg library
/database/connection.js
```
const { Pool } = require("pg");

// DB URL should either be read from .env in development
// or set as part of production deployment (e.g. on Heroku)
if (!process.env.DATABASE_URL) {
  throw new Error("Missing DATABASE_URL env var");
}

// Connect to the database
// and create a pool of available connections to support simultaneous requests
const db = new Pool({
  connectionString: process.env.DATABASE_URL,
});

// export the pool object so we can query the DB in other files
module.exports = db;

```


## Cookie

### Reading a cookie with Express
is not coming with Express built-in - should separately install it

```
npm install cookie-parser
```

```
const cookieParser = require("cookie-parser");

server.use(cookieParser());
```

## Password security


bcrypt
```
npm install bcryptjs
```


## dotenv 
```
npm install dotenv

```

## PG

```
npm install pg
```


