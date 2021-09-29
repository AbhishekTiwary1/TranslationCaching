  ## Introduction and Goal 

A web server with a RESTful API that exposes an API that translate a text from one language to another.

## Tasks Performed
 * Created a web server with a **RESTful API using NodeJS** to translate a text from one language to another using [google-traslate-api](https://www.npmjs.com/package/@vitalets/google-translate-api)
 * Target Language is **defined by user** and can be requested by API
 * **Caching** of data is done to avoid repeated hits to the translation API using [redis](https://redis.io/)
 * Server implemented with **extensible architecture** for switching caching startegy or switching translation service.
 * Wrote **Tests** to test the APIs using [mocha](https://mochajs.org/) and [chai](https://www.chaijs.com/)
 * **Linting** of code is done using [ESLint](https://eslint.org/docs/user-guide/getting-started)


 ## Motivation behind using `redis` for caching


 | Redis    | RDBMS           | 
| ------- | --------------- |
| Redis stores everything in primary memory.   | RDBMS stores everything in secondary memory.          |
| In Redis, Read and Write operations are extremely fast because of storing data in primary memory.     | In RDBMS, Read and Write operations are slow because of storing data in secondary memory.   |

>  ## Tech Stacks Used
- `NodeJS` and `ExpressJS`(NodeJS based application framework)
- `Google Translate` npm package as an external service for actual translation
- `redis` used as database cache.
- `Mocha and Chai` as testing framework
- `ESLint` for code analysis

## Run it locally:computer:

1. Install [NodeJS](https://nodejs.org/en/):arrow_double_down:
2. Download [Redis](https://github.com/dmajkic/redis/downloads) and open the `redis-server` file for starting the server (neccesary to run the app)
3. Open the terminal window and write
```
git clone https://github.com/AbhishekTiwary1/TranslationCaching.git

```


4. Install Dependencies

```
npm install
```
This will download all the node modules to your local computer.

5. Next thing to write on terminal is
```
npm start
```
This will run the software on port `3000`

6. You are ready to go to [localhost:3000](http://localhost:3000/) on your browser and enjoy the traslation caching. 

## Testing Code
Run 

```
npn test
```
Make sure the server file is not already running only the redis server should run
and the test written in `test\task.js` will run using mocha

> ESlint Configuratin file can be found in `.eslintrc.js`


## Database Schema

Key is taken as `Input text + desired languae Iso code` as string
The value returned from the translation Api is stored in value.

| Key | Value |
|----| ---|
|Happyhi| प्रसन्न |
|Hellofr | Bonjour | 

