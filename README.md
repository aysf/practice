# Daily Practice Coding

a small progress from daily practicing routine will make big impact...     
52 weeks to be fullstack software engineer!

## Programming Language

- How to create new Project?
- How to run developer mode (reload when changes occured)?
- How to get package from personal or private repository like github?
- How to use various data type?
    - how to check the data type?
    - (string) how to concate string?
    - (string) how to interpolate string?
    - (number) what is the maximum number?


### How to Create new project

#### Ruby

- create `Gemfile` file. create manually or by running `bundle init`
- put line `gem "sinatra"` to the file
- run `bundle i` to install the package
- create new file `app.rb` and put these lines
    ```rb
    require 'sinatra'

    get '/' do
        'Sinatra Rocks!!!'
    end
    ```
- run `ruby app.rb` and follow the instruction

#### Node

- create `package.json` file manually or automatically by running `npm init`
- put these lines to the file
    ```js
    {
    "name": "node-app",
    "private": true
    }
    ```
- run `npm install @hapi/hapi` to add hapi package 
- create `app.js` file and put these lines 
    ```js
    'use strict';

    import { server as _server } from '@hapi/hapi';

    const init = async () => {

        const server = _server({
            port: 3000,
            host: 'localhost'
        });

        server.route({
            method: 'GET',
            path: '/',
            handler: (request, h) => {
                return 'Hello Budy';
            }
        })

        await server.start();
        console.log('Server running on %s', server.info.uri);
    };

    process.on('unhandledRejection', (err) => {

        console.log(err);
        process.exit(1);
    });

    init();
    ```
- run `node app.js`




## DevOps




## FrontEnd