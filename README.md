# My Sublime Text 4 configuration

### Packages

##### Essential
* `Package Control`
* `Material Theme`
* `Emmet`
* `Babel`
* `DocBlockr`
* `DotENV`
* `EditorConfig`
* `SideBarEnhancements`
* `MoveTab`
* `A File Icon`

##### Optional
* `Babel Snippets`
* `JSX`
* `JS Custom`
* `Naomi`
* `Git blame`
* `GitGutter`
* `GraphQL`
* `TypeScript`
* `TypeScript Syntax`
* `Theme Nexus`
* `Theme Material`
* `Theme Agila`
* `JavaScript Snippets`
* `AdvancedNewFile`
* `SublimeLinter`
* `SublimeLinter-eslint`
* `SublimeLinter-flow`
* `SublimeLinter-stylelint`
* `SublimeLinter-csslint`
* `SyntaxHighlighting for PostCSS`
* `MarkdownPreview`
* `MDX syntax Highlighting`
* `Vue Syntax Highlight`

##### Fonts
* [FiraCode](https://github.com/tonsky/FiraCode) - font with programming ligatures


### Settings

```
{
  "ignored_packages": [
    "Vintage",
  ],
  "hide_tab_scrolling_buttons": true,
  "hide_new_tab_button": true,
  "show_encoding": true,
  "show_line_endings": true,
  "hardware_acceleration": "opengl",
  "remember_full_screen": true,
  "default_line_ending": "unix",
  "draw_white_space": "all",
  "font_face": "Fira Code",
  "font_options": [
    "subpixel_antialias",
    "gray_antialias"
  ],
  "font_size": 9,
  "tab_size": 2,
  "translate_tabs_to_spaces": true,
  "trim_trailing_white_space_on_save": true,
  "word_wrap": true,
  "binary_file_patterns": [
    "*.jpg",
    "*.jpeg",
    "*.png",
    "*.gif",
    "*.ttf",
    "*.tga",
    "*.dds",
    "*.ico",
    "*.eot",
    "*.pdf",
    "*.swf",
    "*.jar",
    "*.zip",
    ".svn/",
    ".git/",
    "dist/",
    "build/",
    "server-build/",
    "server-build-tmp/",
    "php/",
    "package-lock.json"
  ],
  "file_exclude_patterns": [
    "package-lock.json"
  ],
  "folder_exclude_patterns": [
    "bower_components",
    "node_modules",
    ".next"
  ],
  "theme": "Material-Theme.sublime-theme",
  "material_theme_compact_panel": true,
  "material_theme_contrast_mode": true,
  "material_theme_small_statusbar": true,
  "material_theme_bright_scrollbars": true,
  "material_theme_compact_sidebar": true,
  "material_theme_small_tab": true,
  "material_theme_tabs_autowidth": true,
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
    "keys": ["tab"], "command": "expand_abbreviation_by_tab", "context": [
      {
        "operand": "source.js.jsx",
        "operator": "equal",
        "match_all": true,
        "key": "selector"
      },
      {
        "key": "selection_empty",
        "operator": "equal",
        "operand": true,
        "match_all": true
      }
    ]
  },
  {
    "keys": ["tab"], "command": "next_field", "context": [
      {
        "key": "has_next_field",
        "operator": "equal",
        "operand": true
      }
    ]
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
