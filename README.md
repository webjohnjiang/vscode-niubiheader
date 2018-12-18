# niubi-file-header README

给文件顶部添加文件注释的vscode扩展插件。

啥也不说了老铁，看名字就知道，就是牛逼

## Features

需要什么功能你尽管提需求，老哥我立马给你实现


## usage

安装后，使用 `cmd/ctrl + shift + i` 来向文件中插入文档注释

默认的插入的注释是这个样子的:

```js
/*
 * @file 文件描述
 * @author: sheldoncui
 * @date: 2018-12-19 02:11
 */
```

在超过20秒之后如果进行保存操作 这个注释的date时间会自动更新。

### 配置项说明

如果你不喜欢当前模板样式，你可以自定义模板。甚至可以在里面插入更多变量。
方法很简单，只需在vscode自定义配置中搜索 `niubiheader` 就能找到所有可用配置. 然后仿照进行配置修改即可。

```js
    // tpl 配置是指的文档注释的模板 (里面可使用 ${xx} 来作为变量)
    "niubiheader.tpl": "/*\r\n * @file {description}\r\n * @author: {author}\r\n * @date: {updateTime}\r\n */\r\n"
    // data.author 是定义模板变量 author
    "niubiheader.data.author": "sheldoncui", // 
    // data.description 是定义目标变量 description
    "niubiheader.data.description": "文件描述",
    // 另外有几个预置的变量可在模板中使用: createTime(创建时间), updateTime(文档最后更新时间)

    // dateFormat 设置是定义模板中时间的输出格式 y年 M月 d天 h小时 m分钟 s秒
    "niubiheader.dateFormat": "yyyy-MM-dd hh:mm",
```

## 自定义变量举例

比如你希望你的注释中加一个 @company 公司字段。

那么这个场景下，你需要修改下 tpm 模板:

```js
"niubiheader.tpl": "/*\r\n * @company 腾讯科技 \r\n * @file {description}\r\n * @author: {author}\r\n * @date: {updateTime}\r\n */\r\n"
```

但你的公司可能会经常修改，所以你希望把它从模板中抽出来，变成一个变量。这时，你可以把模板改为:

```js
"niubiheader.tpl": "/*\r\n * @company {mycompany} \r\n * @file {description}\r\n * @author: {author}\r\n * @date: {updateTime}\r\n */\r\n"
```

然后加一个niubiheader的data配置:

```js
"niubiheader.data.mycompany": "阿里巴巴",
```

这样就ok了。保存配置不需重启，立刻就能生效哦！

## 感谢

感谢您的使用