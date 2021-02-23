# webpack-w-paper-demo

Getting started with paper.js and webpack
=========================================

I'd like to create some browser applications that let the user play around with vector graphics.
[Paper.js](http://paperjs.org/) appears to suit my needs perfectly.

The apps must be self-contained: ideally, the user can just unpack the files, point their browser at them and use the application, even when offline.
So paper.js, and any other dependencies, must be bundled with releases. [Webpack](https://webpack.js.org/) can do this, but it doesn't support paperscript out of the box.

This project documents my attempts to make it work.
I'm new to modern JavaScript, _npm_, _paper.js_ and _webpack_, so this is a novice playing with newfound toys.
The configuration after [the first commit](https://github.com/reinierpost/webpack-w-paper-demo/tree/b1f0ec94b6225d882e0754dc0816eba670070164) hurts the eyes, but it works for me.
Future commits will try a bunch of improvements, such as a [paper loader](https://github.com/aprowe/paper-loader).

Setting up
----------  
This is what I did on an Ubuntu 18.04 host.

- This app uses npm modules, so it is an npm module. (Unpublished for now.)
- Install [nvm](https://github.com/nvm-sh/nvm) - Ubuntu's nvm is too old, and we need to be flexible about versions.
- `nvm install 14.15.4` - current stable version. I haven't tested with anything else.
- Install these files (you can do this with `git clone`).
- Install the dependencies: `npm install -g webpack webpack-cli html-webpack-plugin clean-webpack-plugin html-loader paper --save-dev`
- Build: `npm run build`. This will create a self-contained web application in `dist/`
- Make a local webserver map a URL to that directory. E.g. `cd dist/; python3 -m http.server` will make `http://localhost:8000/` map to it on my machine.
- Open the URL in a web browser. You should see a green doughnut shape drawn with paper.js.
