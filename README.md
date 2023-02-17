# i18n-tools 国际化多语言插件

## 介绍

i18n-tools 提供一键扫描中文、提取文案、文案回显、翻译、支持代码跳转等功能，帮助快速生成多语言应用。

## 功能

- 支持一键提取文件或目录内包含中文内容的文件
![](http://qiniu.sponges.cn/note/2023/02/17/20230217234155.gif)
- 支持一键还原文件为中文显示
![](http://qiniu.sponges.cn/note/2023/02/17/20230217234407.gif)
- 支持文案回显
![](http://qiniu.sponges.cn/note/2023/02/17/20230217234638.png)
- 支持全量翻译、增量翻译，默认增量翻译（目前使用百度和腾讯翻译）
![](http://qiniu.sponges.cn/note/2023/02/17/20230217235023.png)
![](http://qiniu.sponges.cn/note/2023/02/17/20230217234904.png)
- 支持command/ctrl + 点击翻译函数内的 key, 跳转到 key 在json 文件中对应的位置
![](http://qiniu.sponges.cn/note/2023/02/17/20230217234532.gif)
注意：目前适合vue2，js和ts文件提取（vue3、react暂不支持，会不定期更新）

## 配置

系统会自动在根目录生成项目配置文件, 当然你也可以在项目文件夹下创建 `i18n-tools.config.js` 文件, 按下面的配置修改你的自定义配置

```js
module.exports = {
    entry: 'src', // 提取入口文件夹,默认是 src
    outDir: 'src/locales', // i18n 输出文件夹 默认是 src/locales
    outShow:1, //输出文件展示结构 1 扁平化结构 2树级结构 默认扁平化
    exclude: ['src/locales'], // 不提取的文件夹, 默认是 ['src/locales']
    extensions: ['.vue', '.js', '.ts'], // 提取的文件类型，默认是 ['.js', '.vue', '.ts']
    filename: 'zh_cn', // 输入的中文 json 文件名,默认为 zh_cn
    // 翻译目标语言列表，默认是 ['en']   具体语种请自行查看。百度支持https://api.fanyi.baidu.com/doc/21，腾讯支持：en（英语）、ja（日语）、ko（韩语）、fr（法语）、es（西班牙语）、it（意大利语）、de（德语）、tr（土耳其语）、ru（俄语）、pt（葡萄牙语）、vi（越南语）、id（印尼语）、th（泰语）、ms（马来语）注意：使用不同的翻译接口，需要更换对应的语言编码
    langList: ['en']
}
```
## BUG反馈

[Github](https://github.com/oorzc/i18n-tools/issues)
