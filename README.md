# smilevue

> A Vue.js project

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

# 引入vant的第一种方法 在main.js里面引进（不推荐）
import Vant from 'vant'
import 'vant/lib/vant-css/index.css'
Vue.use(Vant)
# 引入vant的第二种方法（推荐）
npm i babel-plugin-import -D 
安装之后在babelrc文件修改配置
  在plugins下引入
  ["import",{"libraryName":"vant","style":true}]
  在main.js下按需引入
