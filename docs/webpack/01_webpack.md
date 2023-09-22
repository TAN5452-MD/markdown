# webpack
## mode
  //默认值是production
  //设置不同的配置 webpack会自身给你加上属于不同模式的配置 production会加入混淆等
  mode:'production',
## 开启源映射 
devtool:"source-map"
可以对应到打包前的源文件方便调试**在转换后的代码最后添加注释他指向source-map**
要在浏览器中打开设置（css也可以生成）

## devtool
第一个 devtool:"source-map"
devtool大概有26个值可以设置 分别是不同的风格 对于构建速度和重新构建速度有不同的影响

### 不会生成sourcemap的值
 - false
 - none (production环境默认值)
 - eval

### 会生成sourcemap的值
eval-source-map    但是是以 URL的形式添加到**eval**函数的后面的
inline-source-map  会添加到打包文件的后面
cheap-source-map  低开销 更加高效  development环境 （没有列信息，只有行信息）
cheap-module-source-map 对于用loader处理后的代码能够更好的还原
hidden-source-map 会生成 但是不会自动引用URL，需要手动加入
nosources-source-map  不会生成映射文件，只会有报错信息
