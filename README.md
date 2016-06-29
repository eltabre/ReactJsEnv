# ReactJsEnv

## A quick and easy guid to making a ReactJs enviorment

###Getting the Correct software and setup

First things first, this guide will be using npm from the node.js so go download it here:
**https://nodejs.org/en/**

Second if you don't care about how everything is setup up and just want to start programming in React download this repo and then navigate in your command prompt to the file. (it should look something like C:\ReactJsEnv-master\ReactJsEnv) and do the following steps:
   
    1. npm install
    2. npm -g webpack webpack-dev-server babel-cli
    3. npm start 
    4. Navigate to http://localhost:3000/ and you should see "React enviorment is Working"

Now to start understanding the mirad of libraries that it takes to set up a reliable reactjs enviroment, lets go back to the first step. Node.js is a javascript runtime built on the Chrome V8 engine.  With Node.js installed you can now access a ton of open source libraries with the npm command.

    -For more on npm: https://www.npmjs.com/

Now after Node.js is installed go to your command prompt and make a directory.  You can name it whatever you like but for this tutorial I will call it reactjsenv.

    -mkdir reactjsenv
    -cd reactjsenv (change into the directory you just created)
    
Now run a command called *npm init*.  This command will prompt you with many questions you can just enter until the questions stop and then it will create a package.json file for you.  This package.json file will be criticle later.

###Installing the correct packages

Now that we have setup our package.json correctly now we have to download many different libraries using **npm**

    -npm install --save react react-dom babel-core babel-loader babel-preset-react babel-preset-es2015
    
A quick run down on what this command is doing: 

    1. npm install --save, or -s, will install and save all of the following libraries as dependincies
    in your package.json file. If you go check it out the pacakage.json you should see a dependancies: {} 
    with all of the libraires that we just installed!
    2. react and react-dom are Javascript libraries for building user interfaces that were open-sourced by 
    Facebook: https://facebook.github.io/react/index.html
    3. babel-core is the main complier for Babel.  Babel is a complier for Javascript that you will need. 
    more on Babel here: https://babeljs.io/
    4. babel-loader is a plugin to make babel work with webpack, a module bundler that we will be using. 
    5. babel-preset-es2015 and babel-preset-react are plugins for babel to make it work with ES6 and react

Next we have to install webpack and babel, but we are going to do this so globally so that you can make multiple react projects easily. 

    -npm install -g webpack webpack-dev-server babel-cli

This command installs these packages globally. 

###Making the files 
Now that we have installed all of the libraries where they need to be we can start making the files. 

      -touch index.html script.js webpack.config.js
      -mkdir build

These commands should make your "reactjsenv" directory mirror the directory that you will find the the master branch of this repository. So in each file that you made copy and paste the code from this repo into your files.  

###Explaing the Webpack file and polishing the package.json
      module.exports = {
         entry: './script.js',
         output: {
            path: __dirname + '/build',
            publicPath: '/build/',
            filename: 'bundle.js'
      },
      devServer: {
         inline: true, 
         port: 3000
      },
      module: {
      loaders: [
         {
            test: /\.js$/,
            exclude: /node_modules/,
            loader: 'babel',
            query: {
               presets: ['es2015', 'react']
             }
         }
         ]
         }
      }

The module.exports portion of this file is where webpack will enter to begin the bundling process.  The output consists of where webpack will go put the bundled file and what the file name will be.  Dev server is where we specify what port we want the server to be on and if we want to reload changes on the fly.  The last part tells webpack to look at all of the files ending in a .js but to skip the node_modules folder when it does that.  Then we tell webpack what loader it should use.  

Lastly, go into the package.json file and go to the portion that says scripts and delete the line that has been generated for you and insted put:
      -"start": "webpack-dev-server"
Now you should be able to start your server with the React.js enviorment by typing in npm start to your command prompt
