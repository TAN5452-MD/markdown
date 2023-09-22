# 脚本
npm install webpack-dev-server   -D

"serve": "webpack serve"

- webpack-dev-server 在编译之后不会写入到任何输出文件，而是将 bundle **文件保留在内存中**
 - 事实上webpack-dev-server使用了一个库叫memfs（memory-fs webpack自己写的）

# 处理静态文件
webpack.js
devServer:{
  //默认配置了public,可以不写当需要其他文件夹的时候再主动配置
  static:["public"]
}

# 其他配置
liveReload //参见文档
port 
open
// gzip压缩
compress

# 代理
devServer:{
  proxy:{
    "/api":{
      target:"http://localhost:3000",
      pathRewrite:{
        "^/api":""
      }
    }
  }
}

# historyApiFallback
//当使用 HTML5 History API 时，任意的 404 响应都可能需要被替代为 index.html
//如果不配置，当访问不存在的页面时会报错
devServer:{
  historyApiFallback:true
}

#historyApiFallback
//当使用 HTML5 History API 时，任意的 404 响应都可能需要被替代为 index.html
默认为false
还可以设置为一个对象值
事实上是通过connect-history-api-fallback插件实现的
