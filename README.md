# Sublime Text 3 configuration

### Packages

##### Essential
* `Package Control`
* `Theme Nexus`
* `Emmet`
* `Babel`
* `SublimeLinter`
* `SublimeLinter-eslint`
* `SublimeLinter-flow`
* `EditorConfig`
* `SideBarEnhancements`
* `MoveTab`

##### Optional
* `DocBlockr`
* `Naomi`
* `TypeScript`
* `TypeScript Syntax`
* `Theme Material`
* `Theme Agila`
* `JavaScript Snippets`
* `Babel Snippets`
* `AdvancedNewFile`
* `SublimeLinter-stylelint`
* `SublimeLinter-csslint`
* `SyntaxHighlighting for PostCSS`
* `Vue Syntax Highlight`

##### Fonts
* [FiraCode](https://github.com/tonsky/FiraCode) - font with programming ligatures


### Settings

```
{
  "file_exclude_patterns": [
    "package-lock.json"
  ],
  "folder_exclude_patterns": [
    "dist",
    "build",
    "server-build",
    "server-build-tmp",
    "php",
    "bower_components",
    "node_modules",
    ".next"
  ],
  "color_scheme": "Packages/Color Scheme - Default/Monokai.sublime-color-scheme",
  "default_line_ending": "unix",
  "draw_white_space": "all",
  "font_face": "Fira Code",
  "font_options": [
    "subpixel_antialias",
    "gray_antialias"
  ],
  "font_size": 11,
  "ignored_packages": [
    "Vintage"
  ],
  "tab_size": 2,
  "theme": "Nexus.sublime-theme",
  "translate_tabs_to_spaces": true,
  "trim_trailing_white_space_on_save": true,
  "word_wrap": true
}
```

### Key bindings

```
[
  {"keys": ["tab"], "command": "expand_abbreviation_by_tab", "context":
    [
      { "operand": "source.js", "operator": "equal", "match_all": true, "key": "selector" },
      { "match_all": true, "key": "selection_empty" },
      { "operator": "equal", "operand": false, "match_all": true, "key": "has_next_field" },
      { "operand": false, "operator": "equal", "match_all": true, "key": "auto_complete_visible" },
      { "match_all": true, "key": "is_abbreviation" }
    ]
  },
  {
    "keys": ["alt+shift+d"],
    "command": "duplicate_line",
  },
  {
    "keys": ["f10"],
    "command": "reindent",
    "args": {"single_line": false}
  },
  {
    "keys": ["ctrl+v"],
    "command": "paste_and_indent"
  },
  {
    "keys": ["ctrl+alt+v"],
    "command": "paste"
  },
  {
    "keys": ["ctrl+up"],
    "command": "scroll_lines",
    "args": {"amount": 1.0 }
  },
  {
    "keys": ["ctrl+down"],
    "command": "scroll_lines",
    "args": {"amount": -1.0 }
  },
  {
    "keys": ["alt+up"],
    "args": { "action": "increment_number_by_1" },
    "command": "run_emmet_action",
    "context": [{ "key": "emmet_action_enabled.increment_number_by_1" }]
  },
  {
    "keys": ["alt+down"],
    "args": { "action": "decrement_number_by_1" },
    "command": "run_emmet_action",
    "context": [{ "key": "emmet_action_enabled.decrement_number_by_1" }]
  },
  {
    "keys": ["alt+shift+up"],
    "args": {"forward": false},
    "command": "select_lines",
  },
  {
    "keys": ["alt+shift+down"],
    "args": {"forward": true} ,
    "command": "select_lines",
  },
]
```

#### Emmet settings

```
{
  "preferences": {
    // Change syntax of the comments inserted in the HTML
    "filter.commentAfter": "<!-- /<%= attr(\"id\", \"#\") %><%= attr(\"class\", \".\") %> -->",

    // Configure css property line-ending
    // "css.propertyEnd": "; ",
    "css.propertyEnd": ";\n",

    "css.autoInsertVendorPrefixes": false,

    // Align prefixed declarations by the original declaration
    "css.alignVendor": true,

    "css.gradient.fallback": false,

    "css.unitlessProperties" : "z-index, line-height, opacity, font-weight, zoom"
  },
  "snippets": {
    "html": {
      "filters": "html", // Add ", c" to generate comments
      "snippets": {
        // HTML Snippets
        "link:css" : "<link rel=\"stylesheet\" href=\"css/style.css\" type=\"text/css\" media=\"all\" />",
        "scriptsrc" : "<script src=\"js/|.js\"></script>",
        "st" : "style=\"|\"",
        "svg" : "<svg aria-hidden=\"true\" class=\"icon icon-svg|\">\n\t<use xlink:href=\"../../images/svg-sprite.svg#|\"></use>\n</svg>|"
      },
      "abbreviations": {
        // Custom Abbreviations
        "a": "<a href=\"#\">",
        "menu": "nav.nav>ul>li*>a",
        "soc":".socials>a[target=\"_blank\" class=\"socials-item $#\"]{$#}*",
        "input":"<input type=\"|\" name=\"|\" id=\"|\" placeholder=\"|\" />",
        "img": "<img src=\"../../images/|\" alt=\"\" />|",
      }
    },
    "css": {
      "filters": "html",
      "snippets": {
        // CSS snippets
        "scm": "/* ------------------------------------------------------------ *\\\n\t#$1\n\\* ------------------------------------------------------------ */\n$2",
        "scmm": "/* ==========================================================================\n\t#$1\n========================================================================== */\n$2",
        "mysrc": "\\'@{path}/|\\'",
        "fa": "filter:alpha(opacity:|); ",
        "bh": "backface-visibility: hidden;",
        "tras": "transition: all 0.3s;",
        "trano": "transform-origin: center top;",
        "wch": "will-change: transform, opacity, visibility;",
        "tran": "transform: |;",
        "va": "var(--|);"
      }
    }
  },
  "syntaxProfiles": {
    "html": "xhtml"
  }
}
```
