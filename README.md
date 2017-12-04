# vscode-stylelint

[![Build Status](https://travis-ci.org/shinnn/vscode-stylelint.svg?branch=master)](https://travis-ci.org/shinnn/vscode-stylelint)

A [Visual Studio Code](https://code.visualstudio.com/) extension to lint [CSS](https://www.w3.org/Style/CSS/)/[SCSS](http://sass-lang.com/documentation/file.SASS_REFERENCE.html#syntax)/[Less](http://lesscss.org/) with [stylelint](http://stylelint.io/)

![screenshot](screenshot.png)

## Installation

1. Run [`Install Extension`](https://code.visualstudio.com/docs/editor/extension-gallery#_install-an-extension) command from [Command Palette](https://code.visualstudio.com/Docs/editor/codebasics#_command-palette).
2. Search and choose `stylelint`.

See the [extension installation guide](https://code.visualstudio.com/docs/editor/extension-gallery) for details.

## Usage

1. Enable the linter in the VS Code [settings](https://code.visualstudio.com/docs/customization/userandworkspace), while disabling the built-in CSS and SCSS linter:

```json
{
  "stylelint.enable": true,
  "css.validate": false,
  "scss.validate": false
}
```

2. Add some basic rules, based on [stylelint-config-recommended
](https://github.com/stylelint/stylelint-config-recommended/blob/master/index.js)
```json
"stylelint.config": {
  "rules": {

      "at-rule-no-unknown": true,
      "block-no-empty": true,
      "color-no-invalid-hex": true,
      "comment-no-empty": true,
      "declaration-block-no-duplicate-properties": [
        true,
        {
          "ignore": ["consecutive-duplicates-with-different-values"]
        }
      ],
      "declaration-block-no-redundant-longhand-properties": true,
      "declaration-block-no-shorthand-property-overrides": true,
      "font-family-no-duplicate-names": true,
      "font-family-no-missing-generic-family-keyword": true,
      "function-calc-no-unspaced-operator": true,
      "function-linear-gradient-no-nonstandard-direction": true,
      "keyframe-declaration-no-important": true,
      "media-feature-name-no-unknown": true,
      "no-descending-specificity": true,
      "no-duplicate-at-import-rules": true,
      "no-duplicate-selectors": true,
      "no-empty-source": true,
      "no-extra-semicolons": true,
      "no-invalid-double-slash-comments": true,
      "property-no-unknown": true,
      "selector-pseudo-class-no-unknown": true,
      "selector-pseudo-element-no-unknown": true,
      "selector-type-no-unknown": true,
      "string-no-newline": true,
      "unit-no-unknown": true
    }
   }
```

### Configurations

*In addition to the VS Code settings mentioned below, you can set the config by adding [stylelint configuration files](https://github.com/stylelint/stylelint/blob/master/docs/user-guide/configuration.md#configuration) to the workspace directory.*

#### stylelint.enable

Type: `Boolean`  
Default: `true`

Control whether [stylelint](https://github.com/stylelint/stylelint/) is enabled for CSS/SCSS/Less files or not.

#### stylelint.configOverrides

Type: `Object`  
Default: `null`

Will be directly passed to [`configOverrides`](https://github.com/stylelint/stylelint/blob/master/docs/user-guide/node-api.md#configoverrides) option.

#### stylelint.config

Type: `Object`  
Default: `null`

Will be directly passed to [`config`](https://github.com/stylelint/stylelint/blob/master/docs/user-guide/node-api.md#config) option. Note that if you set `config` option, this plugin ignores all the stylelint configuration files.

#### stylelint.additionalDocumentSelectors

Type: `Array`  
Default: `[]`

Document types that you can use to run stylelint against if you are using CSS inside document types like: `javascriptreact`, `typescriptreact` or `vue`.

## License

Copyright (c) 2015 - 2017 [Shinnosuke Watanabe](https://github.com/shinnn)

Licensed under [the MIT License](./LICENSE).
