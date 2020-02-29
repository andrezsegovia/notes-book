# Starting Notes About Reactjs

## Pre-requirements
- Node.js v10.16.3 or later
- Nope Package Manaher (NPM)
- React Developer Tools plugin for Chrome and Firefox

## Starting a new project
- Create a new dicetory for the project
- Inside this directory execute ```npm init -y``` to init a new NPM base project
- Install webpack ```npm install --save-dev webpack webpack-cli```
- Add a npm script to init and build the project 
	```json
		"scripts": {
			"start": "webpack --mode development",
			"build": "webpack --mode production",
		}
	```
- Install react packages ```npm install react react-dom```
- Install Babel packages to compile the code to a readable format for every browser ```npm install --save-dev @babel/code @babel/preset-env @babel/preset-react babel-loader```
- Configure Webpack to user React and Babel packages. This configurtion is place within the ```webpack.config.js``` file
    ```json
        modele.exports = {
            module: {
                rules: [
                    {
                        test: /\.js$/,
                        excluede: /node_modules/,
                        use: {
                            loader: 'babel-loader',
                        },
                    },
                ],
            },
        }
    ```
- Create a ```.babelrc``` file to configure ```babel-loader``` to use ```@babel/preset-env``` and ```@babel/preset-react``` and add the below configuration
    ```json
    {
        "presets": [
            [
                "@babel/preset-evn",
                {
                    "targets": {
                        "node": "current"
                    }
                }
            ],
            "@babel/react",
        ]
    }
    ```
- To Webpack add the script tag into the ```index.html``` to load the minified bundle code we need to install ```html-webpack-plugin``` as a development dependency: ```npm instlal --save-dev html-webpack-plugin```. Then web have to add the configuration within ```webpack.config.js``` file:
    ```json
        const HtmlWebPackPlugin = require('html-webpack-plugin');

        const htmlPlugin = new HtmlWebPackPlugin({
            template: './src/index.html',
            filename: './index.html',
        });

         modele.exports = {
                module: {
                    rules: [
                        {
                            test: /\.js$/,
                            excluede: /node_modules/,
                            use: {
                                loader: 'babel-loader',
                            },
                        },
                    ],
                },
            }
    ```
- To add hot reloading to the project we should install ```webpack-dev-server``` as a development dependency and modify the start npm script:
	```json
		"scripts": {
			"start": "webpack-dev-server --mode development --hot",
			"build": "webpack --mode production",
		}
	```
	
## Creating a PWA with Create React App
We can use this starter kit if the want to avoid all the starting configuration of a React project.

First, install ```create-react-app``` package globally
```bash
npm install -g create-react-app
```
 The we can create a new project executing the following command
 ```bash
npm init react-app project-name
 ```
