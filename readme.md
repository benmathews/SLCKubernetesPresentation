# Marp presentation

https://github.com/marp-team/marp-cli/

## Install

```
npm install -g @marp-team/marp-cli
```

## Help

```
$ npx @marp-team/marp-cli -h
npx: installed 272 in 14.797s
Usage:
  marp [options] <files...>
  marp [options] -I <dir>

Basic Options:
  --version, -v      Show versions                                     [boolean]
  --help, -h         Show help                                         [boolean]
  --output, -o       Output file path (or directory when input-dir is passed)
                                                                        [string]
  --input-dir, -I    The base directory to find markdown and theme CSS  [string]
  --config-file, -c  Specify path to configuration file                 [string]
  --watch, -w        Watch input markdowns for changes                 [boolean]
  --server, -s       Enable server mode                                [boolean]
  --preview, -p      Open preview window (EXPERIMENTAL)                [boolean]

Converter Options:
  --pdf                Convert slide deck into PDF                     [boolean]
  --pptx               Convert slide deck into PowerPoint document     [boolean]
  --image              Convert the first slide page into an image file
                                               [string] [choices: "png", "jpeg"]
  --images             Convert slide deck into multiple image files
                                               [string] [choices: "png", "jpeg"]
  --jpeg-quality       Setting JPEG image quality         [number] [default: 85]
  --allow-local-files  Allow to access local files from Markdown while
                       converting PDF and image (NOT SECURE)           [boolean]

Template Options:
  --template          Choose template
                        [string] [choices: "bare", "bespoke"] [default: bespoke]
  --bespoke.osc       [Bespoke] Use on-screen controller
                                                       [boolean] [default: true]
  --bespoke.progress  [Bespoke] Use progress bar      [boolean] [default: false]

Meta Options:
  --title        Define title of the slide deck                         [string]
  --description  Define description of the slide deck                   [string]
  --url          Define canonical URL                                   [string]
  --og-image     Define Open Graph image URL                            [string]

Marp / Marpit Options:
  --engine     Select Marpit based engine by module name or path        [string]
  --html       Enable or disable HTML tag                              [boolean]
  --theme      Override theme by name or CSS file                       [string]
  --theme-set  Path to additional theme CSS files                        [array]
```
## Start

```
npx @marp-team/marp-cli -sw .
```

## Render PDF

```
npx @marp-team/marp-cli codefreshPresentation.md --pdf --allow-local-files
```