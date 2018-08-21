## Babel  Javascript 编译器。

将最新版本的Ecmascript 编译成浏览器可兼容的版本。

参考文档：https://www.babeljs.cn/

### 基于webpack 配置babel 

```
// 安装
npm install --save-dev babel-loader babel-core
```

```
// 配置webpack
module: {
  rules: [
    { test: /\.js$/, exclude: /node_modules/, loader: "babel-loader" }
  ]
}
```

```
//配置 babel,在根目录创建.babelrc文件

{
  "presets": ["env"]
}
```

### babel 配置项说明 
  * presets
  
    Presets 是可共享的 .babelrc 配置或者只是一个 babel 插件的数组。比如 babel-preset-env 相当于 es2015 ，es2016 ，es2017 及最新版本。 官方提供的presets有 env,react,flow等。 state-x 表示实验性质阶段的preset
    
    ~ Stage 0 - 稻草人: 只是一个想法，可能是 babel 插件
    
    ~ Stage 1 - 提案: 初步尝试。
    
    ~ Stage 2 - 初稿: 完成初步规范。
    
    ~ Stage 3 - 候选: 完成规范和浏览器初步实现。
    
    ~ Stage 4 - 完成: 将被添加到下一年度发布。
    
    ~~~
    // 需要提前npm install 相关插件
    {
      presets:['babel-preset-env','babel-preset-react']
    }
    
    // 也可以简化为
    {
      presets:['env','react']
    }
    ~~~
    presets 编译js的插件顺序是倒序
    
  * plugins 
    
     配置用到的插件列表， plugins 编译js的插件顺序是正序。  在配置文件中 plugins会先于presets执行。
     
   * env 
     
      针对不同环境下配置不同的 presets plugins等配置选项
      
      ~~~
      {
        env:{
          production:{
            presets:[]
          }
        }
      }
      ~~~
      
   ### babel-polyfill
   babel-polyfill 可以生成一个es2015的环境，可以直接引入浏览器，也可以在某个js文件中通过 import引入，也可以在webpack中配置以在全局起作用。
   ~~~
   
   module.exports = {
      entry: ["babel-polyfill", "./app/js"]
   };

   ~~~
