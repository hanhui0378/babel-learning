# babel-learning

### 安装依赖

```
yarn
```

### 运行 TS 代码

```
node -r ts-node/register xxx.ts
```

### 运行 JS 代码

```
node xxx.js
```

## AST相关
1. `@babel/parse` 把代码code变成AST
2. `@babel/traverse` 遍历AST变成修改
3. `@bable/generate` 把AST变成代码code2

babel可以吧高级代码翻译为低级代码(ES5)
@babel/parser
@babel/traverse
@babel/generator
@babel/cord 包含前三者
@babel/preset-env 内置很多规则

### code -> AST -> code2
1. let_to_var.ts -> 把代码中的 let声明 变为 var声明
2. file_to_var.ts -> 读取文件中的代码(test.js) 将代码中的let声明 变为 var声明 并生成编译后的文件(test.es5.js)
3. to_es5.ts -> 使用 `@babel/preset-env` 编译code 打印结果

### 收集依赖(import)
1. dep_1.ts -> 读取 `project_1` 项目并收集项目中的依赖(import)
2. dep_2.ts -> 读取 `project_2` 项目并递归收集项目中的依赖(import)
3. dep_3.ts -> 读取 `project_3` 项目并递归收集项目中的依赖(import)，因为项目中有循环依赖会造成死循环
4. dep_4.ts -> 读取 `project_4` 项目并递归收集项目中的依赖(import)，通过检测key来避免重复收集依赖造成的死循环
