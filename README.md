# i18n tools 国际化多语言插件

[插件地址](https://marketplace.visualstudio.com/items?itemName=oorzc.i18n-tools-plus)

## 介绍

i18n tools 提供一键扫描中文、提取文案、遗漏扫描、文案回显、翻译、支持代码跳转等功能，帮助快速生成多语言应用。

## 功能

* 建议使用前先备份代码
* 为防止误操作，部分功能使用系统通知弹窗提示，请在右下角开启允许消息通知

![](https://qiniu.sponges.cn/note/2023/02/22/20230222224451.png)

- 支持一键提取文件或目录内包含中文内容的文件

![](https://qiniu.sponges.cn/note/2023/02/22/20230222211615.gif)

- 支持一键还原文件或目录为中文显示

![](https://qiniu.sponges.cn/note/2023/02/22/20230222211833.gif)

- 遗漏扫描 （针对不存在的i18n key检测）

![](https://qiniu.sponges.cn/note/2023/02/19/20230219232153.png)

- 支持右键菜单对选中目录进行提取、还原、遗漏扫描功能

![](https://qiniu.sponges.cn/note/2023/02/22/20230222225541.png)

- 支持文案回显

![](https://qiniu.sponges.cn/note/2023/02/17/20230217234638.png)

- 支持command/ctrl + 点击翻译函数内的 key, 跳转到 key 在json 文件中对应的位置

![](https://qiniu.sponges.cn/note/2023/02/17/20230217234532.gif)

- 支持全量翻译、增量翻译，默认增量翻译（目前使用百度和腾讯翻译）
* 翻译密匙申请：      
 [百度翻译申请参考](https://bobtranslate.com/service/translate/baidu.html)           
 [腾讯翻译申请参考](https://bobtranslate.com/service/translate/tencent.html)        
![](https://qiniu.sponges.cn/note/2023/02/22/20230222225026.png)

> 注意：目前适合vue2，js和ts文件提取（vue3、react暂不支持，会不定期更新）
## 插件配置
![](https://qiniu.sponges.cn/note/2023/02/17/20230217235023.png)

## 项目配置

系统会自动在根目录生成项目配置文件, 当然你也可以在项目文件夹下创建 `i18n-tools.config.js` 文件, 按下面的配置修改你的自定义配置

```js
module.exports = {
      entry: ['src'], // 提取、还原、遗漏扫描入口文件夹，可以配置多个,默认是 src
      outDir: 'src/locales', // i18n 输出文件夹 默认是 src/locales
      outShow:1, //输出文件展示结构 1 扁平化结构 2树级结构 默认扁平化
      exclude: ['src/locales'], // 不提取的文件夹, 默认是 ['src/locales']
      extensions: ['.vue', '.js', '.ts'], // 提取的文件后缀名，默认是 ['.js', '.vue', '.ts']
      filename: 'zh_cn', // 输出的文件名,默认为 zh_cn
      extname: 'js', //  输出的文件后缀名,支持json和js（js需要符合CommonJS模块化规范，不支持ES6模块化，格式 module.exports = {}，输出后使用require加载文件），默认为 js  
      langList: ['en'] // 翻译目标语言列表，默认是 ['en']   具体语种请自行查看。百度支持https://api.fanyi.baidu.com/doc/21，腾讯支持：en（英语）、ja（日语）、ko（韩语）、fr（法语）、es（西班牙语）、it（意大利语）、de（德语）、tr（土耳其语）、ru（俄语）、pt（葡萄牙语）、vi（越南语）、id（印尼语）、th（泰语）、ms（马来语）注意：使用不同的翻译接口，需要更换对应的语言编码
}
```

## BUG反馈

[Github](https://github.com/oorzc/i18n-tools/issues)
