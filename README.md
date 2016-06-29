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

    1. npm install --save, or -s, will install and save all of the following libraries as dependincies in your package.json file. If you go check it out the pacakage.json you should see a dependancies: {} with all of the libraires that we just installed!
    2. 
