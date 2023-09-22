# 兼容性考虑 主要针对js和css新特性

browseslist底层会使用caniuse-lite来查询兼容性数据

有2种编写方式

- 在package.json里面编写
- 在.browserslistrc文件里面编写


## 如果没有配置 会有一个默认配置
> 0.1%
last 2 version
firefox ESR
not dead
  

有 or(默认) not and 三种模式


# Stage-X
• TC39 遵循的原则是：分阶段加入不同的语言特性，新流程涉及四个不同的 Stage
口 Stage 0: strawman（稻草人），任何尚未提交作为正式提案的讨论、想法变更或者补充都被认为是第0阶段的“稻草人”；
口 Stage 1:proposal（提议），提案已经被正式化，并期望解决此问题，还需要观察与其他提案的相互影响；
口Stage 2: draft（草稿），Stage 2 的提案应提供规范初稿、草稿。此时，语言的实现者开始观察 runtime 的具体实现是否
合理；
口 Stage 3:candidate（候补），Stage 3提案是建议的候选提案。在这个高级阶段，规范的编辑人员和评审人员必须在最终
规范上签字。Stage 3 的提案不会有太大的改变，在对外发布之前只是修正一些问题；
口stage 4: finished（完成），进入Stage 4的提案将包含在 ECMAScript 的下一个修订版中；


## polyfill有很多实践方式 最好的还是babel-plugin-transform-runtime 

npm install --save core-js regenerator-runtime

//设置polyfill
corejs: 3,
// false 不填充 usage 自动检测/ entry 入口文件填充(需要在文件中手动引入)
useBuiltIns: "usage"


## preset支持react语法
单独安装react插件太多且繁琐，所以我们可以使用@babel/preset-react来代替
