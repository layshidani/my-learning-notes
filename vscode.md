# VSCode

## ShortCuts
* [VSCode Shortcuts - Brad Traversy](https://gist.github.com/bradtraversy/b28a0a361880141af928ada800a671d9)
* [Linux](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-linux.pdf)
* [Microsoft](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-windows.pdf)
* [MacOS](https://code.visualstudio.com/shortcuts/keyboard-shortcuts-macos.pdf)


## Extensions
### Tools
* [Bracket Pair Colorizer 2](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer-2)
* [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
* [Turbo console.log](https://marketplace.visualstudio.com/items?itemName=ChakrounAnas.turbo-console-log)
* [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
* [change-case](https://marketplace.visualstudio.com/items?itemName=wmaurer.change-case)
* [VS Intellicode](https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.vscodeintellicode)

### JS
* [Code Runner](https://marketplace.visualstudio.com/items?itemName=formulahendry.code-runner)

### HTML
* [Auto rename tag](https://marketplace.visualstudio.com/items?itemName=formulahendry.auto-rename-tag)


### CSS
* [Colorize](https://marketplace.visualstudio.com/items?itemName=kamikillerto.vscode-colorize)
* [VSCode Color Peeker](https://marketplace.visualstudio.com/items?itemName=lihui.vs-color-picker)

### Markdown
* [Markdown Lint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
* [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)

### Tema e personalização
* [Drácula](https://marketplace.visualstudio.com/items?itemName=dracula-theme.theme-dracula)
* [Material Icon Theme](https://marketplace.visualstudio.com/items?itemName=PKief.material-icon-theme)

## Configuração

*settings.json*
```JSON
{
    "workbench.colorTheme": "Dracula",
    "workbench.iconTheme": "material-icon-theme",
    "material-icon-theme.folders.color": "#90a4ae",
    "editor.fontSize": 16,
    "editor.tabSize": 2,
    "editor.detectIndentation": true,
    "editor.insertSpaces": true,
    "editor.fontFamily": "'Fira Code',  monospace",
    "editor.fontLigatures": true,
    "[javascript]": {
        "editor.formatOnSave": true
    },
    "files.autoSave": "onWindowChange",
    "colorize.ignore_search_variables_info": true,
    "files.insertFinalNewline": true,
    "files.trimTrailingWhitespace": true,
    "editor.wordWrap": "on",
    "liveServer.settings.donotShowInfoMsg": true,
    "window.zoomLevel": 0,
    "explorer.confirmDragAndDrop": false,
    "shell.terminal.integrated.shell.osx": "zsh",
    "editor.minimap.renderCharacters": false,
    "editor.minimap.maxColumn": 200,
    "editor.minimap.showSlider": "always",
    // "editor.renderWhitespace": "all",
    "editor.smoothScrolling": true,
    "editor.cursorBlinking": "phase",
    "editor.cursorSmoothCaretAnimation": true,
    "emmet.includeLanguages": {
        "javascript": "javascriptreact",
    },
}
```

## Fonte com ligatura
[FiraCode](https://github.com/tonsky/FiraCode)

Instale conforme as instruções do link acima. 
