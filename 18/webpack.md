webpack


官網
https://www.webpackjs.com/
https://webpack.js.org/

node.js
安裝 node.js
webpack usage
webpack 最好使用 node > 9 以上
如何安裝
你需要全域安裝來使用 webpack 大部分的功能：
npm install -g webpack
然而 webpack 有些功能，像是優化的 plugins，需要你將它安裝在本機。像這種情況下你需要：
npm install --save-dev webpack

全域安裝 npm install webpack-cli -g
沒有配置文件時使用 (webpack.config.js)
指令
webpack app.js // 檔案名稱會自動打包檔案

dist/main.js // 打包出來

-p 產品模式
-d 開發模式

文件配置
從 webpack v4.0.0 開始，可以不用引入一個配置文件。然而，webpack 仍然還是高度可配置的。在開始前你需要先理解四個核心概念：

入口(entry)
輸出(output)
loader
插件(plugins)

基本配置 webpack.config.js
module.exports = {
    entry: '',               // 入口文件
    output: {},              // 出口文件
    module: {},              // 處裡對應模組
    plugins: [],             // 對應的插件
    devServer: {},           // 服務器配置
    mode: 'development'      // 開發模式配置
}
1. 入口跟出口模式 entry output
指令
webpack -d //開發模式

webpack -p //上線模式

webpack -d --watch // 開發監看模式


webpack.config.js
const path = require('path');

module.exports = {
  entry: 'app.js',
  output: {
    path: path.resolve(__dirname, 'dist'),
    filename: 'bundle.js'
  }
};

2. loader 使用 (css / sass)
安裝 css lodader 與 style loader
npm init
npm install --save-dev css-loader style-loader
配置[Configuration]

module: {
        rules: [{
            // 格式
            test: /\.css$/,
            //順序是由下到上 css > style
            use: [
                'style-loader',
                'css-loader'
            ],
        }]

    }, 
3. CSS 檔案額外輸出到一個 .css 檔案裡面的話，要額外再使用其他的 loader。
安裝 mini-css-extract-plugin
npm i --save-dev mini-css-extract-plugin
const MiniCssExtractPlugin = require('mini-css-extract-plugin');

module: {
        rules: [{
            // 格式
            test: /\.css$/,
            //順序是由下到上 css > style
            use: [{
                loader: MiniCssExtractPlugin.loader,
                options: {
                  publicPath: './dist'
                }
              },
                //'style-loader',
                'css-loader'
            ],
        }]

    }
對應plugin

 plugins: [
        new MiniCssExtractPlugin({
            filename: "./style.css"
        })
    ],             // 對應的插件


各別產生兩個css檔與js檔，在entry的入口時要分別設置兩個進入點並在output時更改 [name]
entry : {
       app : "./app.js",
       app2 : "./app2.js"
    },
output: {
        path: path.resolve(__dirname, 'dist'),
        filename: '[name].bundle.js'
      },
plugins: [
        new MiniCssExtractPlugin({
            filename: "./[name].css"
        })
    ],      
4. sass loader 使用
安裝 sass-loader node-sass
npm install sass-loader node-sass --save-dev

多了sass loader 與格式

   module: {
        rules: [{
            // 格式
            test: /\.(sass|scss|css)$/,
            //順序是由下到上 sass > css > style
            use: [{
                loader: MiniCssExtractPlugin.loader,
                options: {
                  publicPath: './dist'
                }
              },
                'css-loader',
                'sass-loader'
            ],
        }]

    }, 
4. HTML的注入 （HtmlWebpackPlugin）
安裝
npm install --save-dev html-webpack-plugin

引入套件

const HtmlWebpackPlugin = require('html-webpack-plugin');


基本配置

plugins: [
        new MiniCssExtractPlugin({
            filename: "./[name].css"
        }),
        new HtmlWebpackPlugin()

    ], 
5. 服務器的使用
https://www.npmjs.com/package/webpack-dev-server

安裝
npm install webpack-dev-server --save-dev
服務器配置
 devServer: {
        contentBase: './dist',
        host: 'localhost',
        port: 3000,
        // 指定首頁檔案
        index: 'index.html',
        open: true
    },
指令 webpack-dev-server
會出錯，必須要安裝 npm i -D webpack-cli 在專案裡
必須在HtmlWebpackPlugin 裡做好配置
new HtmlWebpackPlugin({
             //來源檔
            template: 'index.html',
            //產生的檔案
            filename: 'index.html', 

        })
my note
你需要全域安裝來使用 webpack 大部分的功能：
npm install -g webpack
全域安裝
npm install webpack-cli -g
使用指令查看版本
webpack -v
webpack-cli -v
生產package檔
npm init
寫入想要的套件在package.json中
  "devDependencies": {
    "webpack": "^4.44.1"
  }
安裝package檔
npm install
再跑一次版本
npm install --save-dev webpack
監看變動
webpack -d --watch