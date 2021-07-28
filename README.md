<h1 align="center">Orange markup language</h1>
<p align="center">A powerful and simple markup language</p>
<p align="center"><img src="https://emojipedia-us.s3.dualstack.us-west-1.amazonaws.com/thumbs/160/twitter/282/tangerine_1f34a.png"></p>
<p align="center"><a href="https://github.com/NNBnh/orml/blob/main/LICENSE"><img src="https://img.shields.io/github/license/NNBnh/orml?labelColor=F49104&color=F49104&style=for-the-badge" alt="License: GPL-3.0"></a> <!-- <a href="https://gist.github.com/NNBnh/9ef453aba3efce26046e0d3119dab5a7#development-completed"><img src="https://img.shields.io/badge/development-completed-%23F49104.svg?labelColor=F49104&style=for-the-badge&logoColor=FFFFFF" alt="Development completed"></a> --></p>

## 💡 About

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

### 📔 Story

<!-- 
> 1. [ ] Lazy markup language (LZML)
> 2. [ ] Unoriginal markup language (UOML)
> 3. [ ] _"Original"_ markup language (ORML)
> 4. [x] Orange markup language (ORML)
-->

### ✨ Features

## 🚀 Setup

### 🧾 Dependencies

### 📥 Installation

## ⌨️ Usage

## 📙 Reference

### 📜 1. HTML power

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

No [`<!DOCTYPE>`](https://www.w3schools.com/tags/tag_doctype.asp).

#### 🏷️ 1.1. Alternative tags

| HTML tags                                                                                        | ORML alternative tags          | Description                                                                        |
| ------------------------------------------------------------------------------------------------ | ------------------------------ | ---------------------------------------------------------------------------------- |
| [`<strong>...</strong>`](https://www.w3schools.com/tags/tag_strong.asp)                          | `[* ...]`                      | Defines important text                                                             |
| [`<em>...</em>`](https://www.w3schools.com/tags/tag_em.asp)                                      | `[_ ...]`                      | Defines emphasized text                                                            |
| [`<ins>...</ins>`](https://www.w3schools.com/tags/tag_ins.asp)                                   | `[+ ...]`                      | Defines a text that has been inserted into a document                              |
| [`<del>...</del>`](https://www.w3schools.com/tags/tag_del.asp)                                   | `[- ...]`                      | Defines text that has been deleted from a document                                 |
| [`<mark>...</mark>`](https://www.w3schools.com/tags/tag_mark.asp)                                | `[% ...]`                      | Defines marked/highlighted text                                                    |
| [`<pre>...</pre>`](https://www.w3schools.com/tags/tag_pre.asp)                                   | `[$ ...]`                      | Defines monospace text (preformatted text)                                         |
| [`<small>...</small>`](https://www.w3schools.com/tags/tag_small.asp)                             | `[. ...]`                      | Defines smaller text                                                               |
| [`<sub>...</sub>`](https://www.w3schools.com/tags/tag_sub.asp)                                   | `[, ...]`                      | Defines subscripted text                                                           |
| [`<sup>...</sup>`](https://www.w3schools.com/tags/tag_sup.asp)                                   | `[^ ...]`                      | Defines superscripted text                                                         |
| [`<span>...</span>`](https://www.w3schools.com/tags/tag_span.asp)                                | `[; ...]`                      | Defines a section in a document                                                    |
| [`<hr>` (`<hr>...</hr>`)](https://www.w3schools.com/tags/tag_hr.asp)                             | `[---]` (`[--- ...]`)          | Defines a thematic change in the content                                           |
| [`<!--...-->`](https://www.w3schools.com/tags/tag_comment.asp)                                   | `[# ...]`                      | Defines a comment                                                                  |
| [`<a href="URL">...</a>`](https://www.w3schools.com/tags/tag_a.asp)                              | `["URL" ...]` or `['URL' ...]` | Defines a hyperlink                                                                |

<!--
Removed:

| HTML tags                                                                                        | ORML alternative tags          | Description                                                                        |
| ------------------------------------------------------------------------------------------------ | ------------------------------ | ---------------------------------------------------------------------------------- |
| [`<h1>...</h1>` to `<h6>...</h6>`](https://www.w3schools.com/tags/tag_hn.asp)                    | `[= ...]` to `[====== ...]`    | Defines a headings (the number of `=` character to the header level is correspond) |
| [`<div>...</div>`](https://www.w3schools.com/tags/tag_div.asp)                                   | `[/ ...]`                      | Defines a section in a document                                                    |
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
-->

#### ⚠️ 1.2. Strict tags

| HTML tags                                                                                        | ORML strict tags | Description                  |
| ------------------------------------------------------------------------------------------------ | ---------------- | ---------------------------- |
| [`<input type="checkbox" disabled="">`](https://www.w3schools.com/tags/tag_input.asp)            | `[ ]`            | Defines a unchecked checkbox |
| [`<input type="checkbox" disabled="" checked="">`](https://www.w3schools.com/tags/tag_input.asp) | `[X]`            | Defines a checked checkbox   |

#### ♾️ 1.3. Extend tags

| HTML tags                          | ORML alternative tags              | Description            |
| ---------------------------------- | ---------------------------------- | ---------------------- |
| `<span class="spoiler">...</span>` | `[? ...]`                          | Defines a spoiler text |
| #TODO                              | `[! "URL" ...]` or `[! 'URL' ...]` | Auto media             |

`#TODO`:
[Document](https://www.pml-lang.dev/docs/reference_manual/index.html#node_doc),
[Chapter](https://www.pml-lang.dev/docs/reference_manual/index.html#node_ch),
[Bibliography](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#bibliography),
[Footnotes](https://docs.asciidoctor.org/asciidoc/latest/syntax-quick-reference/#section-footnotes)

### 📑 2. Markdown simplicity

Because ORML doesn't support [indented code blocks](https://github.github.com/gfm/#indented-code-blocks) so every element (fenced code blocks, lists, tables, ...) can be indented freely (by it own rule) without become a code block.

#### 🔗 2.1. Autolinks

ORML support [autolinks (extension)](https://github.github.com/gfm/#autolinks-extension-) (**not the original [autolinks](https://github.github.com/gfm/#autolinks)**) exactly like from [GFM](https://github.github.com/gfm).

#### 📟 2.2. Codes

ORML support [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [code fence](https://github.github.com/gfm/#code-fence) is a sequence of at least three consecutive `` ` `` characters (and not `~` characters).
- The line with the opening code fence may optionally contain some text that start with the `.` character following the code fence; this is trimmed of leading and trailing whitespace and called the [info string](https://github.github.com/gfm/#info-string) (and it may not contain any `` ` `` characters).

ORML support [code spans](https://github.github.com/gfm/#code-spans) from [GFM](https://github.github.com/gfm) but with the following difference:
- The closing backtick strings of a [code spans](https://github.github.com/gfm/#code-spans) may optionally contain some text that start with the `.` character that function like [fenced code blocks](https://github.github.com/gfm/#fenced-code-blocks)'s [info string](https://github.github.com/gfm/#info-string)

#### 📝 2.3. Lists

ORML support [list items](https://github.github.com/gfm/#list-items)
and [lists](https://github.github.com/gfm/#lists) from [GFM](https://github.github.com/gfm) but with the following difference:
- A [bullet list marker](https://github.github.com/gfm/#bullet-list-marker) is a `-` character (and not a `+` nor a `*` character).
- An [ordered list marker](https://github.github.com/gfm/#ordered-list-marker) is a sequence of 1–9 arabic digits `0-9`, followed by a `.` character (and not followed by a `)` character).

#### 🗄️ 2.4. Tables

ORML support [tables](https://github.github.com/gfm/#tables-extension-) from [GFM](https://github.github.com/gfm) but with the following difference:
- The [delimiter row](https://github.github.com/gfm/#delimiter-row) consists of cells whose only content are hyphens `-`, and optionally, a leading or trailing equals sign `=` (and not colon `:`), or both, to indicate left, right, or center alignment respectively.
- Footer. `#TODO`

#### 🔣 2.5. Backslash escapes

Except inside [code spans or fenced code blocks](#-22-codes), any punctuation or space character preceded by a backslash will be treated literally, even if it would normally indicate formatting.

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

## 💌 Credits
Special thanks to:
- [**PML (Practical Markup Language)**](https://www.pml-lang.dev) by [Christian Neumanns](https://www.pml-lang.dev/about/faq.html#creator)
- [**HTML5 (HyperText Markup Language)**](https://en.wikipedia.org/wiki/HTML5) by [W3C](https://www.w3.org)
- [**GitHub Flavored Markdown**](https://github.github.com/gfm) by [Github](https://github.com)
- [**Pandoc**](https://pandoc.org) by [John MacFarlane](https://johnmacfarlane.net)

<br><br><br><br>

---

> <h1 align="center">Fork with ❤️ by <a href="https://github.com/NNBnh"><i>NNB</i></a></h1>
>
> <p align="center"><a href="https://www.buymeacoffee.com/nnbnh"><img src="https://img.shields.io/badge/buy_me_a_coffee%20-%23F7CA88.svg?logo=buy-me-a-coffee&logoColor=333333&style=for-the-badge" alt="Buy Me a Coffee"></a></p>
