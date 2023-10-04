# Sample 1: Sinatra

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

