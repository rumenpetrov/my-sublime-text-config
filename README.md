# Sublime Text 3 configuration

## Packages
* `Package Control`
* `Theme Material`
* `Theme Nexus`
* `Emmet`
* `JavaScript Snippets`
* `Babel`
* `Babel Snippets`
* `AdvancedNewFile`
* `SublimeLinter`
* `SublimeLinter-eslint`

Optional:
* [FiraCode](https://github.com/tonsky/FiraCode) - font with programming ligatures

### Settings

```
{
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
    "node_modules/",
    "bower_components/"
  ],
  "color_scheme": "Packages/Color Scheme - Default/Monokai.sublime-color-scheme",
  "default_line_ending": "unix",
  "draw_white_space": "all",
  "font_face": "Fira Code",
  "font_options": [
    "gray_antialias"
  ],
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
    // change syntax of the comments inserted in the HTML
    "filter.commentAfter": "<!-- /<%= attr(\"id\", \"#\") %><%= attr(\"class\", \".\") %> -->",

    // remove the space between propery and value
    "css.valueSeparator": ": ",

    // add space after each declaration
    "css.propertyEnd": "; ",
    // "css.propertyEnd": ";\n",
    // "css.propertyEnd": ";",

    // disable vendor prefixes
    "css.autoInsertVendorPrefixes": false,

    // align prefixed declarations by the original declaration
    "css.alignVendor": true,

    "css.gradient.fallback": false,

    "css.unitlessProperties" : "z-index, line-height, opacity, font-weight, zoom"
  },
  "snippets": {
    "html": {
      // add/remove ", c" to add/remove comments
      "filters": "html",
      "snippets": {
        // My Snippets
        "logo" : "<a href=\"index.html\" class=\"logo\">\n\t<img src=\"../../images/logo2x.png\" alt=\"logo\" />\n</a>",
        "link:css" : "<link rel=\"stylesheet\" href=\"css/style.css\" type=\"text/css\" media=\"all\" />",
        "scriptsrc" : "<script src=\"js/|.js\"></script>",
        "paging" : "<nav class=\"paging\">\n\t<ul>\n\t\t<li class=\"prev\"><a href=\"#\">|</a></li>\n\t\t<li class=\"selected\"><a href=\"#\">1</a></li>\n\t\t<li><a href=\"#\">2</a></li>\n\t\t<li class=\"next\"><a href=\"#\"></a></li>\n\t</ul>\n</nav><!-- /.paging -->",
        "st" : "style=\"|\"",
        "svg" : "<svg aria-hidden=\"true\" class=\"icon icon-svg|\">\n\t<use xlink:href=\"../../images/svg-sprite.svg#|\"></use>\n</svg>|"
      },
      "abbreviations": {
        // My Abbreviations
        "a": "<a href=\"#\">",
        "menu": "nav.nav>ul>li*>a",
        "soc":".socials>a[target=\"_blank\" class=\"socials-item $#\"]{$#}*",
        "input":"<input type=\"|\" name=\"|\" id=\"|\" placeholder=\"|\" />",
        "img": "<img src=\"../../images/|\" alt=\"\" />|",
        "bread": "nav.breadcrumbs>ul>li>a^+li"
      }
    },
    "css": {
      "filters": "html",
      "snippets": {
        // Custom Comments Snippet
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

#### Emmet keybindings

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
]
```
