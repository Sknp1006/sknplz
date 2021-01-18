---
title: 关于网站
date: 2020-07-02 16:55:40
---
# 吃水不忘挖井人の如何创建酷炫的个人网站

<br />

## 零、准备工作(基础版)
* 该网站是基于 **hexo** 使用 **yun** 主题部署在 **github** 的博客
* 参见 [hexo 官方文档](https://hexo.bootcss.com/docs/) ，在按要求装好hexo、Node.js、Git后，即可愉快的搭建自己的网站啦~
* 如果想获得更好的体验，建议使用[hexo主题](https://yun.yunyoujun.cn/) 。
* 如果你想使用跟我一样的主题，请参照 [https://yun.yunyoujun.cn/](https://yun.yunyoujun.cn/) ，你的99%的问题都能在这里找到答案( •̀ ω •́ )y
* 对于小白，搭建好一个框架大概花费2天时间（保守估计）

## 一、推荐配置(进阶版)
### Valine评论模块
* 其实完成上面的内容已经可以正常部署网站，但是在实践中发现还有待优化的地方;
> 关于valine模块，参见 [https://valine.js.org/](https://valine.js.org/) 
> Valine可自定义表情ψ(｀∇´)ψ，推荐使用 [https://bili33.top/2020/04/19/Valine-Magic/](https://bili33.top/2020/04/19/Valine-Magic/)
```yaml
valine:  # 评论系统支持  
  enable: true
  appId: 你的appId
  appKey: 你的appKey
  placeholder: 大佬求指教 _(:з」∠)_  # comment box placeholder
  avatar: mp
  meta:
    - nick
    - mail
    - link
  pageSize: 10 # pagination size
  lang: zh-CN
  visitor: true
  highlight: true
  recordIP: true
  # serverURLs:
  emojiCDN: https://valinecdn.bili33.top/
  emojiMaps:
    {
      "bilibilitv2": "bilibilitv/[tv_doge].png",
    }
  enableQQ: true
  requiredFields:
    - nick
    - mail
```
```yaml
minivaline:
  enable: true
  appId: 你的appId
  appKey: 你的appKey
  placeholder: 大佬求指教 _(:з」∠)_
  adminEmailMd5: # The MD5 of Admin Email to show Admin Flag.
  math: true # Support MathJax.
  md: true # Support Markdown.
  # MiniValine's display language depends on user's browser or system environment
  # If you want everyone visiting your site to see a uniform language, you can set a force language value
  # Available values: en  | zh-CN | (and many more)
  # More i18n info: https://github.com/MiniValine/minivaline-i18n
  lang:
```
> Valine 的扩展和增强功能可以参考 [Valine-Admin](https://github.com/DesertsP/Valine-Admin)，适用于miniValine

### 二、MARKDOWN技巧
> 如何编写markdown？网络上有很多相关教程，这里分享一个 [在线编辑markdown的网站](http://www.mdeditor.com/) ，它已经为你准备好了不同语句所对应的样式，依葫芦画瓢就能学会啦~
> 技巧是要练的，熟能生巧嘛~
#### 折叠语句

<details><summary>查看全部</summary>

```html
<details><summary>查看全部</summary>

markdown的正文与标签之间要空行
同理，上标签的上方与下标签的下方也要空行

<details><summary>禁止套娃</summary>

禁止禁止套娃<(￣ c￣)y▂ξ

</details>

</details>
```

</details>

#### 支持代码高亮

<details><summary>查看全部</summary>

| language	| key |
| ---------|------|
| 1C  |	1c |
| ActionScript	| actionscript|
| Apache	| apache|
| AppleScript	| applescript|
| AsciiDoc	| asciidoc|
| AspectJ	| asciidoc|
| AutoHotkey	|autohotkey|
| AVR Assembler	|avrasm|
| Axapta	|axapta|
| Bash|	bash|
| BrainFuck	|brainfuck|
| Cap’n Proto	|capnproto|
| Clojure REPL	|clojure|
| Clojure	|clojure|
| CMake	|cmake|
| CoffeeScript	|coffeescript|
| C++	|cpp|
| C#	|cs|
| CSS	|css|
| D	|d|
| Dart	|d|
| Delphi	|delphi|
| Diff	|diff|
| Django	|django|
| DOS.bat	|dos|
| Dust	|dust|
| Elixir	|elixir|
| ERB(Embedded Ruby)	|erb|
| Erlang REPL	|erlang-repl|
| Erlang	|erlang|
| FIX	|fix|
| F#	|fsharp|
| G-code(ISO 6983)	|gcode|
| Gherkin	|gherkin|
| GLSL	|glsl|
| Go	|go|
| Gradle	|gradle|
| Groovy	|groovy|
| Haml|	haml|
| Handlebars	|handlebars|
| Haskell	|haskell|
| Haxe	|haxe|
| HTML	|html|
| HTTP	|http|
| Ini file	|ini|
| Java	|java|
| JavaScript	|javascript|
| JSON	|json|
| Lasso	|lasso|
| Less	|less|
| Lisp	|lisp|
| LiveCode	|livecodeserver|
| LiveScript	|livescript|
| Lua	|lua|
| Makefile	|makefile|
| Markdown	|markdown|
| Mathematica	|mathematica|
| Matlab	|matlab|
| MEL (Maya Embedded Language)	|mel|
| Mercury	|mercury|
| Mizar|	mizar|
| Monkey	|monkey|
| Nginx	|nginx|
| Nimrod	|nimrod|
| Nix	|nix|
| NSIS	|nsis|
| Objective C	|objectivec|
| OCaml	|ocaml|
| Oxygene	|oxygene|
| Parser 3	|parser3|
| Perl	|perl|
| PHP	|php| 
| PowerShell	|powershell|
| Processing	|processing|
| Python’s profiler output	|profile|
| Protocol Buffers	|protobuf|
| Puppet	|puppet|
| Python	|python|
| Q	|q|
| R	|r|
| RenderMan RIB	|rib|
| Roboconf	|roboconf|
| RenderMan RSL	|rsl|
| Ruby	|ruby|
| Oracle Rules Language	|ruleslanguage|
| Rust	|rust|
| Scala	|scala|
| Scheme	|scheme|
| Scilab	|scilab|
| SCSS	|scss|
| Smali|	smali|
| SmallTalk	|smalltalk|
| SML	|sml|
| SQL	|sql|
| Stata|	stata|
| STEP Part21(ISO 10303-21)	|step21|
| Stylus	|stylus|
| Swift|swift|
| Tcl	|tcl|
| Tex	|tex|
| text	|text/plain|
| Thrift	|thrift|
| Twig	|twig|
| TypeScript	|typescript|
| Vala	|vala|
| VB.NET	|vbnet|
| VBScript in HTML	|vbscript-html|
| VBScript	|vbscript|
| Verilog	|verilog|
| VHDL	|vhdl|
| Vim Script	|vim|
| Intel x86 Assembly	|x86asm|
| XL	|xl|
| XML	|xml|
| YAML	|yml|

</details>

---

![](https://cdn.jsdelivr.net/gh/Sknp1006/cdn@master/img/anime/tobecontinued.jpg)

---
# More
有关我为什么创建个人博客，答案在 [这里](https://sknplz.xyz/about/) 