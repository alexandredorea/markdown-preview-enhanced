Markdown Preview Enhanced
===
Still Beta Version!    
[![](https://img.shields.io/github/tag/shd101wyy/markdown-preview-enhanced.svg)](https://github.com/shd101wyy/markdown-preview-enhanced/releases) ![](https://img.shields.io/apm/dm/markdown-preview-enhanced.svg)  [![](https://img.shields.io/github/stars/shd101wyy/markdown-preview-enhanced.svg?style=social&label=Star)](https://github.com/shd101wyy/markdown-preview-enhanced)  

[中文文档](./docs/README_CN.md)  

Feature **Pandoc Document Export** is now supported after version `0.8.4`! More information can be found [here](./docs/advanced-export.md)

You can now create **EBook** using this plugin! More information can be found [here](./docs/ebook.md).

Feature **Presentation Writer** is now supported after version `0.7.7`!  
[Click here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html) to see the introduction slides generated by **Markdown Preview Enhanced**.

Post [here](https://github.com/shd101wyy/markdown-preview-enhanced/issues) if you request new features or you want to report bugs ;)

(TOC below was generated by this package)

<!-- toc orderedList:0 -->

- [Markdown Preview Enhanced](#markdown-preview-enhanced)
	- [Features](#features)
	- [How it works](#how-it-works)
	- [Usages](#usages)
	- [Preview Context Menu](#preview-context-menu)
	- [Extra](#extra)
	- [For Developer](#for-developer)
	- [Thanks](#thanks)
	- [TODO](#todo)

<!-- tocstop -->
---

![main](https://cloud.githubusercontent.com/assets/1908863/15383014/14ad19d0-1dc2-11e6-9385-acd90f53a831.gif)

## Features
- **2-side scroll sync**  
- **[pandoc](./docs/advanced-export.md)**
- **Presentation Writer** (beta) [Introduction](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html)  
- **[Extensible](#for-developer)**
- markdown preview with math typesetting support   
You can choose [MathJax](https://github.com/mathjax/MathJax) or [KaTeX](https://github.com/Khan/KaTeX) to render math expressions  
- export **PDF**, **PNG**, and **JPEG**   
- export **ePub**, **Mobi**, and **PDF** ebook
- export beautiful **HTML** (mobile device supported)  
- customize Markdown Preview css  
- [TOC] generation **(beta)**  
- Flowchart / Sequence diagram
- Task List *(Github Flavored)*  
- Image Helper
- [Footnotes](https://github.com/shd101wyy/markdown-preview-enhanced/issues/35)  
- [Front Matter](https://github.com/shd101wyy/markdown-preview-enhanced/issues/100)
- And many more...

## How it works
- [remarkable](https://github.com/jonschlinkert/remarkable) to convert markdown to html.
- [KaTeX](https://github.com/Khan/KaTeX) or [MathJax](https://github.com/mathjax/MathJax) to render math expressions. ([KaTeX Supported functions/symbols](https://github.com/Khan/KaTeX/wiki/Function-Support-in-KaTeX))
  - expression within `$...$` will be rendered normally.  
  - expression within `$$...$$` will be rendered in displayMode.   
  - You can choose your math rendering method from [settings panel](#settings-panel).   
		**MathJax** supports more symbols, but it has slower rendering speed compared to **KaTeX**.
  - <img src="https://cloud.githubusercontent.com/assets/1908863/14398210/0e408954-fda8-11e5-9eb4-562d7c0ca431.gif">
- [mermaid](https://github.com/knsv/mermaid) to render flowchart and sequence diagram.  
	- code block within `mermaid` notation will be rendered by [mermaid](https://github.com/knsv/mermaid)  
	- check [mermaid doc](http://knsv.github.io/mermaid/#flowcharts-basic-syntax) for more information about how to create flowchart and sequence diagram   
	- <img src="https://cloud.githubusercontent.com/assets/1908863/15132962/468c0dd0-1624-11e6-868c-cf3033ce3b5d.gif">
- [PlantUML](http://plantuml.com/) to create multiple kinds of graph. (**Java** is required)  
	- You can install [Graphviz](http://www.graphviz.org/) (not required) to generate all diagram types.
	- code block within `puml` or `plantuml` notation will be rendered by [PlantUML](http://plantuml.com/).  
- [WaveDrom](http://wavedrom.com/) to create digital timing diagram.  
	- code block within `wavedrom` notation will be rendered by [wavedrom](https://github.com/drom/wavedrom).
- [Viz.js](https://github.com/mdaines/viz.js) to render [dot language](https://en.wikipedia.org/wiki/DOT_(graph_description_language)) graph.  
	- code block within `viz` notation will be rendered by [Viz.js](https://github.com/mdaines/viz.js).
- [reveal.js](https://github.com/hakimel/reveal.js) to render beautiful presentations.
	- [Click here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html) to see the introduction.

## Usages
To use this package, press <kbd>cmd + shift + p</kbd>   in atom editor first to toggle <strong> Command Palette </strong>. Then choose the commands below:
- <strong>Markdown Preview Enhanced: Toggle</strong>
  - Toggle Markdown file preview with KaTeX support.   
	You can also use the keymap <kbd>ctrl+shift+m</kbd> to toggle preview. (To use keymap, you have to disable the default [markdown preview](https://atom.io/packages/markdown-preview) package, otherwise there would be keymap conflict)
- <strong>Markdown Preview Enhanced: Customize CSS</strong>
  - Customize preview page css. You can edit styles inside `markdown-preview-enhanced-custom` section in `style.less` file.  
  - if you didn't see `markdown-preview-enhanced-custom` section in `style.less` file, you may need to run `Markdown Preview Enhanced: Customize CSS` command first.
- <strong>Markdown Preview Enhanced: Toc Create </strong>
  - Generate TOC
	 or simply insert ` <!-- toc -->` in editor (need preview toggled).
- <strong>Markdown Preview Enhanced: Toggle Scroll Sync </strong>
  - Enable/Disable scroll sync for preview.
- <strong>Markdown Preview Enhanced: Toggle Break On Single Newline </strong>
  - Enable/Disable breaking on single newline.
- <strong>Markdown Preview Enhanced: Insert New Slide </strong>  
- <strong>Markdown Preview Enhanced: Insert Table </strong>
- <strong>Markdown Preview Enhanced: Insert Page Break </strong>
- <strong> Markdown Preview Enhanced: Config Mermaid</strong>
  - edit `mermaid` init configuration.
- <strong> Markdown Preview Enhanced: Config Header Footer</strong>
  - **PDF** export header and footer configuration.
- <strong>Markdown Preview Enhanced: Image Helper</strong>  
	- Image Helper supports image url quick insertion, image paste, and image upload powered by [imgur](http://imgur.com/) and [sm.ms](https://sm.ms/).       
	(if **imgur** is blocked by **the Great Firewall**, then you can choose **sm.ms** instead).    
	- Keymap <kbd>ctrl+shift+i</kbd>    
	-  ![image_helper](https://cloud.githubusercontent.com/assets/1908863/15414603/c40b6556-1e6e-11e6-956c-090b5996ec87.gif)  

## Preview Context Menu
**Right click at preview to see the menu**

![context menu](https://cloud.githubusercontent.com/assets/1908863/14586062/18852988-0451-11e6-9cc0-578d54384926.gif)

- <strong> Open in Browser </strong>
  - Open HTML in browser
- **Export to Disk**
	- Export **HTML**, **PDF**, **PNG**, **JPEG** files.
- **Pandoc Document Export**
	- [doc](./docs/advanced-export.md)

## Extra
* **EBook**  
	More information about how to create ebook can be found [here](./docs/ebook.md).
* **Presentation Writer**  
	More information about how to create Presentation can be found [here](https://rawgit.com/shd101wyy/markdown-preview-enhanced/master/docs/presentation-intro.html).
* **Task List**  
	This package supports *Github Flavored* task list.  
	More information about how to create **task list** can be found [here](https://github.com/blog/1375-task-lists-in-gfm-issues-pulls-comments)
* **Smart Navigation**    
	You can quickly open another markdown file by clicking its link in preview.  
	![smart_navigation](https://cloud.githubusercontent.com/assets/1908863/15382175/e5f0a66e-1db9-11e6-9581-3f3ee8dc45dd.gif)  
* **Preview Auto Open**  
	Open preview pane automatically when you open a markdown file. You can disable this functionality from settings panel.

## For Developer
Manual installation instruction can be found [here](./docs/DEVELOPER.md).   
It is also very easy to write your own extension, more information can be found [here](./docs/extension.md).

## Thanks  
Thanks for everyone that supports this package!    

## TODO
- [ ] fix bugs
- [ ] modify css to make preview look nice
- [x] ePub output
- [x] support more image upload methods other than imgur (as imgur is blocked in some countries)
- [x] image paste [#30](https://github.com/shd101wyy/markdown-preview-enhanced/issues/30)
- [ ] pdf book generation [#56](https://github.com/shd101wyy/markdown-preview-enhanced/issues/56)
- [x] header and footer for pdf [57](https://github.com/shd101wyy/markdown-preview-enhanced/issues/57)

Thanks for using and supporting this package ;)

> UIUC License
