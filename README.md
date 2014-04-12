# Middleman on Heroku
### precompiled and served statically

## Usage

    git clone http://github.com/johnnycaja/middleman-heroku-static-app.git <project folder>
    cd <project folder>
    rm -rf .git
    bundle && bundle exec middleman init .
    git init . && git add .
    git commit -m "Middleman skeleton"
    git remote add heroku <heroku git url>
    git push heroku master

The only expectation is that `middleman build` will generate your site into `./build`. That's where Rack::TryStatic will look.

You can customize the 404 page that's served if TryStatic can't find a file by editing `source/404.html.erb`.

## To use Haml

    gem install html2haml
    cd <project folder>
    html2haml source/index.html.erb source/index.html.haml && rm source/index.html.erb
    html2haml source/layouts/layout.erb source/layouts/layout.haml && rm source/layouts/layout.erb
