# babel命令行使用
@babel/core
@babel/cli

**babel默认是不做任何转换的需要手动选择插件**

## bebel的预设
@babel/preset-env  

使用： --presets=@babel/preset-env

常见的预设有三个
- env
- react
- TypeScript

## babel的底层原理
我们可以将babel看成一个编译器

1. @babel/parser  将代码转换成AST
2. @babel/traverse 遍历AST
3. @babel/core 将AST转换成代码
「『「
解析阶段 - 转换阶段 - 生成阶段
插件是在解析到转换时处理的
