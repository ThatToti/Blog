# npm 包管理-版本锁定

上次给大家介绍了一下npm 的 package.json 里面,关于版本符号的东西.具体文章内容戳这:



关于了解这个的概念,还真的很有用.最近入手一个新的项目,同事来给我配环境.安装到一个库的时候,他说,这个库不能用包里面的版本,我发一个版本给你吧.于是,他发了一个 zip 过来...



项目里面的 package.json 大概如下:

```js
{
    "highchart":"~6.0.3"
}
```

这个的意思是,匹配到最小一级的最新版本,如果有 v6.0.9的话,那么就匹配到 v6.0.9



而项目中使用的版本,是 v4的.因为用了一个插件的缘故,导致不得不继续使用久版本.其实锁版本不用那么复杂,不需要把库专门打包出来单独维护这样.只需要把 package.json 改成如下,就能实现锁版本了:

```js
{
    "highchart":"4.0.0"
}
```



把前面的符号去掉,再跑一遍 npm install, 就会更新这个库到对应版本,不会自动升级了.



