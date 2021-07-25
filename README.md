# Orange markup language

| Markdown               | AsciiDoc               | HTML               | ORML      | Style                    |
| ---------------------- | ---------------------- | ------------------ | --------- | ------------------------ |
| `**...**` or `__...__` | `*...*`                | `<b>...</b>`       | `[b ...]` | **Bold**                 |
| `*...*` or `_..._`     | `_..._`                | `<i>...</i>`       | `[i ...]` | _Italic_                 |
| `<u>...</u>`           | `[.underline]#...#`    | `<u>...</u>`       | `[u ...]` | U̲n̲d̲e̲r̲l̲i̲n̲e̲d̲               |
| `~~...~~`              | `[.line-through]#...#` | `<s>...</s>`       | `[s ...]` | ~~Strike~~               |
| `<mark>...</mark>`     | `#...#`                | `<mark>...</mark>` | `[% ...]` | `𝐇𝐢𝐠𝐡𝐥𝐢𝐠𝐡𝐭𝐞𝐝`            |
| `<sub>...</sub>`       | `~...~`                | `<sub>...</sub>`   | `[, ...]` | <sub>subscripted</sub>   |
| `<sup>...</sup>`       | `^...^`                | `<sup>...</sup>`   | `[^ ...]` | <sup>superscripted</sup> |
| `` `...` ``            | `` `...` ``            | `<pre>...</pre>`   | `[$ ...]` | `Monospace`              |

## 1. HTML

```html
<tagname attribute="value" more-attribute="value">content</tagname>
```

```orml
[tagname attribute="value" more-attribute="value" content]
```

```html
<tagname attribute="value" more-attribute="value">
```

```orml
[tagname attribute="value" more-attribute="value"]
```

| HTML Tag                                                       | Description               |
| -------------------------------------------------------------- | ------------------------- |
| [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp) | Defines the document type |

### 1.1. Alternative tags

| HTML tags                                                                                        | ORML alternative tags          | Description                                                                        |
| ------------------------------------------------------------------------------------------------ | ------------------------------ | ---------------------------------------------------------------------------------- |
| [`<hr>` (`<hr>...</hr>`)](https://www.w3schools.com/tags/tag_hr.asp)                             | `[---]` (`[--- ...]`)          | Defines a thematic change in the content                                           |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)                                   | `[# ...]`                      | Defines a comment                                                                  |
|                                                                                                  |                                |                                                                                    |
| [`<strong>...</strong>`](https://www.w3schools.com/tags/tag_strong.asp)                          | `[* ...]`                      | Defines important text                                                             |
| [`<em>...</em>`](https://www.w3schools.com/tags/tag_em.asp)                                      | `[_ ...]`                      | Defines emphasized text                                                            |
| [`<ins>...</ins>`](https://www.w3schools.com/tags/tag_ins.asp)                                   | `[+ ...]`                      | Defines a text that has been inserted into a document                              |
| [`<del>...</del>`](https://www.w3schools.com/tags/tag_del.asp)                                   | `[- ...]`                      | Defines text that has been deleted from a document                                 |
| [`<mark>...</mark>`](https://www.w3schools.com/tags/tag_mark.asp)                                | `[% ...]`                      | Defines marked/highlighted text                                                    |
| [`<pre>...</pre>`](https://www.w3schools.com/tags/tag_pre.asp)                                   | `[$ ...]`                      | Defines monospace text (preformatted text)                                         |
| [`<small>...</small>`](https://www.w3schools.com/tags/tag_small.asp)                             | `[. ...]`                      | Defines smaller text                                                               |
| [`<sub>...</sub>`](https://www.w3schools.com/tags/tag_sub.asp)                                   | `[, ...]`                      | Defines subscripted text                                                           |
| [`<sup>...</sup>`](https://www.w3schools.com/tags/tag_sup.asp)                                   | `[^ ...]`                      | Defines superscripted text                                                         |
|                                                                                                  |                                |                                                                                    |
| [`<address>...</address>`](https://www.w3schools.com/tags/tag_address.asp)                       | `[@ ...]`                      | Defines contact information for the author/owner of a document/article             |
| [`<abbr>...</abbr>`](https://www.w3schools.com/tags/tag_abbr.asp)                                | `[A ...]`                      | Defines an abbreviation or an acronym                                              |
| [`<cite>...</cite>`](https://www.w3schools.com/tags/tag_cite.asp)                                | `[T ...]`                      | Defines the title of a work                                                        |
| [`<code>...</code>`](https://www.w3schools.com/tags/tag_code.asp)                                | `[C ...]`                      | Defines a piece of computer code                                                   |
| [`<dfn>...</dfn>`](https://www.w3schools.com/tags/tag_dfn.asp)                                   | `[D ...]`                      | Specifies a term that is going to be defined within the content                    |
| [`<kbd>...</kbd>`](https://www.w3schools.com/tags/tag_kbd.asp)                                   | `[K ...]`                      | Defines keyboard input                                                             |
| [`<blockquote>...</blockquote>`](https://www.w3schools.com/tags/tag_blockquote.asp)              | `[Q ...]`                      | Defines a section that is quoted from another source                               |
| [`<samp>...</samp>`](https://www.w3schools.com/tags/tag_samp.asp)                                | `[S ...]`                      | Defines sample output from a computer program                                      |
| [`<var>...</var>`](https://www.w3schools.com/tags/tag_var.asp)                                   | `[V ...]`                      | Defines a variable                                                                 |
|                                                                                                  |                                |                                                                                    |
| [`<span>...</span>`](https://www.w3schools.com/tags/tag_span.asp)                                | `[; ...]`                      | Defines a section in a document                                                    |
|                                                                                                  |                                |                                                                                    |
| [`<a href="URL">...</a>`](https://www.w3schools.com/tags/tag_a.asp)                              | `["URL" ...]` or `['URL' ...]` | Defines a hyperlink                                                                |

<!--
Removed:

| HTML tags                                                                                        | ORML alternative tags          | Description                                                                        |
| ------------------------------------------------------------------------------------------------ | ------------------------------ | ---------------------------------------------------------------------------------- |
| [`<h1>...</h1>` to `<h6>...</h6>`](https://www.w3schools.com/tags/tag_hn.asp)                    | `[= ...]` to `[====== ...]`    | Defines a headings (the number of `=` character to the header level is correspond) |
| [`<div>...</div>`](https://www.w3schools.com/tags/tag_div.asp)                                   | `[/ ...]`                      | Defines a section in a document                                                    |
-->

### 1.2. Quick tags

| HTML tags                                                                                        | ORML quick tags | Description                  |
| ------------------------------------------------------------------------------------------------ | --------------- | ---------------------------- |
| [`<input type="checkbox" disabled="">`](https://www.w3schools.com/tags/tag_input.asp)            | `[ ]`           | Defines a unchecked checkbox |
| [`<input type="checkbox" disabled="" checked="">`](https://www.w3schools.com/tags/tag_input.asp) | `[X]`           | Defines a checked checkbox   |

### 1.3. Extend tags

| HTML tags                          | ORML alternative tags              | Description            |
| ---------------------------------- | ---------------------------------- | ---------------------- |
| `<span class="spoiler">...</span>` | `[? ...]`                          | Defines a spoiler text |
| #TODO                              | `[! "URL" ...]` or `[! 'URL' ...]` | Auto media             |

#TODO
[Bibliography](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#bibliography)
[Footnotes](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#section-footnotes)

## 2. Markdown

No [indented code blocks](https://github.github.com/gfm/#indented-code-blocks).

### 2.1. Autolinks

ORML support [autolinks (extension)](https://github.github.com/gfm/#autolinks-extension-) (**not the original [autolinks](https://github.github.com/gfm/#autolinks)**) exactly like from [GFM](https://github.github.com/gfm)

### 2.2. Lists

ORML support [list items](https://github.github.com/gfm/#list-items)
and [lists](https://github.github.com/gfm/#lists) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [bullet list marker](https://github.github.com/gfm/#bullet-list-marker) is a `-` character (and not a `+` nor a `*` character).
- An [ordered list marker](https://github.github.com/gfm/#ordered-list-marker) is a sequence of 1–9 arabic digits (`0-9`), followed by a `.` character (and not followed by a `)` character).

### 2.3. Tables

ORML support [tables](https://github.github.com/gfm/#tables-extension-) from [GFM](https://github.github.com/gfm) but with the following difference:
- `:` => `=`
- Foot.

### 2.4. Codes

ORML support [code spans](https://github.github.com/gfm/#code-spans)
and [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks) from [GFM](https://github.github.com/gfm) but with the following difference:
- A code fence is a sequence of at least three consecutive `` ` `` characters (and not `~` characters)

### 2.5. Backslash escapes

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
