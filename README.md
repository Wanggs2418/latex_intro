## LaTeX配置说明

### 1.VScode

**安装**

微软编辑器：vscode https://code.visualstudio.com/docs/?dv=win

**配置**

 安装LaTeX Workshop插件

settings.json 路径为：C:\Users\Administrator\AppData\Roaming\Code\User

vs用`Ctrl+p`后进行搜索settings即可。

注意现在发行的包大多以`pdfTeX`为默认的引擎，此此处设置`xelatex`为首位。

```json

        "latex-workshop.latex.recipes": [{
        "name": "xelatex",
        "tools": [
            "xelatex"
        ]
      }, {
        "name": "latexmk",
        "tools": [
            "latexmk"
        ]
      },
      
      {
        "name": "pdflatex -> bibtex -> pdflatex*2",
        "tools": [
            "pdflatex",
            "bibtex",
            "pdflatex",
            "pdflatex"
        ]
      }
      ],
      "latex-workshop.latex.tools": [{
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOC%"
      ]
      }, {
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
      }, {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
      }, {
      "name": "bibtex",
      "command": "bibtex",
      "args": [
        "%DOCFILE%"
      ]
      }],
      "latex-workshop.view.pdf.viewer": "tab",
      "latex-workshop.latex.clean.fileTypes": [
      "*.aux",
      "*.bbl",
      "*.blg",
      "*.idx",
      "*.ind",
      "*.lof",
      "*.lot",
      "*.out",
      "*.toc",
      "*.acn",
      "*.acr",
      "*.alg",
      "*.glg",
      "*.glo",
      "*.gls",
      "*.ist",
      "*.fls",
      "*.log",
      "*.fdb_latexmk"
      ],
      "editor.minimap.enabled": false,
```

### 2.TeX

具体安装步骤可参考：install-latex-guide-zh-cn

TeX发行版与编辑器

| 操作系统 |  发行版  |  编辑器   |
| :------: | :------: | :-------: |
|   通用   | TeX Live | TeXworks  |
| windows  |  MkiTeX  | TeXstudio |
|  Mac OS  | Mac TeX  |  TeXShop  |

Tex Live的下载与安装

建议直接下载ISO镜像，节约时间。符清华大学镜像列表

https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/

对下载后的*.iso文件直接进行解压缩，然后进行安装。用管理员模式（右键-->Run as Administrator）运行install-tl-windows.bat文件，先修改安装的路径。**而后进入第一个框框后点击Advanced，为了控制一下TeX Live占用的内存大小，我们可以选择修改N. of collections选项，并根据个人需要，去掉Texworks(比较老的编辑器，不推荐)以及部分我们日常不会使用的语言包，例如阿拉伯语、斯洛伐克语等等。**

而后经过漫长的等待安装即可。。。

### 3.查看帮助文档

```shell
#查看XeCJK宏包帮助文档
texdoc XeCJK
```

### 4.宏包的安装
通过源安装宏包，
`cmd`状态下：
```cmd
tlmgr install package_name
```
不到万不得已，不手动安装宏包。