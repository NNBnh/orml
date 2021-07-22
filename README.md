Lazy Markup Language
====================

`#TODO`

| Markdown               | AsciiDoc               | HTML               | LZML      | Style                    |
| ---------------------- | ---------------------- | ------------------ | --------- | ------------------------ |
| `**...**` or `__...__` | `*...*`                | `<b>...</b>`       | `[b ...]` | **Bold**                 |
| `*...*` or `_..._`     | `_..._`                | `<i>...</i>`       | `[i ...]` | _Italic_                 |
| `<u>...</u>`           | `[.underline]#...#`    | `<u>...</u>`       | `[u ...]` | <u>Underlined</u>        |
| `~~...~~`              | `[.line-through]#...#` | `<s>...</s>`       | `[s ...]` | ~~Strike~~               |
| `<mark>...</mark>`     | `#...#`                | `<mark>...</mark>` | `[h ...]` | <mark>Highlighted</mark> |
| `<sub>...</sub>`       | `~...~`                | `<sub>...</sub>`   | `[, ...]` | <sub>subscripted</sub>   |
| `<sup>...</sup>`       | `^...^`                | `<sup>...</sup>`   | `[^ ...]` | <sup>superscripted</sup> |
| `` `...` ``            | `` `...` ``            | `<pre>...</pre>`   | `[m ...]` | `Monospace`              |

https://www.w3schools.com/tags/ref_byfunc.asp



Removes
-------

`#TODO`

| HTML Tag                                                       | Description                 |
| -------------------------------------------------------------- | --------------------------- |
| [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp) | Defines the document type   |
| [`<html>`](https://www.w3schools.com/tags/tag_html.asp)        | Defines an HTML document    |
| [`<body>`](https://www.w3schools.com/tags/tag_body.asp)        | Defines the document's body |



Replace
-------

`#TODO`

| HTML tag                                                            | LZML Tag  | Description                                          |
| ------------------------------------------------------------------- | --------- | ---------------------------------------------------- |
| [`<mark>`](https://www.w3schools.com/tags/tag_mark.asp)             | `[h]`     | Defines Highlighted text                             |
| [`<sub>`](https://www.w3schools.com/tags/tag_sub.asp)               | `[,]`     | Defines subscripted text                             |
| [`<sup>`](https://www.w3schools.com/tags/tag_sup.asp)               | `[^]`     | Defines superscripted text                           |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)      | `[#]`     | Defines a comment                                    |
| [`<abbr>`](https://www.w3schools.com/tags/tag_abbr.asp)             | `[a]`     | Defines an abbreviation or an acronym                |
| [`<pre>`](https://www.w3schools.com/tags/tag_pre.asp)               | `[m]`     | Defines monospace text (preformatted text)           |
| [`<kbd>`](https://www.w3schools.com/tags/tag_kbd.asp)               | `[k]`     | Defines keyboard input                               |
| [`<var>`](https://www.w3schools.com/tags/tag_var.asp)               | `[v]`     | Defines a variable                                   |
| [`<blockquote>`](https://www.w3schools.com/tags/tag_blockquote.asp) | `[quote]` | Defines a section that is quoted from another source |

| HTML                                                                | LZML          | Description         |
| ------------------------------------------------------------------- | ------------- | ------------------- |
| [`<a href="URL">...</a>`](https://www.w3schools.com/tags/tag_a.asp) | `["URL" ...]` | Defines a hyperlink |



Additions
---------

### Alternative syntax

`#TODO`

| HTML tag                                                      | LZML tag         | LZML alternative        | Description                                                                                                                                                                                                                                                                                                                                                                                                             |
| ------------------------------------------------------------- | ---------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [`<h1>` to `<h6>`](https://www.w3schools.com/tags/tag_hn.asp) | `[h1]` to `[h6]` | `= ...` to `====== ...` | An ATX heading consists of a string of characters, parsed as inline content, between an opening sequence of 1–6 unescaped `=` characters. The opening `=` character may be indented any number of spaces or tabs. The raw contents of the heading are stripped of leading and trailing spaces before being parsed as inline content. The heading level is equal to the number of `=` characters in the opening sequence |
| [`<hr>`](https://www.w3schools.com/tags/tag_hr.asp)           | `[hr]`           | `---`                   | A line consisting of any indentation, followed by a sequence of three or more matching `-` characters, each followed optionally by any number of spaces or tabs, forms a horizontal rule                                                                                                                                                                                                                                |
| [`<br>`](https://www.w3schools.com/tags/tag_br.asp)           | `[br]`           | `\n`                    | Hard line breaks                                                                                                                                                                                                                                                                                                                                                                                                        |

### Auto media `#TODO`

`[! "URL" ...]`

### Code spans

A backtick string is a string of one or more backtick characters (`\``) that is neither preceded nor followed by a backtick.

A code span begins with a backtick string and ends with a backtick string of equal length. The contents of the code span are the characters between the two backtick strings, normalized in the following ways:
- First, line endings are converted to spaces.
- If the resulting string both begins and ends with a space character, but does not consist entirely of space characters, a single space character is removed from the front and back. This allows you to include code that begins or ends with backtick characters, which must be separated by whitespace from the opening or closing backtick strings.

### Simple lists `#TODO`

- https://github.github.com/gfm/#list-items
- https://github.github.com/gfm/#lists

| Starter                         | Description                |
| ------------------------------- | -------------------------- |
| `-`                             | Bullet points              |
| `[ ]`, `[x]`                    | Checkbox                   |
| `0.`, `1.`, `2.`, `3.`, ...     | Decimal numbers            |
| `a.`, `b.`, `c.`, `d.`, ...     | Alphabetically (lowercase) |
| `A.`, `B.`, `C.`, `D.`, ...     | Alphabetically (uppercase) |
| `i.`, `ii.`, `iii.`, `iv.`, ... | Roman numbers (lowercase)  |
| `I.`, `II.`, `III.`, `IV.`, ... | Roman numbers (uppercase)  |

### Simple tables `#TODO`

- https://github.github.com/gfm/#tables-extension-
- https://www.pml-lang.dev/docs/reference_manual/index.html#node_admon
- https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#tables



Backslash escapes
-----------------

`#TODO`

| Escapes | Charater | Name                  |
| ------- | -------- | --------------------- |
| `\\\\`  | `\\`     | Backslash             |
| `\\&`   | `&`      | Ampersand             |
| `\\[`   | `[`      | Left square brackets  |
| `\\]`   | `]`      | Right square brackets |
| `\\=`   | `=`      | Equals sign           |
| `\\'`   | `'`      | Apostrophe            |
| `\\"`   | `"`      | Quotation marks       |
| `\\\``  | `\``     | Grave accent          |
| `\\-`   | `-`      | Hyphen/minus          |
| `\\\|`  | `\|`     | Vertical bar          |
| `\\n`   | ↵        | Hard line breaks      |
