# Introduction

Orange markup language

#TODO

| Markdown               | AsciiDoc               | HTML               | ORML      | Style                    |
| ---------------------- | ---------------------- | ------------------ | --------- | ------------------------ |
| `**...**` or `__...__` | `*...*`                | `<b>...</b>`       | `[b ...]` | **Bold**                 |
| `*...*` or `_..._`     | `_..._`                | `<i>...</i>`       | `[i ...]` | _Italic_                 |
| `<u>...</u>`           | `[.underline]#...#`    | `<u>...</u>`       | `[u ...]` | <u>Underlined</u>        |
| `~~...~~`              | `[.line-through]#...#` | `<s>...</s>`       | `[s ...]` | ~~Strike~~               |
| `<mark>...</mark>`     | `#...#`                | `<mark>...</mark>` | `[% ...]` | <mark>Highlighted</mark> |
| `<sub>...</sub>`       | `~...~`                | `<sub>...</sub>`   | `[, ...]` | <sub>subscripted</sub>   |
| `<sup>...</sup>`       | `^...^`                | `<sup>...</sup>`   | `[^ ...]` | <sup>superscripted</sup> |
| `` `...` ``            | `` `...` ``            | `<pre>...</pre>`   | `[$ ...]` | `Monospace`              |

# HTML

| HTML Tag                                                       | Description               |
| -------------------------------------------------------------- | ------------------------- |
| [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp) | Defines the document type |

## Alternative tags

| HTML tags                                                                                        | ORML alternative tags              | Description                                                            |
| ------------------------------------------------------------------------------------------------ | ---------------------------------- | ---------------------------------------------------------------------- |
| [`<mark>...</mark>`](https://www.w3schools.com/tags/tag_mark.asp)                                | `[% ...]`                          | Defines marked/highlighted text                                        |
| [`<pre>...</pre>`](https://www.w3schools.com/tags/tag_pre.asp)                                   | `[$ ...]`                          | Defines monospace text (preformatted text)                             |
| [`<small>...</small>`](https://www.w3schools.com/tags/tag_small.asp)                             | `[. ...]`                          | Defines smaller text                                                   |
| [`<sub>...</sub>`](https://www.w3schools.com/tags/tag_sub.asp)                                   | `[, ...]`                          | Defines subscripted text                                               |
| [`<sup>...</sup>`](https://www.w3schools.com/tags/tag_sup.asp)                                   | `[^ ...]`                          | Defines superscripted text                                             |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)                                   | `[# ...]`                          | Defines a comment                                                      |
|                                                                                                  |                                    |                                                                        |
| [`<strong>...</strong>`](https://www.w3schools.com/tags/tag_strong.asp)                          | `[* ...]`                          | Defines important text                                                 |
| [`<em>...</em>`](https://www.w3schools.com/tags/tag_em.asp)                                      | `[~ ...]`                          | Defines emphasized text                                                |
| [`<ins>...</ins>`](https://www.w3schools.com/tags/tag_ins.asp)                                   | `[+ ...]`                          | Defines a text that has been inserted into a document                  |
| [`<del>...</del>`](https://www.w3schools.com/tags/tag_del.asp)                                   | `[- ...]`                          | Defines text that has been deleted from a document                     |
|                                                                                                  |                                    |                                                                        |
| [`<address>...</address>`](https://www.w3schools.com/tags/tag_address.asp)                       | `[@ ...]`                          | Defines contact information for the author/owner of a document/article |
| [`<abbr>...</abbr>`](https://www.w3schools.com/tags/tag_abbr.asp)                                | `[A ...]`                          | Defines an abbreviation or an acronym                                  |
| [`<code>...</code>`](https://www.w3schools.com/tags/tag_code.asp)                                | `[C ...]`                          | Defines a piece of computer code                                       |
| [`<cite>...</cite>`](https://www.w3schools.com/tags/tag_cite.asp)                                | `[T ...]`                          | Defines the title of a work                                            |
| [`<dfn>...</dfn>`](https://www.w3schools.com/tags/tag_dfn.asp)                                   | `[D ...]`                          | Specifies a term that is going to be defined within the content        |
| [`<kbd>...</kbd>`](https://www.w3schools.com/tags/tag_kbd.asp)                                   | `[K ...]`                          | Defines keyboard input                                                 |
| [`<var>...</var>`](https://www.w3schools.com/tags/tag_var.asp)                                   | `[V ...]`                          | Defines a variable                                                     |
|                                                                                                  |                                    |                                                                        |
| [`<samp>...</samp>`](https://www.w3schools.com/tags/tag_samp.asp)                                | `[; ...]`                          | Defines sample output from a computer program                          |
| [`<div>...</div>`](https://www.w3schools.com/tags/tag_div.asp)                                   | `[/ ...]`                          | Defines a section in a document                                        |
|                                                                                                  |                                    |                                                                        |
| [`<input type="checkbox" disabled="">`](https://www.w3schools.com/tags/tag_input.asp)            | `[ ]`                              | Defines a unchecked checkbox                                           |
| [`<input type="checkbox" disabled="" checked="">`](https://www.w3schools.com/tags/tag_input.asp) | `[X]`                              | Defines a checked checkbox                                             |
|                                                                                                  |                                    |                                                                        |
| [`<h1>...</h1>` to `<h6>...</h6>`](https://www.w3schools.com/tags/tag_hn.asp)                    | `[= ...]` to `[====== ...]`        | Defines a headings #TODO                                               |
| [`<blockquote>...</blockquote>`](https://www.w3schools.com/tags/tag_blockquote.asp)              | `[> ...]`                          | Defines a section that is quoted from another source                   |
| [`<hr>`](https://www.w3schools.com/tags/tag_hr.asp)                                              | `[---]`                            | Defines a thematic change in the content #TODO                         |
| [`<a href="URL">...</a>`](https://www.w3schools.com/tags/tag_a.asp)                              | `["URL" ...]` or `['URL' ...]`     | Defines a hyperlink #TODO                                              |
| #TODO                                                                                            | `[! "URL" ...]` or `[! 'URL' ...]` | #TODO                                                                  |

# Markdown

No [indented code blocks](https://github.github.com/gfm/#indented-code-blocks)

## Simple Code

Support [code spans](https://github.github.com/gfm/#code-spans) and [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks) With out `~`

## Simple list

Support [lists](https://github.github.com/gfm/#lists) and [list items](https://github.github.com/gfm/#list-items) but only `-` and `NUMBER.` support

## Simple tables

Support [table](https://github.github.com/gfm/#tables-extension-)

## Autolinks

Support [autolinks](https://github.github.com/gfm/#autolinks-extension-)

# Backslash escapes

#TODO

| Escapes  | Charater | Name                  |
| -------- | -------- | --------------------- |
| `\\`     | `\`      | Backslash             |
| `\&`     | `&`      | Ampersand             |
|          |          |                       |
| `\[`     | `[`      | Left square brackets  |
| `\]`     | `]`      | Right square brackets |
| `\=`     | `=`      | Equals sign           |
| `\'`     | `'`      | Apostrophe            |
| `\"`     | `"`      | Quotation marks       |
| `\{`     | `{`      | Left curly brackets   |
| `\}`     | `}`      | Right curly brackets  |
|          |          |                       |
| `` \` `` | `` ` ``  | Grave accent          |
|          |          |                       |
| `\-`     | `-`      | Hyphen/minus          |
| `\.`     | `.`      | Period                |
|          |          |                       |
| `\\|`    | `\|`     | Vertical bar          |
| `\-`     | `-`      | Hyphen/minus          |
| `\=`     | `=`      | Equals sign           |
