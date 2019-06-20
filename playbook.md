
--- START VIDEO TUTORIAL DESIGNCOURSE ---  

First of this kit is based  on the video from Gary Simon :thumbsup: 

Check-out his website and youtube channel:  
[![YouTube Video][youtube-image]][youtube-url]

[youtube-url]: https://www.youtube.com/watch?v=TzdEpgONurw
[youtube-image]: https://i.ytimg.com/vi/TzdEpgONurw/hqdefault.jpg?sqp=-oaymwEjCPYBEIoBSFryq4qpAxUIARUAAAAAGAElAADIQj0AgKJDeAE=&rs=AOn4CLBWQljJT3lWgtfByvmllQGkLhpK3w

keywords  
    - bundler  
    - transpiling  
    - tree-shaking  
    - minification  
    - asset management  

- 1 npm init -y
- 2 npm i -D webpack webpack-cli  
- 3 edit packack.json
    - rm scripts : test
    - add build : webpack
- 4 test run build
    errors  : - no src folder
            : - no index.js file  (entry point)
- 5 add src folder && index.js file
- 6 test run again
    errors : none
    - dist folder was created
    - main.js was created (output file)
- 7 Create src/bro.js (example file)
- 8 Edit bro.js
- 9 Edit index.js
- 10 create index.html file
    - add html scaffolding
    - add script : index.js
    - run test in browser (F12) -> console
        -> error : SyntaxError: import declarations may only appear at top level of a module
        -> the import syntax is strange
- 11 Currently we are at a webpack 0 configuration
    - if we run the build - index.html does not get compiled
    - so we need to add configuration
- 12 Create webpack.config.js in the root of our proj.
    - before we can configure we need to install aditional devdependencies.
- 13 npm i -D html-webpack-plugin html-loader 
- 14 edit webpack.config.js 
        - instagate HtmlWebPackPlugin
        - create module.exports object
        - add Rules -> test: for html using the html-loader with some options
            - html-loader has 7 or 8 different options base ipon what we want todo.
        - next use the plugin HtmlWebPackPlugin
            - template is the entry directory
            - filenane is the output directory
- 15 run npm build
    - error : Module parse failed: Export 'bro' is not defined (4:9)    
    - run it again : -> error ->bro.js sysntax error 'constbro' => 'const bro'
    - run it agian : OK : ./dist/index.html exists.
    - and it is minified.
- 16 remove index.js script at the bottom of the index.html
    webpack has injected it and thus we don't need to import a second time
- 17 Next we are goint to install WebPack Dev Server
    npm i -D webpack-dev-server
- 18 Next edit package.json
    - add a new script: "start:dev": "webpack-dev-server"
    - so we name it anything we want does n't need to be "start:dev"
- 19 do a test run npm run start:dev
    - scroll up and find http://localhost:8080 link and click on it
    - next goto F12 -> console -> "Dude, bro"
- 20 Next test live reloading : 
    - modify bro.js
    - 'bro' -> 'sup'
    - check the browser console for the log.
    - stop server 
- 21 Next adding Babbel a javascript backwards compatblity compliler
    - npm i -D @babel/core babel-loader @babel/preset-env
- 22 Next mod: webpack.config.js
    - add new rule -> test any .js file, use babael-loader
- 23 Assets: 
    - new folder : src/images
    - find bg of a moutain on pexels.com
    - add an img tag to index.html
    - to handle file transfers during build we need to install a loader
    - npm i -D file-loader : no-errors : ok
    - add a new rule to handle the graphics.
    - run the dev build "npm run build"
    - error / not an error ?
- 24 Sass support: 
    - install packagaes
        - node-sass
        - style-loader
        - css-loader
        - sass-loader
        - mini-css-extract-plugin
        - npm i  -D .....
        -> done
    - create new folder : styles -> main.scss -> done
    - instead of adding it to index.html we're gonna import it into our index.js file ->import the path.
    - edit webpack.config file:
        - add role && plugin
        - npm run build -> OK : done
    - testing:
        -> index.js -> ctl+F -> blue
        -> reload apache browser => bg = blue
        -> start:dev => auto-reload with sass testing
            -change color to red  

--- END VIDEO TUTORIAL DESIGNCOURSE ---























