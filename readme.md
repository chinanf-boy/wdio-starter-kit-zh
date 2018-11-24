# klamping/wdio-starter-kit [![explain]][source] [![translate-svg]][translate-list]

<!-- [![size-img]][size] -->

[explain]: http://llever.com/explain.svg
[source]: https://github.com/chinanf-boy/Source-Explain
[translate-svg]: http://llever.com/translate.svg
[translate-list]: https://github.com/chinanf-boy/chinese-translate-list
[size-img]: https://packagephobia.now.sh/badge?p=Name
[size]: https://packagephobia.now.sh/result?p=Name

「 使用 TravisCI, Sauce Labs 和 视觉回归测试，一个 快速设置 WebdriverIO 测试脚本的 模版库 」

[中文](./readme.md) | [english](https://github.com/klamping/wdio-starter-kit)

---

## 校对 ✅

<!-- doc-templite START generated -->
<!-- repo = 'klamping/wdio-starter-kit' -->
<!-- commit = '11619d622fc6719dc88921fee34aef82eb0b8d1d' -->
<!-- time = '2018-09-13' -->

| 翻译的原文 | 与日期        | 最新更新 | 更多                       |
| ---------- | ------------- | -------- | -------------------------- |
| [commit]   | ⏰ 2018-09-13 | ![last]  | [中文翻译][translate-list] |

[last]: https://img.shields.io/github/last-commit/klamping/wdio-starter-kit.svg
[commit]: https://github.com/klamping/wdio-starter-kit/tree/11619d622fc6719dc88921fee34aef82eb0b8d1d

<!-- doc-templite END generated -->

### 贡献

欢迎 👏 勘误/校对/更新贡献 😊 [具体贡献请看](https://github.com/chinanf-boy/chinese-translate-list#贡献)

## 生活

[help me live , live need money 💰](https://github.com/chinanf-boy/live-need-money)

---

[![Build Status](https://travis-ci.org/klamping/wdio-starter-kit.svg?branch=master)](https://travis-ci.org/klamping/wdio-starter-kit)
[![js-semistandard-style](https://img.shields.io/badge/code%20style-semistandard-brightgreen.svg?style=flat-square)](https://github.com/Flet/semistandard)

# WebdriverIO 入门套件

使用 TravisCI, Sauce Labs 和 视觉回归测试，一个 快速设置 WebdriverIO 测试脚本的 模版库

## 步骤

1.  clone ,并运行`npm install`
2.  添加有效的`SAUCE_USERNAME`和`SAUCE_ACCESS_KEY`到您的环境变量以启用 Sauce Labs 集成.([设置 Sauce Labs](http://webdriver.io/guide/usage/cloudservices.html#Sauce-Labs))
3.  更新`wdio.conf.js`和`wdio.conf.local.js`的'baseUrl'属性
4.  更新测试文件夹中的 spec 文件和 page 对象

## 用法

默认情况下,使用

- `npm test`,运行测试命令.

- `npm run lint`, lint 代码.

## 该套件包括:

- [登录和注册测试,带有 page 对象](#入门测试用例)
- [Mocha](http://mochajs.org/)
- [全局`expect`的 Chai](http://chaijs.com/guide/styles/#expect)
- [Chai WebdriverIO](https://github.com/marcodejongh/chai-webdriverio)
- [Sauce Labs 集成](http://webdriver.io/guide/usage/cloudservices.html#Sauce-Labs)
- [视觉回归测试](https://github.com/zinserjan/wdio-visual-regression-service)
- [本地通知](http://blog.kevinlamping.com/continuous-local-webdriverio-testing-with-onchange-and-node-notifier-watching/)
- [ESLint](http://eslint.org/)，运用[semistandard 风格](https://github.com/Flet/semistandard)
- [WebdriverIO 调整了 gitignore 文件](https://github.com/klamping/wdio-starter-kit/blob/master/.gitignore#L61)

## 更多细节

### 入门测试用例

由于登录和注册页面在网站上无处不在，我已经包含了两个带有相应 Page 对象 的测试文件。

您很可能需要替换 Page 对象 中使用的选择器。

你还想要更新，Page 对象 中的`isLoggedIn`和`isRegistered` 函数，以返回正确的响应.

### 文件夹结构

测试和 Page 对象 位于`test\`文件夹,此目录给您创建需要的测试。

用一个`.spec.js`后缀命名测试。例如:`mytest.spec.js`

用一个`.page.js`后缀命名 page 对象文件。例如:`mypageobject.page.js`

视觉回归截图，则保存到`screenshots`文件夹.

### TravisCI 集成

该套件包括一个基本的`.travis.yml`文件设置允许轻松集成其服务。只需启用您的 repo 的[TravisCI](https://travis-ci.org/)你就会得到并运行它。并确保**更新**此文件顶部的小图标信息.

### 调试命令行标志以调整超时

通过将'DEBUG'环境变量设置为 true,可以基本上删除测试超时,从而允许您运行[`debug`命令](https://www.youtube.com/watch?v=xWwP-3B_YyE&lc=z12gw1vqpu2sunjeq222hrsxstf3glohh04)，期间你的测试不会超时.

`DEBUG=true npm test`

### 你的配置文件口味

默认情况下,测试将在 Sauce Labs 中运行,以测试您的生产服务器.

要在本地完全运行测试,请运行:

`npm test wdio.conf.local.js`

## 配置

[WebdriverIO 配置](http://webdriver.io/guide/testrunner/gettingstarted.html)可以通过双短划线传递(即`--`).

例如,要运行单个测试文件,请使用 WDIO 的`spec`参数:`npm test -- --spec=login`

双短划线表示应将剩余选项发送到 npm 正在运行的命令,而不是 npm 本身.

在前面的例子就是, `--`之后的一切转到 WDIO 命令行.

还有一些例子:

要更改日志级别,请传入`--logLevel`参数:`npm test -- --logLevel=verbose`

要指定某个 Web 服务器,请传入`baseUrl`参数:`npm test -- --baseUrl=http://url.of.server`
