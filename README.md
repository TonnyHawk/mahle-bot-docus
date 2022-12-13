# Mahle bot documentation
## Documentation structure
- How to build and run the project
    - Installing Webpack
    - Commands for building and developing:
- How to use embedded, small version of the chat
- Project structure or where to find files needed
    - src
    - target
    - presentation

# How to build and run the project
## Installing Webpack
First of all you need to install webpack to this folder
so do this:

1. Make shure that node and npm (node package manager) is installed on your computer
2. Open terminal right in this folder
3. Type `npm i`

P.S. after those steps the "node_modules" folder will appear, you don't need to make
anything with it, webpack needs it for internal use

4. Now you can use commands for building and developing

## Commands for building and developing:
- `npm run build` - builds project into "target" folder
- `npm run serve` - developing mode with live changes in browser

to stop any of those commands press "ctrl+c" in runing terminal

# How to use embedded, small version of the chat
1. Paste embed-script.js on the page where you want to have webchat
2. Make sure that you already hosted the full width version somewhere on the internet
3. On line 172 in file `embed-script.js` change the `object.src` value to the actual path to the full width webchat version.

# Project structure or where to find files needed
## The src folder
The source `src` folder with it directories looks like this
```shell
src/
├── assets
│   ├── chat-avatar
│   ├── embed-version
│   │   └── assets
│   │       └── favicon
│   ├── favicon
│   ├── fonts
│   ├── icons
│   │   ├── arrows
│   │   ├── button-arrows
│   │   └── triangles
│   └── images
├── js
│   ├── modules
│   └── vendor
│       └── cognigy
├── sass
│   ├── _functions
│   └── _partials
├── shaders
└── types
```
## Entrypoints
- [src/js/index.ts](./src/js/index.ts) - main `javascript` file
- [src/sass/main.scss](./src/sass/main.scss) - main `styles` file
- [src/index.html](./src/index.html) - main `html` file where all markup is
- [src/assets/js/embed-script.js](./src/assets/js/embed-script.js) - smaller version of the webchat to use as a widget
## Src folder in detail
### assets [(./src/assets)](./src/assets)
Files that are needed for script/page to looks good like images, fonts, favicons... or additional features like embeded version of a webchat
- [embed-version/](./src/assets/embed-version/) - The script that adds webchat widget to the page
### js [(./src/js)](./src/js)
Files that will be connected and built into one main.js file that is the webchat itself
- [vendor/](./src/js/vendor) - external libraries
- [modules/](./src/js/modules) - microservices used in a webchat
### sass [(./src/sass)](./src/sass)
Literally all styles
### shaders [(./src/shaders)](./src/shaders)
Files that we need to display a 3d bot avatar
### types [(./src/types)](./src/types)
Files that describe some global typescript structures

## Other files and folders

- [./presentation/](presentation/) - folder for presenting both versions of webchat: full-page and side-like page widget  
- [./prepare-presentation.sh](prepare-presentation.sh) - collects files that are needed for presentation into dedicated folder (should be runed after building the project). A 'presentation' is just a way to see how both full page webchat and the embedded small version look like and work. Just start a server in a folder called `presentation` or host this folder on dedicated server to see how it looks like
- [./.gitignore](./.gitignore) - lists all files that will be ignored by git
- [./.prettierignore](./.prettierignore) - same as gitignore but for prettier formatter 
- [./.prettierrc](./.prettierrc) - prettier configuration file
- [./package-lock.json](./package-lock.json) - generated automatically by npm and lists the exact version of all modules and dependencies installed on that particular project
- [./package.json](./package.json) - npm project configuration file
- [./postcss.config.js](./postcss.config.js) - file needed for webpack. Defines which plugins will be used to css that webpack will find during the build process
- [./tsconfig.json](./tsconfig.json) - main typescript configuration file
- [./webpack.dev.js](./webpack.common.js) - webpack config part for developing mode
- [./webpack.prod.js](./webpack.common.js) - webpack config for production mode
- [./webpack.common.js](./webpack.common.js) - webpack setup that is common for both developing and production modes






