# heroku-buildpack-multi

Use multiple buildpacks on your app

## Usage

    $ heroku config:add BUILDPACK_URL=https://github.com/MrMarvin/heroku-buildpack-multi.git

    $ cat .buildpacks
    https://github.com/heroku/heroku-buildpack-nodejs.git#versions
    https://github.com/heroku/heroku-buildpack-ruby.git
                                                                  
    $ cat .release
    ---
    config_vars:
        PATH: vendor/bundle/ruby/1.9.1/bin:/app/bin:/usr/local/bin:/usr/bin:/bin
        LUA_CPATH: ./?.so;/app/packages/lib/lua/5.1/?.so
        LUA_PATH: ./?.lua;/app/packages/share/lua/5.1/?.lua;/app/packages/share/lua/5.1/?/init.lua
        GEM_PATH: vendor/bundle/ruby/1.9.1
        RACK_ENV: production
        LANG: en_US.UTF-8