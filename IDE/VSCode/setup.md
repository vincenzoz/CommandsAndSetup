# Visual studio code configuration

## General

### Configure git bash terminal

File > Preferences > settings > Terminal integrated Automation shell: Window > Edit in settings.json

Modify the "terminal.integrated.shell.windows" entry with

```javascript
{
    "terminal.integrated.shell.windows": "C:\\path_to_git_folder\\Git\\bin\\bash.exe"
}
```

## Extensions / plugins

### File > Preferences > Extensions

* markdownlint
* Material Icon Theme
