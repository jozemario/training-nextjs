# Training NextJS
NextJS Design Patterns and Module Federation


<details><summary>Tech Stack </summary>
<p>

#### Ecosystem:
```
NodeJs v.14.x
Express v4.16.0
Nodemon v2.0.19
Mysql v.2.17.0
Prisma v4.1.1
Jest": v28.1.3
Pino v6.14.0
```
</p></details>

<details><summary>Development</summary>
<p>

#### Setup repository
```
github clone git@github.com:jozemario/training-nextjs.git
cd training-nextjs/
git checkout dev
```
#### Setup project
```
# Install all the dependencies to run the apps in parallel.
run yarn 
# Install all the required dependencies on both host-app and remote-app
run npm run install:apps 
# Start both host-app and remote-app
run npm run start 

host-app on localhost:3000
remote-app on localhost:3001
Navigate to localhost:3000 
# Two Button Component should be visible, one from remote and another from host app
```
</p>
</details>

<details><summary>Project Structure</summary>
<p>

```
├── server.js        the entry point for starting the server (network configurations)
src/
  ├── app.js         Express(http-server) config
  ├── routes/        Express route handlers for all the endpoints of the app
  ├── middleware/    Middleware for the endpoints of the app
  ├── config/        Environment configurations
        ├── utils/   Common utils across app
  ├── services/      Service layer with the business logic
  ├── models/        Model layer with schemas
  ├── database/      Database schema with migrations and config
test/
  ├── integration/   All the integration tests of the app
├── package.json     Main project configuration file
├── ...              Others config files (.gitignore, etc)
```
</p>
</details>
