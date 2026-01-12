# starlight cli guide

starlight comes with a command line interface (cli) to run code, open learning guides, and work interactively.

## installation

1. make sure you have node.js installed.
2. clone or download starlight.
3. open a terminal in the starlight folder.

## usage

```bash
starlight <file.sl>        # run a starlight source file
starlight <file.md>        # view a markdown file directly in browser
starlight -v               # show cli version
starlight --help           # show help
starlight --learn          # open learning guide
starlight --writedirectly  # interactive editor mode
```

### options

* `-v` or `--version`
  show starlight cli version.

* `--help`
  display all available commands and usage.

* `--learn`
  opens the official starlight learning guide in your browser.

* `--writedirectly`
  opens an interactive editor for writing starlight code directly in the terminal.

## running files

to run a `.sl` file:

```bash
starlight myscript.sl
```

to view a markdown file directly:

```bash
starlight guide.md
```

* markdown files are rendered as html in your default browser.

## interactive editor (`--writedirectly`)

1. type code directly in the terminal.
2. use `:run` to execute the code.
3. syntax is highlighted as you type.
4. after execution, you can choose to save the code.

### example

```sl
let x = 5
let y = 10
sldeploy x + y   # outputs 15
```

* after typing `:run`, your code is evaluated immediately.
* saved files must be inside an existing folder.

## saving code from interactive mode

1. enter folder path when prompted.
2. enter file name. `.sl` extension is added automatically if missing.
3. your code is saved and can be run later using `starlight <file.sl>`.

## error handling

* syntax errors in parser stop execution without showing node.js stack trace.
* runtime errors show the message with line and column info.
* unexpected errors are also caught and displayed safely.

## cli workflow summary

| command                     | action                                                         |
| --------------------------- | -------------------------------------------------------------- |
| `starlight <file.sl>`       | run a starlight source file                                    |
| `starlight <file.md>`       | view a markdown file directly in browser                       |
| `starlight -v`              | show cli version                                               |
| `starlight --help`          | show this help guide                                           |
| `starlight --learn`         | open learning guide in browser                                 |
| `starlight --writedirectly` | interactive editor with immediate evaluation and optional save |

## additional features

* syntax highlighting in interactive mode.
* temporary files automatically cleaned up after execution.
* markdown files render beautifully in dark theme html.
* cross-platform support for opening files and urls.

