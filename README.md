# Daily Practice Coding

a small progress from daily practicing routine will make a big impact!    
52 weeks to be an expert fullstack software engineer!

## Programming Language

- How to create new Project?
- Naming Convention?
- Modularize Code?
- How to run developer mode (reload when changes occured)?
- How to get package from personal or private repository like github?
- How to use various data type?
    - how to check the data type?
    - (string) how to concate string?
    - (string) how to interpolate string?
    - (number) what is the maximum number?
- Conditionals
- Example concurrency?


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

### Naming Convention

#### Ruby
- constant -> CAPITAL_SNAKE_CASE

#### Python
- filename -> snake_case


### Modularize Code

#### Ruby

source:
- https://www.youtube.com/watch?v=Cq_dKYAqMrI
- https://ryanlue.com/posts/2017-03-03-how-to-structure-a-library

note:
- **_module_** is basically just a container where we can store groups of method

task:

create a file, `people.rb`, with the following contents

```rb
# frozen_string_literal: true

module Person
  module Ani
    AGE = 3
  end

  module Budi
    AGE = 3
  end

  module Tono
    AGE = 3
  end
end

puts Person::Ani::AGE
puts Person::Budi::AGE
puts Person::Tono::AGE
```



#### Python 

source: 
- https://realpython.com/absolute-vs-relative-python-imports/
- https://www.youtube.com/watch?v=e9yMYdnSlUA

note:
- **_module_** is an individual python file
- **_package_** is a directory containing multiple Python modules

task:

Open up your IDE and create these following structure

```
└── project
    ├── people
    │   ├── budi.py
    │   └── tono.py
    └── ani.py
    └── main.py
```

put age variable for each person, for example

```py
# budi.py
age = 5
```

```py
# tono.py
age = 9
```

```py
# ani.py
age = 3
```

use the package and module in the `main.py` and play around with it!

1. print ani age 
2. print budi age
3. use `__init__.py` to print something when importing package
4. use some importing syntax like: `import [package|module]` and `from package import [subpackage|module|object(class|function)] as [custom_name]`



### Example Simple Concurrency

print bip every 0.3 second and bop every 2 second

### Ruby

```rb
def print_bip(queue)
    loop do
        sleep(0.3)
        queue.push("bip")
    end
end

def print_bop(queue)
    loop do
        sleep(2)
        queue.push("bop")
    end
end

bip_queue = Queue.new
bop_queue = Queue.new

Thread.new { print_bip(bip_queue) }
Thread.new { print_bop(bop_queue) }

loop do 
    if bip_queue.size > 0 
        puts bip_queue.pop
    end
    if bop_queue.size > 0 
        puts bop_queue.pop
    end 
end
```


## DevOps




## FrontEnd